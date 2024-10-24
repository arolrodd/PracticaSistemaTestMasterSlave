# PracticaSistemaTestMasterSlave
Practica de despliegue sobre un servidor dns

1.Creamos la estructura de las maquinas en el archivo de configuración de Vagrantfile
![alt text](/images/image.png)


2.Sacamos los archivos necesarios de la maquina tierra a vagrant y creamos una carpeta file con los archivos
![alt text](/images/image1.png)


3.Configuramos los archivos que hemos sacado a vagrant anteriormente y los añadimos a la configuracion de las maquinas para  que se puedan copiar y ejecutar correctamente, cambiamos la configuración para que solo se escuche por ipv4, configuramos las acl confiables, configuramos las zonas de la maquina esclava y la maestra, configuramos los dos archivos del servidor

![alt text](/images/image3.png)
![alt text](/images/image4.png)
![alt text](/images/images5.png)
![alt text](/images/image6.png)
![alt text](/images/image7.png)
![alt text](/images/image8.png)
![alt text](/images/image9.png)
