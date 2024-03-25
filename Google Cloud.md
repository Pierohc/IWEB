ver si tienes java:

![image](https://github.com/Pierohc/Cloud/assets/133154904/692759d9-c176-4f24-be90-0ac179872fa4)


Actualizo el sistema y luego instalo java:
    
    sudo apt update && sudo apt upgrade -y
    sudo apt install openjdk-17-jre-headless

Verificar la version que tengamos instalada: 

    java -version

Instalar tomcat:
    
    wget https://dlcdn.apache.org/tomcat/tomcat-10/v10.1.16/bin/apache-tomcat-10.1.16.tar.gz

Descomprimir:

    tar xvf tomcat....


Mover a carpeta de users:

![image](https://github.com/Pierohc/Cloud/assets/133154904/995a41a6-209b-4162-8378-a4cc3f88bf1f)

    sudo mv ./apache-tomcat-10.1.16 /usr/share/apache-tomcat

Vemos el dueño de la carpeta y le tenemos que agregar un usuario tomcat:

![image](https://github.com/Pierohc/Cloud/assets/133154904/176c45dc-262a-46b9-b40f-86637b77d1b3)

![image](https://github.com/Pierohc/Cloud/assets/133154904/a318f0fb-3401-43f1-becf-973c21dcc3a8)

![image](https://github.com/Pierohc/Cloud/assets/133154904/da91c27b-f0d9-4628-a046-fb0e051a8b86)


## Ahora, debemos especificar los usuarios que accederán al tomcat:


![image](https://github.com/Pierohc/Cloud/assets/133154904/a3b29aeb-a6a1-40d4-b0b8-1e47c1f734b5)


Antes de tomcat-users:
    
    <!-- manager section user role -->
    <role rolename="manager-gui" />
    <user username="manager" password="telecom2022" roles="manager-gui" />
    
    <!-- admin section user role -->
    <role rolename="admin-gui" />
    <user username="admin" password="telecom2022" roles="manager-gui,admin-gui" />


----------------------

## por defecto permite solo localhost, debemos permitir que ello se expanada a mas que solo eso:

![image](https://github.com/Pierohc/Cloud/assets/133154904/79c66c71-ed74-4802-9a6a-eae8ea05efcf)

comentamos valve:

![image](https://github.com/Pierohc/Cloud/assets/133154904/561569d1-bc97-4295-8261-f1304fe98338)

## Para evitar que el tomcat dee de correr como servicio y siempre este corriendo como servicio:

![image](https://github.com/Pierohc/Cloud/assets/133154904/16c26f5c-5545-40db-bef6-9b9bab2ebfbd)

![image](https://github.com/Pierohc/Cloud/assets/133154904/36108efb-248e-455f-8285-802d0f4d54aa)

[Unit]
Description=Tomcat
After=syslog.target network.target

[Service]
Type=forking

User=tomcat
Group=tomcat

Environment=JAVA_HOME=/usr/lib/jvm/java-17-openjdk-amd64
Environment='JAVA_OPTS=-Djava.awt.headless=true'

Environment=CATALINA_HOME=/usr/share/apache-tomcat
Environment=CATALINA_BASE=/usr/share/apache-tomcat
Environment=CATALINA_PID=/usr/share/apache-tomcat/temp/tomcat.pid

ExecStart=/usr/share/apache-tomcat/bin/catalina.sh start
ExecStop=/usr/share/apache-tomcat/bin/catalina.sh stop

[Install]
WantedBy=multi-user.target

Y reiniciamos el servicio:

![image](https://github.com/Pierohc/Cloud/assets/133154904/1442c20b-a0f9-48c9-ae53-7070fd86ffac)

Vemos el estado del servicio tomcat. Ese tomcat hace referencia a como llamamo el archivo de servicio, en este caso fue tomcat.service:

![image](https://github.com/Pierohc/Cloud/assets/133154904/44219c6f-83b2-4d62-bd2a-cbf628c4fe76)

Reiniciamos el tomcat para que ahora si esté activo:

![image](https://github.com/Pierohc/Cloud/assets/133154904/e4029438-3045-4fcb-a772-62812747fb00)


CTRL + C
Por ultimo habilitamos que cada vez que volvamos a reinicar la VM, se prenda automaticamente el tomcat:

![image](https://github.com/Pierohc/Cloud/assets/133154904/0b369afc-b234-47d6-ad6d-c41e7f4b522c)

Verificamos que el tomcat esté corriendo y vemos que si en el puerto 8080:

![image](https://github.com/Pierohc/Cloud/assets/133154904/116429b4-240b-4f56-80af-915614a22dcd)

Por ultimo debemos habilitar el puerto 8080 de nuestra VM, creamos una regla de firewall y la añadimos luego a la VM.

----------------------------------------------------------------------------------------------------------

# Crear vm para Base de Datos en Google Cloud:













