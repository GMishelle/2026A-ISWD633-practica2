## Esquema para el ejercicio
![Imagen](esquema-4-ejercicio.PNG)

### Crear la red

<img width="631" height="47" alt="image" src="https://github.com/user-attachments/assets/7cd8bd80-33e7-4b90-864b-ed7a361bed2f" />

### Crear el contenedor mysql a partir de la imagen mysql:8, configurar las variables de entorno necesarias

docker run -d --name mysql-wp --network net-wp -e MYSQL_ROOT_PASSWORD=1234 -e MYSQL_DATABASE=wordpress -e MYSQL_USER=wpuser -e MYSQL_PASSWORD=wp1234 mysql:8

<img width="1345" height="295" alt="image" src="https://github.com/user-attachments/assets/9abc71a2-7f52-4c75-b048-528844cc4dff" />


### Crear el contenedor wordpress a partir de la imagen: wordpress, configurar las variables de entorno necesarias

docker run -d --name wordpress-wp --network net-wp -e WORDPRESS_DB_HOST=mysql-wp:3306 -e WORDPRESS_DB_USER=wpuser -e WORDPRESS_DB_PASSWORD=wp1234 -e WORDPRESS_DB_NAME=wordpress -p 9300:80 wordpress

<img width="1347" height="526" alt="image" src="https://github.com/user-attachments/assets/162d6be5-249a-4613-8c63-796a0458ec12" />



De acuerdo con el trabajo realizado, en el esquema del ejercicio el puerto a es 9300.

Ingresar desde el navegador al wordpress y finalizar la configuración de instalación.
# COLOCAR UNA CAPTURA DE LA CONFIGURACIÓN

<img width="649" height="650" alt="image" src="https://github.com/user-attachments/assets/1bf37ee5-2bb3-44ce-a8f1-fb321e216fd3" />



<img width="816" height="416" alt="image" src="https://github.com/user-attachments/assets/626cbd7c-ce82-457c-97b1-32575802e873" />

Desde el panel de admin: cambiar el tema y crear una nueva publicación.
Ingresar a: http://localhost:9300/ 
recordar que a es el puerto que usó para el mapeo con wordpress
# COLOCAR UNA CAPTURA DEL SITO EN DONDE SEA VISIBLE LA PUBLICACIÓN.

<img width="1365" height="724" alt="image" src="https://github.com/user-attachments/assets/bf27e1c6-ed65-4b83-b33c-762eeb9e7b85" />


### Eliminar el contenedor wordpress

<img width="744" height="55" alt="image" src="https://github.com/user-attachments/assets/ac91992c-b3b7-4a7b-93c5-56b4515abce4" />


### Crear nuevamente el contenedor wordpress
Ingresar a: http://localhost:9300/ 
recordar que a es el puerto que usó para el mapeo con wordpress

### ¿Qué ha sucedido, qué puede observar?
# COMPLETAR

