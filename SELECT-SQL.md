# Orden:

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/7133f2d7-521c-41df-9ae5-63b905b3601b)

# Select - From:
No debe haber una coma antes del `FROM`

Select permite obtener datos de una o más tablas a manera de consulta.

Select no modifica el contenido de las tablas

* = mostrar todas las columnas, pero tambien se pueden mostrar columnas adicionales repetidas:
  
![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/0838aa80-858f-4e13-a104-c158fd7846b2)


código en SQL = Query
-----------
## Si de una tabla solo quiero mostrar nombre, apellido y dni:

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/9272cd88-d4f8-44e3-8220-05fe7c8edef3)

## Se pueden exportar tablas:

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/332a9a1f-85f0-4764-89a7-f20b681cb0fe)

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/518b67ee-71ae-479f-8ab4-71710c2c4d6d)

## Juntar Columnas:

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/d6084f3d-a2f6-4c84-a636-5c0d95baf755)

## Colocar Alias: 
Recordar que antes del **FROM** debe haber un espacio.
Tambien se puede usar comillas dobles o comillas simples y no poner `as`, sin embargo lo recomendable es usar comillas invertidas ``.

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/12c2b97a-fbd7-4f7c-9275-8b178df27794)

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/e81d4cd6-7d36-47bd-b736-5b289f0bcadd)

## Algunas funciones:

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/b9afd169-852e-4c2b-b6ed-e92df60b0bda)

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/f5b7f80e-35a2-49ce-9655-0af367ed985b)

## Para fechas:

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/352ae971-5787-4d32-b887-1cf79cc624d0)

## Mostrar una columna sin repetir datos:
Solo se puede mostrar una unica columna con está opción

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/da996812-f913-4d95-b32d-97a5924c684e)

## Ordenar columna:
Se puede colocar order by salary desc o 

order by salary asc(este ultimo equivale a no poner nada), ya que por defecto ordena de menor a mayor

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/77f95305-a039-42eb-aa1e-d558d9813af3)

---------------------

Y si hay datos que se repiten(como el salario) y quiero que pase a ordenarse por nombre esos comunes en salario:

En este ejemplo Hazel y Steven tienen el mismo salario pero lo ordenamos tal que por nombre respecto al abecedario

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/62894fc1-e816-40c4-98e7-486c5171045f)

Además, el segundo criterio de orden se puede indicar como asc(default) o desc(descendente):

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/9666c4c3-4d72-40e1-8045-0ee98cc839de)


-----------------

Tambien funciona para VARCHAR. Entre numeros y letras, lo mayor serán las letras y lo menos los numeros:

Menor a Mayor: 1,2,...,9,a,b,c,...,z (asc)

Mayor a Menor: z,...,b,a,9,8,...,2,1 (desc)

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/0a4b8151-501b-42f1-98d0-33e5dd20e255)

-------

# Where (filtrado):
Mostrar el empleados con salario mayor a 9000:

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/22a1cdd8-999a-4e5f-878a-216d4319ce17)

2 o más condiciones:

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/7e894f9a-b0d3-4df9-92b8-2788d9cb5b29)

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/b9a02c50-daa6-4e26-a98f-c10a4831dc9d)

Condición de que algo sea no nulo:
Ojo: que sea nulo no significa que sea cero, sino que no existe

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/a928a791-475a-4509-9207-af49cef90db6)

-------------

## Between:
Intervalo cerrado:

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/84e76778-25c3-4774-b2fc-175830245a79)

Intervalo abierto(No cuenta los limites señalados como 3000 y 4000 en este caso):

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/615f0f2f-dcf6-4f01-ae2e-d3fe005b0584)

-------------------
## In():
Sin in:

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/15460a43-0acb-40e0-aea0-c470dc3ddafd)

Con in:

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/3221d065-9d0c-4afe-b7e8-a7edde440a76)

Para excluir:

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/67b74c84-cdac-4450-a080-8ecec8e94289)

-------------
# Like y not Like:
ES SOLO PARA STRINGS
Para no complicarnos con mayusculas o minúsculas podemos usar `lower` o `upper`:

Empiecen con s:

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/a5b1bdd4-d623-424d-a0e9-35ff56a5e95f)


Empiecen con s y tenga en total 5 caracteres:

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/b7f29d86-dc1a-4572-84ce-8f99cdebc65e)


Dos condiciones:

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/a7466f7f-04da-459c-8510-a9556e4e2dc7)

Empleados cuyo nombre no empiece con S:

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/8d426a10-30e1-44fc-8297-26c00c7bb360)


Not Like:

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/d8c8f87b-1414-4f4b-98f7-42ca59cb56e0)

Con escape:
El escape se usa para indicar que lo que está a la derecha del escape no es un símbolo de wildcard, es solo para un caractér(el contiguo).

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/479b5b88-fc56-4c27-9a0f-04d84d60a1f2)

-------------------
## Group by:
Cuando o usamos, agrupara y mostrara teniendo en cuanto al empleado por orden de su PK, en este caso el employee_id, no es por orden alfabetico de su nombre:

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/3b1e2256-0507-4027-9806-2f938e065e3e)


![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/57e07ecd-b3fb-4498-8de4-da9403f42430)

Funciones:

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/edb42047-cc35-4e8b-ba14-79a4e78d30c6)

-----

Respecto a Count para evitar que se imprima la primera fila:

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/18197761-f068-4be0-aec4-2d60280aafaa)

Solucion:

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/f08fa3bb-11c8-44a1-9996-ad8be89f0abb)

-----------
Ordenar por salario maximo de forma ascendente:

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/04a8068f-d41a-48cf-9f9b-03043cc68c27)

Otra forma(en versiones antiguas de SQL) con alias:

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/3e6a20a3-4342-46a0-a692-7e0deb6c784f)

--------

# Having: 
Aplicar un filtrado al resultado de un agrupamiento, si aplico un agrupamiento se genera una nueva tabla y para aplicar un filtrado a esa nueva tabla ya no se usa where, debo usar `having` y a su vez, ello genera una nueva tabla.

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/0c148b1d-c2fc-45fa-9c40-f10533997538)

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/736430bf-d04d-4027-9eb5-5c71bc30081a)

# Limit:
Sirve para limitar la cantidad de resultados que se va a visualizar en el Query. El primer número indica el offset o a partir de la posición de que elemento se mostrará. El segundo número indica cuántos se mostrara.

Otra forma de verlo, donde np es el número de página:

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/0500647f-0521-4e38-8b16-57dbad37516d)

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/d1caddf6-06c1-471d-a011-fbcffd972905)

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/72238867-2d75-43f2-8459-ccc210683d08)

-----------

## Busquedas Cualificadas:
Siempre que pongo tablas deben de estar relacionados entre ellas

Son aquellas que afectan a más de una tabla

Match:
![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/3f4f16f0-923e-45c8-b54e-68cd6d2ba81d)

Hace match de cada empleado con todos los job_id existentes, a pesar de que solo hay un job_id por empleado:

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/33ab06f9-5327-4e4c-9b4c-15b4a5e4d925)

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/86a7180d-97e8-4487-b01c-e8a2e688f109)

Solución:

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/711881a6-a95b-4cc9-ae91-1d9ce401b2ae)

-----
Si existen dos columnas con el mismo nombre se debe especificar de donde proviene: 

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/6167b9b2-81a0-418a-88ca-6f05927aedfd)

Con abreviacion de tablas: 

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/34724bcb-6e79-4dc0-ade8-5ffdeea2e3f4)

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/2767816c-5358-4c6b-b3be-be6684e98de8)

------------------

El jefe del jefe del empleado:

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/199b7260-8ecf-43cd-9688-abad041295fd)

-----------------------
Ver como llegar de una tabla a otra:

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/0441d8c4-495f-4075-ac09-da46109523c0)

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/003450a1-e68c-41cb-a1eb-dd1dbdad7690)


## Inner - Join:

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/4b05e571-7d74-4ffc-9be5-972972378b48)

Unna linea inner join se relaciona con todo lo que está antes de está dentro del `from`

----------------------------
## Left - Join:
Solo cambia que todo lo de la izquiera se muestra y lo de la derecha si no coincide la relacion lo vuelve nulo, por ejemplo, habi aun empleado que no tiene jefe, porque es el de mayor jerarquia en la empresa y otro empleado que no tenia departamento, por lo tanto, no tiene location, country ni region, por lo tanto consideramos left join.

Si se enuncia "tenga o no" usamos left join

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/9354c0f1-3b7c-4076-9c20-007410eade73)

------------

## Si queremos mostrar los empleados con el mayor suelda, saldrá solo uno si lo hacemos de esta forma:

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/55348f66-712c-4b06-a367-a349d7abdc23)




Primero averiguamos el sueldo maximo:

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/5bd281db-38d1-4da5-99b4-70f3059b3f40)

Verificamos como sería la lista con codigo hardcodeado:

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/5bb792d4-c5e1-400c-96f1-1da39c55597f)


Solución: 

![image](https://github.com/Pierohc/SELECT-SQL/assets/133154904/35b9bc5a-5af8-4bd8-b351-b36d835626e5)























































