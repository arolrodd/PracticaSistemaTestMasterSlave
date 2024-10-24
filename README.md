# PracticaSistemaTestMasterSlave
Practica de despliegue sobre un servidor dns

1. Creamos la estructura de las maquinas en el archivo de configuración de Vagrantfile
![alt text](/PracticaSistemaTestMasterSlave/images/image.png)


2. Sacamos los archivos necesarios de la maquina tierra a vagrant y creamos una carpeta file con los archivos
![alt text](/PracticaSistemaTestMasterSlave/images/image1.png)


3. Configuramos los archivos que hemos sacado a vagrant anteriormente

    -Añadimos la configuración necesaria a el archivo vagrantfile para que los archivos que hemos modificado se copien tanto en la maquina  maestro como en la maquina esclava
 ![alt text](/PracticaSistemaTestMasterSlave/images/image3.png)   


    -Añadimos en el archivo named la configuración para que se escuche por ipv4
![alt text](/PracticaSistemaTestMasterSlave/images/image4.png)


    -Añadimos las acl confiables y le decimos que permitimos  la transferencia de archivos de esas acl y además le decimos que no permitimos ipv6
![alt text](/PracticaSistemaTestMasterSlave/images/image5.png)


    -Añadimos las zonas tanto de MASTER como de ESCLAVO
![alt text](/PracticaSistemaTestMasterSlave/images/image6.png)
![alt text](/PracticaSistemaTestMasterSlave/images/image7.png)


    -Configuramos las zonas tanto la directa como la inversa del servidor
![alt text](/PracticaSistemaTestMasterSlave/images/image8.png)
![alt text](/PracticaSistemaTestMasterSlave/images/image9.png)


4. Una vez comprobado todos los archivos y hechas las pruebas correspondientes para ver que el servidor funciona correctamente hacemos el commit final y subimos los cambios al repositorio de github
