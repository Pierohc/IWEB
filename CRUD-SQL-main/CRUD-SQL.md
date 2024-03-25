insert into usuarios (idUsuario,idRol,idEstado,nombres,apellidos,codigo,correo_pucp,contrasena,fecha_creacion,ultimo_login,cant_eventos_inscritos,motivo_rechazo) 
values ('108', 'GRADUAT', 'ACC', 'Juan', 'Huaman', '20200108', 'a20200108@pucp.edu.pe', '108', now(), NULL, '0', NULL)


use proyectoweb;

ALTER TABLE usuarios
add column idRolAcademico VARCHAR(15);

ALTER TABLE usuarios
ADD CONSTRAINT `fk_rol_academico` FOREIGN KEY (`idRolAcademico`) // agregar una columna idRolAcademico que ser FK
REFERENCES `proyectoweb`.`rol_academico` (`idRolAcademico`) // La relacionara sacandola de la tabla rol_academico seleccionando la columna idRolAcademico de esa tabla
    


![image](https://github.com/Pierohc/CRUD-SQL/assets/133154904/ce0015bd-159d-4d3c-b2d1-e442802da079)

---------------------

# Insert:
Es recomendable ver que columnas son no nulas para tener más información

![image](https://github.com/Pierohc/CRUD-SQL/assets/133154904/d47233c3-57e5-4309-8db8-8f673f0dff03)

----------
Formas de ingresar fechas:

![image](https://github.com/Pierohc/CRUD-SQL/assets/133154904/7275144d-670c-49f2-ac9d-6b7ec186916b)

![image](https://github.com/Pierohc/CRUD-SQL/assets/133154904/2d8d9e4c-7c4d-4256-a647-fb85db65e72f)


---------------------


# Update:

° Permite modificar la información existente en uno o varios registros de una tabla.

° where_condition : es una expresión lógica que determina que filas se actualizarán. Sólo se actualizarán las filas que satisfagan la expresión. Si no se incluye la cláusula WHERE(no hay condición), se modificarán todos los registros de la tabla.

![image](https://github.com/Pierohc/CRUD-SQL/assets/133154904/c56f49d7-33af-4efc-9956-4625a80ba7a4)

![image](https://github.com/Pierohc/CRUD-SQL/assets/133154904/cc99928c-ac97-4f1f-831b-33435debf0e1)

![image](https://github.com/Pierohc/CRUD-SQL/assets/133154904/df76f908-4536-47b6-848c-90ccf9210f91)

----------------------

# Delete: 

![image](https://github.com/Pierohc/CRUD-SQL/assets/133154904/73c93631-e620-498c-a0ac-d04179eca36a)

-------
Borrar varios(por corroborar):

![image](https://github.com/Pierohc/CRUD-SQL/assets/133154904/f2f3ab8e-7db9-4e87-a6a1-5c2d15bd25bb)

--------------

![image](https://github.com/Pierohc/CRUD-SQL/assets/133154904/91514b64-5235-40bb-a9ce-adfc6a415761)

![image](https://github.com/Pierohc/CRUD-SQL/assets/133154904/1e3381d9-b5af-4dde-abd9-8e763921f2ba)

------------
## Delete en tablas relacionadas: 

![image](https://github.com/Pierohc/CRUD-SQL/assets/133154904/fe5b2deb-6cb7-4a6c-ae12-664c82ad9856)

![image](https://github.com/Pierohc/CRUD-SQL/assets/133154904/e7547dae-8e59-4631-a78d-8329cbdd646a)

![image](https://github.com/Pierohc/CRUD-SQL/assets/133154904/3f1dea6b-500f-4d49-b6eb-eb9ef3208991)











