## Herencia:
- Existirá una clase padre.
- La clase hija herede los atributos y metodos de la clase padre
- Si los atributos estan privados se accede mediante getter and setter, para acceder a ellos:
- Para los metodos no es necesario ya que estan en publico normalmente en la clase Padre.
- Si la clase Padre tienen un metodo en private, este no se hereda. Solo se podra acceder a ellos con sus getter and setter.


Clase Hija:

    sout("Fabricante" + getFabricante());
    sout("Fabricante" + this.getFabricante());


# Para heredar:

    public class ClaseHija extends ClasePadre{

# Se pueden pasar pedidos de datos:
clase Padre:

      public void registrarDatos(Scanner scanner){
        sout("Ingrese el fabricante:" );
        fabricante = scanner.nextLine();
         o 
        sout("Ingrese el fabricante:" );
        this.setFabricante(scanner.nextLine());
        
-----------------
# Si en la clase padre e hija hay métodos con el mismo nombre:
Clase Padre:

    public void imprimirEspecificaiones(){
        //pide fabricante, modelo, color // atributos comunes que tendran otras clases

Clase Hija:

    public void imprimirEspecificaciones(){
       //pide pulgadas(pantalla) 

Necesitamos pedir en la clase Hija los otros datos que estan en la clase padre. Solución (`super`):

Clase Hija:

    public void imprimirEspecificaciones(){
            super.imprimirEspecificaciones();
           //pide pulgadas(pantalla)

# Si no se llamada a super y en el main se llama a la funcion que tiene el mismo nombre en la clase Padre:

    monitor.imprimirEspecificaciones()
Este se referirá a la clase que se encuentre en el Hijo(Monitor).

--------------------
# No se pueden borrar metodos de la clase Padre pero si modificar su comportamiento:
Cuando se imprime un objeto, se imprime su posicion de memoria e implicitamente Java llamada a la función `toString`
Pasos:
- Clic derecho en un espacio en blanco.
- Overridee Methods
- Elegimos toString, en este caso la clasePadre herede de Object

      public String toString(){
        return "hola"  //ya no imprimira la pos de memoria, sino un hola
      }
- Estos significa que solo afectara al `toString` de la clase Padre y de los Hijos que la heredan.
Si aun quiero imprimir la pos de memoria:

       public String toString(){
              String posMemoria = super.toString(); //dispositivo@12443533;
              return "hola"  //
            }

------------------------
# Clase Object:

-Todas las clases heredan de Object

------------------------
# Clase abuelo:

Dispositivo -> Computador -> Computador Cuántico
Para modificar metodos con el mismo nombre en alguno de ellos(Padre o Hijo)se usa `@Override`:

Dispo (abuelo):

    public void metodoPrueba(){
    sout"soy un dispo"
Computador (Padre):

    @Override
    public void metodoPrueba(){
    sout"soy un computador"
Computador Cuántico (hijo):

    @Override
    public void metodoPrueba(){
    sout"soy un cc"

Y si quiero que el hijo (CC) acceda al metodo del abuelo(Dispositivo):
Se debe crear un by-pass en el Padre:

    public void intermedio(){
            super.metodoPrueba();
    }

//Verificar esto, practicar.

-----------------------
# Si creo un metodo y no quiero que usen `@Override` los hijos o nietos:
Debo usar final:

        public final voy metodoNoModificable(){
        }

--------------------------------
# Constructor en clase Padre:

    public Dispositivo(){ //constructor sin parámetros

    public Dispositivo(Srting fabricante){  //constructor con parámetros
        this.fabricante = fabricante
    }

Lo llamo en la clase Hija(Computador):

    public Computador(String fabricante){
        super(); //llamo al constructro sin parámetros
        super(fabricante); // llamo al const. con parámetros

OJO: el constructor siempre debe estar antes de cualquier otra linea de codigo dentro del constructor de la clase Hija:

    public Computador(String fabricante){
            super(fabricante);
            sout("hola");
            .......
            .......

-----------------------------
# La visibilidad de un metodo en la clase Hija no puede ser mayor que en la clase Padre
1. Private
2. Default
3. Protected
4. Public

No se puede crear un metodo con el mismo nombre en la clase Hija como private si en el Padre esta como public. 
La visibilidad de clase Hija debe ser igual a menor que la de la clase Padre.

-------------
## Polimorfismo:
Permite que multiples instancias de clases hijas puedan ser referenciadas por su clase padre.

En el main:
Crear un computador normalmente:

        Computador cc = new Computador();
Pero un computador, tambien es un dispositivo(clase Padre)

    Dispositivo dispositivo1 = new Computador();

Pero esto es un ERROR, ya que no todos los computadores son dispositivos:

    Computador cc = new Dispositivo();

# Acceder a los métodos:
lo normal:

         Computador cc = new Computador();
         cc.setVelocidad(2.5f); //float
Usando polimorfismo:

        Dispositivo dispositivo1 = new Computador()
        dispositivo1.set... //Error
        
No se puede acceder porque la forma de la variable es de dispositivo, para poder acceder a la velocidad debo regresarlo a su forma original, que es un computador.

# Casteo:
    Dispositivo dispositivo1 = new Computador();
    Computador compuCasteo = (Computador) dispositivo1;
    dispositivo1.setVelodidad(2.5f)
-------------------

    Dispositivo dispositivo1 = new Computador();

Si no se que tipo de dispositivo es (computador, teclado o mouse):

    if(dispositivo1) instanceof (Computador){
    Computador ccc = (Computador) dispositivo1;
    ccc.setVelocidad(4.5);
    }
    
    if(dispositivo1) instanceof (Teclado){
    Teclado ttt = (Teclado) dispositivo1;
    ttt.setInalambrico(true);
    }
--------------------
# ¿Sera posibles guardar los diferentes dispositivos (computador, teclado o mouse)?
![image](https://github.com/Pierohc/JAVA-Herencia_Polimorfismo/assets/133154904/2f74d452-eea2-45c3-a100-3a4cf0dffa16)

![image](https://github.com/Pierohc/JAVA-Herencia_Polimorfismo/assets/133154904/a3148e1a-9e14-41b7-a52a-e996a4f3882c)

Imprimir dispositivos ordenadamente usando Polimorfismo:

![image](https://github.com/Pierohc/JAVA-Herencia_Polimorfismo/assets/133154904/e1d4fe55-c342-405b-9a4c-45e00d7dc1e0)



 



    










 
