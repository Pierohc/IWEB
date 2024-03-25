## Crear proyecto:

![image](https://github.com/Pierohc/Servidores-Web/assets/133154904/8b942d03-c0c9-4c5a-8909-be9dcedd769a)

Para Tomcat 10 es Jakarta 10, y asi respectivamente si cambiamos la versión del Tomcat

![image](https://github.com/Pierohc/Servidores-Web/assets/133154904/b1dd4031-d66d-4d61-8fa2-81a2f055a819)

----------------
En resources pueden ir imágenes, videos, música o css

![image](https://github.com/Pierohc/Servidores-Web/assets/133154904/c81c7570-c6c2-4c2d-b217-bd24d8884589)

-------------
## Formato en el mundo web:

![image](https://github.com/Pierohc/Servidores-Web/assets/133154904/a63b9e56-e570-411b-8443-f1037a6c24d3)

A la ruta también se le llama contexto o context path.

Para ver el proyecto:

![image](https://github.com/Pierohc/Servidores-Web/assets/133154904/d5e3ad52-5a0b-4a8a-8dfd-4cf6f25af286)

![image](https://github.com/Pierohc/Servidores-Web/assets/133154904/a7510660-ac48-4cae-9f75-a7a7f52019f3)

![image](https://github.com/Pierohc/Servidores-Web/assets/133154904/a8f8c5f1-151c-400b-9aa8-ebc55e8bb8a9)

Tambien podemos modificar el nombre del proyecto.
-----------------------
Update solo agrega nuevos recursos, si es resources es solo imagenes o media, si solo editamos clases ya creadas y media es la segunda opcion de Update.
Si agregamos nuevas clases o Servlet o una nueva libreria en el pom seria un redploy, también cuando agregamos codigo HTML dentro del doGet.
Si algo funciona mal podemos reiniciar el servidor.

![image](https://github.com/Pierohc/Servidores-Web/assets/133154904/85870b49-f16a-45db-9765-7ff049b009ad)

Si configuramos algo en la parte superior de IDE como Tomcat, reiniciamos el servidor.

--------------------------------------
Los formularios son un post

Los href, ir de una pagina a otra con botones es un get. Vinculos entre paginas es get. poner una url en el bbuscardor superior de google también es un get.

![image](https://github.com/Pierohc/Servidores-Web/assets/133154904/ba0def15-d72f-4ef1-af84-e481bdc66897)

----------------------------
## Agregar una nueva clase Servlet:

![image](https://github.com/Pierohc/Servidores-Web/assets/133154904/34c03472-8293-44a5-9a69-0471c58dd6c2)

----------------------

## Agregar codigo SQL. Va en esta parte:

Debemos agregar la dependencia de SQL en el archivo pom, y refrescar Maven.

![image](https://github.com/Pierohc/Servidores-Web/assets/133154904/ed7f91d2-1528-4410-8af4-4a24cc99785d)

![image](https://github.com/Pierohc/Servidores-Web/assets/133154904/104dcfb6-bfb2-4fbd-a0a0-08db5c6fbb07)

![image](https://github.com/Pierohc/Servidores-Web/assets/133154904/081d6498-80ef-49ad-92ab-f2abbdb5782b)


----------------------

# MVC:

![image](https://github.com/Pierohc/Servidores-Web/assets/133154904/083dbaa0-6ba8-449f-9af6-bc7bb44c4a55)

![image](https://github.com/Pierohc/Servidores-Web/assets/133154904/a14d54e6-9c51-40bb-ab40-d1ff291c8ab7)

Todo lo que tenga que ver con base de datos va en los DAOS. Lo recomendable esc rear un dao por cada tabla.

Lo que viaja entre las capas son los beans.
Un bean en la representacion de ima tabla de base de datos en Java.

------------------------------
Todo enlace, href, debe ir hacia un controlador, es decir, hacia un Servlet.

------------------
Para un formulario:

![image](https://github.com/Pierohc/Servidores-Web/assets/133154904/19a86b42-5e51-49b1-ac58-ebb96eb9e54e)

--------------------
Bean(Job) -> el objeto
Dao(JobDao) -> 

