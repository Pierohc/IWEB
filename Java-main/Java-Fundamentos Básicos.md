//Los atributos deben ser privados.

//En el main se crean los objetos.

//CLASE_TIPODATO   nombre_propio = new CONSTRUCTOR

//getter <- para poder imprimir, te da el dato  

//setter <- Para asignar un valor o string

--------------------

# OJO:
Si se crea un metodo y lleva un parámetro, no se debe crear antes en esa clase, solo se crea en el main. En esa clase si se crea dentro de la funcion:

                    void funcion(Arraylist<Clase1> lista)
Los HashMap,HashSet y Scanner se crean donde irian los atributos:

          Scanner scanner = new Scanner(System.in);
          HashSet<String> numeros = new HashSet<>();
          HashMap<Float,String> usuarioContraseña = new HashMap<>();

## Cuando un ArrayList o Hash es una atributo:
Getter:
  Para obtener el arreglo y trabajar con el, incluye:

      isEmpty()
Setter:
  Para pasarle un ArrayList o Hash:

      -----.setListaProducto(Lista creada);

Para el add, será necesario crear un metodo nuevo aparte del getter and setter:

    public void agregarProducto( Producto productoNuevo ){
      listaProductos.add(productoNuevo)
    }

## Cuando se use for each, dependiendo el objetivo, será necesario inicializar una variable;

## Registrar datos sin repetir:

    public void agregarUsuario(Usuario nuevoUsuario){
  
          if (listaUsuarios.isEmpty()){
              listaUsuarios.add(nuevoUsuario);
              System.out.println("Usuario registrado con éxito");
              
          }else{
  
              boolean idEnUso = false; //se inicializa
              for(Usuario elemento: listaUsuarios ){
                  if (elemento.getCodigoPUCP().equals(nuevoUsuario.getCodigoPUCP())){
                      idEnUso = true;
                      break;
                  }
              }
              
  
              if (idEnUso){  //si es true, osea que está en uso
                  System.out.println("El ID del usuario ya está en uso. Intente con otro.");
              }else{
                  listaUsuarios.add(nuevoUsuario);
                  System.out.println("Usuario registrado con éxito");
              }

  
          }
      }
----------------------------

# Constructor:

Ejemplo de un constructor sin parámetros:


    public class MiClase {
        private int valor;
    
        // Constructor sin parámetros (constructor por defecto)
        public MiClase() {
            valor = 0; // Valor inicial predeterminado
        }
    
        // Otros métodos y atributos de la clase...
    }


2. Constructor con parámetros:
Ejemplo de un constructor con parámetros:

    public class Persona {
        private String nombre;
        private int edad;
    
        // Constructor con parámetros
        public Persona(String nombre, int edad) {
            this.nombre = nombre;
            this.edad = edad;
        }
    
        // Otros métodos y atributos de la clase...
    }


En este ejemplo, la clase `Persona` tiene un constructor con parámetros que permite especificar el nombre y la edad de una persona al crear un objeto de esa clase. Los valores proporcionados como argumentos se utilizan para inicializar los atributos correspondientes.

Para utilizar estos constructores, puedes crear objetos de la clase y llamar al constructor apropiado según tus necesidades:


    MiClase objeto1 = new MiClase(); // Constructor sin parámetros
    Persona persona1 = new Persona("Juan", 30); // Constructor con parámetros

Los constructores sin parámetros proporcionan valores predeterminados, mientras que los constructores con parámetros permiten la personalización de los valores iniciales de los atributos de un objeto.


--------------
# LEER DATOS:

System.in para ingresar datos con el teclado.

scanner.nextLine() posiciona el cursos hasta que el usuario ingrese un dato y presione un enter, ese dato se guarda en una variable.

Recordar quitar el "ln" al println para que el cursor no este en la siguiente linea.

          Libreria: import java.util.Scanner;
          
          Scanner scanner = new Scanner(System.in); //creas un scanner que lo puede usar en todo el codigo
          String datoIngresado = scanner.nextLine();

Scanner todo lo guarda como String.
Si queremos ingresar un numero y luego convertirlo a entero:

                    int numero = Integer.parseInt(numeroString);

Si queremos convertir un True o False:
                    int opcion = Boolean.parse
--------------------------------------------

# Problema con nextInt():
            System.out.printf("Seleccione una opción: ");
            int opcion = scanner.nextInt();
            
en este caso sabemos que lo que se va a ingresar será un número y al hacer uso del next.Int(), escribiremos el numero y daremos enter para ingresar el dato; sin embargo, cuando intentas leer una cadena con scanner.nextLine() después del nextInt(), el nextLine() consume la línea en blanco (Enter) dejada por la entrada anterior en lugar de esperar una entrada real de texto.

Para solucionar este problema, puedes agregar un scanner.nextLine() adicional justo después de leer el número para consumir el carácter de nueva línea antes de leer la cadena. . Para ello si lo siguiente que queremos hacer es ingresar de nuevo un dato, deberemos colocar un scanner.nextLine():

            System.out.printf("Seleccione una opción: ");
            int opcion = scanner.nextInt();
            scanner.nextLine();


--------------------

# Una clase dentro de otra clase:
          

se creo un estudiante dentro de una clase de jerarquia mayor y estudiante que es una clase Estudiante, tiene como atributo computadora y la computadora es de clase Computadora, que es una clase adicional de jerarquia menor que Estudiante, la cual tiene una funcion llamada registro():


          Computadora computadora = new Computadora();
          
          public void registrarEstudiante(Estudiante estudiante){
           
          computadora.registro(); //llamo al registro de la computadora
          estudiante.setComputadora(computadora); //guardo la informacion de esa computadora en el estudiante
          System.out.println("El precio es: " + estudiante.getComputadora().getPrecio());



-----------------
CONDICIONALES:
y = &&
o = ||

Si el dato es String:

    if(opcion.equals("texto")){
    }
Si el dato es Int, para numeros:

    if(opcion == 1){
    }

Si una clase esta vacia:

    if(albergue.getGato1() == null){
    albergue.setGato1(gato);
    }


----------------------

Math.PI

-----------------

public final int num = 5 <- atributo que no se puede cambiar, valor fijo.

----------------

Si un metodo a su vez es una clase:

Agregar un valor:

    firulais.getGalleta().setIngredientePrincipan("carne");

Retornar un valor:

    firulais.getGalleta().getMarca()


----------------------------
Ternario para asignaciones:

    int total = 20
    total = num > 6 ? 40 : 10;


    System.out.printf("Permite correo? (S/N): ");
                    String correo = scanner.nextLine();
                    nuevaVLan.setPermiteCorreo(correo.equals("s")? true:false);

Reemplaza a:

    if(num>6){
     total = 40;
    }else{
      total = 10;
    }

------------------------------

# break para while si usamos switch:
  
    buclePrincipal:

    while (true){

        switch{
        
          case 1:
            break;
            
          case2:
            break;
            
          case 3:
            breack buclePrincipal; //Finaliza todo el bucle while
            
         }
     }

---------------------------------
# While:

    while(i<10){
      i++; 
      }
# For:

    for(int i=1; i <=10; i++){

    }


------------------------
# Arreglos:
Crear arreglos:

    int[] arreglo = new int[10]
    int arreglo[] = new int[10]

    int[] notas;
    notas = new int[15];

    int[] notas = {10,17,18,20,15}

Dar valores:

      notas[0] = 10;
      notas[1] = 20;...

    
Conocer tamaño del arreglo:

    sout(arreglo.length);

Imprimir todos los valores:

    for(int i=0; i < arreglo.length; i++){
        sout(arreglo[i]);
     }



Se puede decir que con esa declaracion si o si listaLabs es diferente de null?  

    Laboratorio[] listaLabs = new Laboratorio[3]; 
Sí, con la declaración `Laboratorio[] listaLabs = new Laboratorio[3];`, `listaLabs` definitivamente no será `null`. Esta línea de código crea un nuevo arreglo `listaLabs` de tipo `Laboratorio` con una longitud de 3 elementos y lo inicializa automáticamente con valores `null` para cada elemento.

Por lo tanto, después de esta declaración, puedes estar seguro de que `listaLabs` no es `null`, pero los elementos dentro del arreglo serán `null` hasta que los inicialices explícitamente con objetos `Laboratorio`.


-------------------------------------------

# Arreglo Multidimensional (Matrices):

Longitud multidimensional constante:

![image](https://github.com/Pierohc/Java/assets/133154904/bb528412-4075-4425-bed5-f6e50dacc44b)

Longitud multidimensional variable:

![image](https://github.com/Pierohc/Java/assets/133154904/812486d7-9087-41a8-a486-0fbefebb4e72)



## Imprimir matriz: Se necesita un doble for

    for(int i=0; i<3;i++){
    
        for(int j=0; j<5; j++){
        
        }
     }

## Creacion:

    int[][] matriz = new int[3][4];
En este caso se tienen 3 filas y 4 columnas, tambien se podría declarar solo las filas:

      int[][] matriz = new int[8][];
Caso contrario no se puede hacer solo declarando columnas;

## Arreglos segun tamaño:
    int[][] matrizBidimensional;
    int[][][] matrizTridimensional;

## Longitud de arreglos multidimensionales:
Puedes obtener la longitud de cada dimensión de un arreglo multidimensional utilizando la propiedad length. Por ejemplo:

    int filas = matriz.length; // Obtiene el número de filas
    int columnas = matriz[0].length; // Obtiene el numero de columnas asumiendo que todas       las filas tienen la misma cantidad de columnas

## Matriz sin valores:
    int[][] matriz = null;
Esto declara una matriz bidimensional llamada matriz, pero aún no se ha inicializado. Puedes asignarle un valor más tarde cuando lo necesites.

## Matriz con valores específicos:
    int[][] matriz = {{1, 2, 3}, {4, 5, 6}, {7, 8, 9}};

## Declarar matriz 3x3(ejemplo):
    estante[0] = new int[]{1, 2, 3};
    estante[1] = new int[]{4, 5, 10};
    estante[2] = new int[]{6, 7, 8};

## Darle valores:

    int[][] matriz = new int[3][3];
    for (int i = 0; i < matriz.length; i++) {
        for (int j = 0; j < matriz[i].length; j++) {
            matriz[i][j] = i + j;
        }
    }


## Obtener valores de una matriz:

    for (int i = 0; i < matriz.length; i++) {
        for (int j = 0; j < matriz[i].length; j++) {
            int valor = matriz[i][j];
            // Realiza alguna operación con el valor
        }
    }
    
--------------------------------------

# ArrayList:

Libreria para usar Array(herramiento para manejar arreglos):

    java.util.ArrayList;
    
![sd](https://github.com/Pierohc/Java/assets/133154904/cb37a48a-5ee7-4d2d-97ad-0bd7fb9591b5)

![Sin título](https://github.com/Pierohc/Java/assets/133154904/2fc7b0cd-4b77-46bb-8c56-1217f252db60)

![aaa](https://github.com/Pierohc/Java/assets/133154904/bf309d40-896b-4e9f-a08e-96793a0973c2)


Imprimir elementos de un Arraylist:

        ArrayList<String> lista = new ArrayList<>();
        
        // Agregar elementos a la ArrayList
        lista.add("Manzana");
        lista.add("Banana");
        lista.add("Cereza");
        
Usar un bucle foreach para imprimir los elementos
        
        for (String elemento : lista) {
            System.out.println(elemento);
        }

------------------------------------
# Funcion Split:

        String correo = "a20200814@pucp.edu.pe";
        String partes[] = correo.split("@");

        System.out.println(partes[0]); //Imprimir solo un elemento del arreglo

        for (String eachPart : partes){ //Imprimir todo el arreglo
            System.out.println(eachPart);
        }

------------------------------------
# Verificar si una clase está vacía:

          if (nuevoEstudiante.getComputadora() == null){
              System.out.println("compu vacia");
          }

---------------------------
# Public static void:
Un método estático en Java es un método que pertenece a una clase en lugar de pertenecer a una instancia específica de esa clase. Puedes llamar a un método estático directamente desde la clase sin necesidad de crear un objeto de la clase. Aquí tienes una explicación simple y un ejemplo:

Supongamos que tienes una clase llamada `Matematicas` con un método estático que suma dos números:

```java
public class Matematicas {

    public static int sumar(int a, int b) {
        return a + b;
    }

}
```

En este ejemplo, `sumar` es un método estático de la clase `Matematicas`. Puedes llamar a este método sin crear un objeto `Matematicas`:

```java
int resultado = Matematicas.sumar(5, 3);
System.out.println("La suma es: " + resultado);
```

No necesitas crear una instancia de `Matematicas` para usar `sumar`. Simplemente usas el nombre de la clase seguido del nombre del método estático para realizar la suma.

Los métodos estáticos son útiles para operaciones que no dependen del estado de un objeto específico y se pueden utilizar en situaciones en las que no es necesario crear una instancia de la clase. Se utilizan comúnmente en utilidades matemáticas, funciones de utilidad y métodos de fábrica en clases de utilidad.

-----------------------

# HashMap:

          import java.util.HashMap;

Ojo: 

int-> Integer

double -> Double

float -> Float

cadena -> String

Primero se define el tipo de dato de la key(clave) y luego de su valor, lo llamamos hashmap.
Para este ejemplo se asociaran nombres y edades y se llamara mapaEdades:

          Map<TipoDatoKey, TipoDatoValor> mapaEdades = new HashMap<>();
          Map<String, Integer> mapaEdades = new HashMap<>();


empezamos el mapeo (Agregar elementos):

          mapaEdades.put("Juan", 30);
          mapaEdades.put("María", 25);
          mapaEdades.put("Pedro", 40);
          mapaEdades.put("Ana", 22);

Imprimir u obtener un dato del HashMap (lo unico que se obtienen son los valores):

          int edadJuan = mapaEdades.get("Juan");
          System.out.println("La edad de Juan es: " + edadJuan);


Cantidad de elementos de un HashMap:

          int cantidadElementos = mapaEdades.size();
          sout("La cantidad de elementos es:" + cantidadElementos);

Maneras de saber si una KEY existe:


          boolean existe = mapaEdades.containsKey("Juan")
          sout(existe) // si existe imprimirá "true", sino "false"

         
          //OTRA MANERA:
          
          String nombre = "María";
          if (mapaEdades.containsKey(nombre)) {
            System.out.println(nombre + " está en el mapa.");
          } else {
            System.out.println(nombre + " no está en el mapa.");
          }


![image](https://github.com/Pierohc/Java/assets/133154904/f87c5cee-ed3c-4875-9d4d-0cb3a730869f)

Recorrer elementos del HashMap:

Puedes recorrer un `HashMap` utilizando el método `keySet()` o `values()`:

1. Recorrer las claves (`keys`) del `HashMap` y luego obtener los valores correspondientes:

        HashMap<String, Integer> numeros = new HashMap<>();
        numeros.put("Uno", 1);
        numeros.put("Dos", 2);
        numeros.put("Tres", 3);

        // Recorrer las claves y obtener los valores correspondientes

        for (String key : numeros.keySet()) {
            Integer valor = numeros.get(key);
            System.out.println("Clave: " + key + ", Valor: " + valor);
        }
    



2. Recorrer los valores directamente utilizando `values()`:

        HashMap<String, Integer> numeros = new HashMap<>();
        numeros.put("Uno", 1);
        numeros.put("Dos", 2);
        numeros.put("Tres", 3);

        // Recorrer los valores directamente

        for (Integer valor : numeros.values()) {
            System.out.println("Valor: " + valor);
        }
    
-------------------------------------------------

# HashSet:
          import java.util.HashSet;
              
Crear un HashSet de cadenas:

                  HashSet<String> listaFrutas = new HashSet<>();
          
Agregar elementos:

                  listaFrutas.add("Manzana");
                  listaFrutas.add("Banana");
                  listaFrutas.add("Cereza");
          
Verificar si un elemento ya existe o no:


        HashSet<String> conjunto = new HashSet<>();

        // Agregar elementos al HashSet
        listaFrutas.add("Manzana");
        listaFrutas.add("Banana");
        listaFrutas.add("Cereza");

        // Verificar si un elemento existe en el conjunto
        String elementoBuscado = "Banana";
        if (listaFrutas.contains(elementoBuscado)) {
            System.out.println(elementoBuscado + " existe en el conjunto.");
        } else {
            System.out.println(elementoBuscado + " no existe en el conjunto.");
        }

        // Verificar otro elemento que no está en el conjunto
        String elementoNoEncontrado = "Uva";
        if (listaFrutas.contains(elementoNoEncontrado)) {
            System.out.println(elementoNoEncontrado + " existe en el conjunto.");
        } else {
            System.out.println(elementoNoEncontrado + " no existe en el conjunto.");
        }

Otra forma:

          boolean existe = listaFrutas.contains("fruta1");
          //si se imprime existe, imprimirá "true" o "false"

Eliminar un elemento:

          listaFrutas.remove("fruta1");

Cantidad de elementos:

                  System.out.println("Tamaño del conjunto: " + listaFrutas.size()); // Salida: 3

Limpiar todo un HashSet:

          listaFrutas.clear();

          //verificar si ya está vacío:

          boolean verificar = listaFrutas.isEmpty();


Recorrer elementos de un HashSet:

        HashSet<String> listaFrutas = new HashSet<>();
        listaFrutas.add("Manzana");
        listaFrutas.add("Banana");
        listaFrutas.add("Cereza");

        // Recorrer el HashSet de frutas utilizando un bucle for-each
        for (String fruta : listaFrutas) {
            System.out.println("Fruta: " + fruta);
        }
  

 

          













          





