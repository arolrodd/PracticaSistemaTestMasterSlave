# PracticaSistemaTestMasterSlave
Practica de despliegue sobre un servidor dns

1. Creamos la estructura de las maquinas en el archivo de configuración de Vagrantfile
![alt text](/images/image.png)


2. Sacamos los archivos necesarios de la maquina tierra a vagrant y creamos una carpeta file con los archivos
![alt text](/images/image1.png)


3. Configuramos los archivos que hemos sacado a vagrant anteriormente

    -Añadimos la configuración necesaria a el archivo vagrantfile para que los archivos que hemos modificado se copien tanto en la maquina  maestro como en la maquina esclava
 ![alt text](/images/image3.png)   


    -Añadimos en el archivo named la configuración para que se escuche por ipv4
![alt text](/images/image4.png)


    -Añadimos las acl confiables y le decimos que permitimos  la transferencia de archivos de esas acl y además le decimos que no permitimos ipv6
![alt text](/images/image5.png)


    -Añadimos las zonas tanto de MASTER como de ESCLAVO
![alt text](/images/image6.png)
![alt text](/images/image7.png)


    -Configuramos las zonas tanto la directa como la inversa del servidor
![alt text](/images/image8.png)
![alt text](/images/image9.png)


4. Una vez hecha la configuración procedemos a ejecutar las pruebas necesarias para comprobar que todo este configurado correctamente

    -Registros A
![alt text](/images/image10.png)


    -Resolución inversa de las direcciones ips
![alt text](/images/image11.png)


    -Resolver los alias ns1.sistema.test y ns2.sistema.test

![alt text](/images/image13.png)


    -Consultar los servidores NS de sistema.test
![alt text](/images/image14.png)

    -Consultar servidores MX de sistema.test
![alt text](/images/image15.png)
