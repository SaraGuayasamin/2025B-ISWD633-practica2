## Esquema para el ejercicio
![Imagen](esquema-4-ejercicio.PNG)

### Crear la red
# docker network create net-wp

### Crear el contenedor mysql a partir de la imagen mysql:8, configurar las variables de entorno necesarias
# docker run -d --name cont-mysql --network net-wp -e MYSQL_ROOT_PASSWORD=mi_root_password -e MYSQL_DATABASE=wordpress_db -e MYSQL_USER=wordpress_user -e MYSQL_PASSWORD=mi_wp_password mysql:8

### Crear el contenedor wordpress a partir de la imagen: wordpress, configurar las variables de entorno necesarias
# docker run -d --name cont-wordpress --network net-wp -p 9300:80 -e WORDPRESS_DB_HOST=cont-mysql -e WORDPRESS_DB_NAME=wordpress_db -e WORDPRESS_DB_USER=wordpress_user -e WORDPRESS_DB_PASSWORD=mi_wp_password wordpress

De acuerdo con el trabajo realizado, en el esquema del ejercicio el puerto a es **(completar con el valor)**

Ingresar desde el navegador al wordpress y finalizar la configuración de instalación.
# COLOCAR UNA CAPTURA DE LA CONFIGURACIÓN
<img width="2630" height="1556" alt="image" src="https://github.com/user-attachments/assets/6666eb90-606e-46a8-bec2-76467647d15c" />


Desde el panel de admin: cambiar el tema y crear una nueva publicación.
Ingresar a: http://localhost:9300/ 
recordar que a es el puerto que usó para el mapeo con wordpress
# COLOCAR UNA CAPTURA DEL SITO EN DONDE SEA VISIBLE LA PUBLICACIÓN.
<img width="3114" height="1660" alt="image" src="https://github.com/user-attachments/assets/bff81da9-9a34-45e1-831c-0e512524e17b" />

### Eliminar el contenedor wordpress
# docker rm -f cont-wordpress

### Crear nuevamente el contenedor wordpress
docker run -d --name cont-wordpress-nuevo --network net-wp -p 9300:80 -e WORDPRESS_DB_HOST=cont-mysql -e WORDPRESS_DB_NAME=wordpress_db -e WORDPRESS_DB_USER=wordpress_user -e WORDPRESS_DB_PASSWORD=mi_wp_password wordpress
Ingresar a: http://localhost:9300/ 
recordar que a es el puerto que usó para el mapeo con wordpress

### ¿Qué ha sucedido, qué puede observar?
# Lo que se puede observar es que la instalación de WordPress ya está completa y el sitio web aparece tal como se configuró antes. El tema cambiado y la nueva publicación creada siguen visibles.

