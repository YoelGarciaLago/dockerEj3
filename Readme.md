## Descarga la imagen 'httpd' y comprueba que está en tu equipo.
sudo docker pull httpd (para descargarla)
sudo docker images (para verlas)

## Crea un contenedor con el nombre 'dam_web1'.
sudo docker run -it --name dam_web1 httpd

## Si quieres poder acceder desde el navegador de tu equipo, ¿que debes hacer?
Borrar el contenedor de docker, y ejecutar el siguiente comando:
sudo docker run -it -p 80:80 --name dam_web1 httpd

## Utiliza bind mount para que el directorio del apache2 'htdocs' esté montado un directorio que tu elijas.
sudo docker run -d --name dam_web1 -p 8080:80 -v /home/accesodatos/Escritorio/wawa:/usr/local/apache2/htdocs httpd:2.4

## Realiza un 'hola mundo' en html y comprueba que accedes desde el navegador.


## Crea otro contenedor 'dam_web2' con el mismo bind mount y a otro puerto, por ejemplo 9080.
sudo docker run -d --name dam_web2 -p 9080:80 -v /home/accesodatos/Escritorio/wawa:/usr/local/apache2/htdocs httpd:2.4

## Comprueba que los dos servidores 'sirven' la misma página, es decir, cuando consultamos en el navegador:
        http://localhost:9080 
        http://localhost:8000
Se pueden ver las dos direcciones en el navegador.

## Realiza modificaciones de la página y comprueba que los dos servidores 'sirven' la misma página
Los servidores sirven
