Clase DaoBase:

    package com.example.proyectoweb.model.daos;
    
    import java.sql.Connection;
    import java.sql.DriverManager;
    import java.sql.SQLException;
    
    public abstract class DaoBase {
        public Connection getConnection() throws SQLException {
    
            try {
                Class.forName("com.mysql.cj.jdbc.Driver");
            } catch (ClassNotFoundException e) {
                throw new RuntimeException(e);
            }
    
            String user = "root";
            String pass = "root";
            String url = "jdbc:mysql://localhost:3306/proyectoweb";
    
            return DriverManager.getConnection(url,user,pass);
        }
    }


Como usarla:

Con Prepared Statement:

     public void editarEstadoUsuario(String idUsuario, String nuevoEstado){

        String sql = "update usuarios set idEstado = ? where idUsuario = ?";

        try(Connection conn = getConnection();
        PreparedStatement pstmt = conn.prepareStatement(sql)) {

            pstmt.setString(1,nuevoEstado);
            pstmt.setString(2, idUsuario);
            pstmt.executeUpdate();

        } catch (SQLException e) {
            throw new RuntimeException(e);
        }
    }


    public void eliminarUsuario(String idUsuario){

        String sql ="delete from usuarios where idUsuario = ?";

        try(Connection conn = getConnection();
            PreparedStatement pstmt = conn.prepareStatement(sql)) {
            
            pstmt.setString(1,idUsuario);
            pstmt.executeUpdate();

        } catch (SQLException e) {
            throw new RuntimeException(e);
        }


    }


    public ArrayList<Usuario> listarPorEstado(String estado){
            ArrayList<Usuario> listaUsuarios = new ArrayList<>();

            String sql = "select * from usuarios where idEstado = ?";


            try(Connection conn = getConnection();
            PreparedStatement pstmt = conn.prepareStatement(sql) ) {

                pstmt.setString(1,estado);

                try(ResultSet rs = pstmt.executeQuery()){

                    while (rs.next()){
                        Usuario u = new Usuario();
                        u.setIdUsuario(rs.getInt(1));
                        u.setIdRol(rs.getString(2));
                        u.setIdEstado(rs.getString(3));
                        u.setNombres(rs.getString(4));
                        u.setApellidos(rs.getString(5));
                        u.setCodigo(rs.getString(6));
                        u.setCorreo(rs.getString(7));
                        u.setUltimoLogin(rs.getString(9));

                        listaUsuarios.add(u);
                    }
                }
            } catch (SQLException e) {
                throw new RuntimeException(e);
            }

        return listaUsuarios;
    }


Con Statement:


    public ArrayList<Usuario> listarTodosUsuarios (){ //admin

        //Conexión a la DB
        String sql = "select * from usuarios where idEstado != 'PEN'";

        ArrayList<Usuario> listaUsuarios = new ArrayList<>();

        try(Connection conn = getConnection();
            Statement stmt = conn.createStatement();
            ResultSet rs = stmt.executeQuery(sql)){

            while(rs.next()){

                Usuario usuario = new Usuario();

                usuario.setIdUsuario(rs.getInt(1));
                usuario.setNombres(rs.getString(4));
                usuario.setApellidos(rs.getString(5));
                usuario.setCodigo(rs.getString(6));
                usuario.setIdRol(rs.getString(2));
                usuario.setIdEstado(rs.getString(3));
                usuario.setUltimoLogin(rs.getString(9));

                listaUsuarios.add(usuario);


            }

        }catch(SQLException e){
            throw new RuntimeException(e);
        }

        return listaUsuarios;
    }
