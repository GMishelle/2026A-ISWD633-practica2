# Variables de Entorno
### ¿Qué son las variables de entorno?

Son valores definidos fuera del código de una aplicación que permiten configurar su comportamiento sin necesidad de modificarlo. Se almacenan como pares clave–valor (por ejemplo, PORT=3000) y hacen posible que un mismo programa funcione en distintos entornos como desarrollo, pruebas o producción.

Son fundamentales en el desarrollo moderno porque ayudan a separar la configuración del código, mejoran la seguridad al manejar datos sensibles (como contraseñas o claves API) y facilitan el despliegue en herramientas como Docker, donde se pueden definir fácilmente al crear un contenedor.


### Para crear un contenedor con variables de entorno

```
docker run -d --name <nombre contenedor> -e <nombre variable1>=<valor1> -e <nombre variable2>=<valor2>
```

### Crear un contenedor a partir de la imagen de nginx:alpine con las siguientes variables de entorno: username y role. Para la variable de entorno rol asignar el valor admin.


# CAPTURA CON LA COMPROBACIÓN DE LA CREACIÓN DE LAS VARIABLES DE ENTORNO DEL CONTENEDOR ANTERIOR

<img width="1061" height="433" alt="image" src="https://github.com/user-attachments/assets/e220132c-9e67-4773-879c-a783867bc2a5" />


### Crear un contenedor con la imagen de mysql, mapear todos los puertos

<img width="775" height="298" alt="image" src="https://github.com/user-attachments/assets/b02f47f7-7a0f-4e07-8160-fe97bb299201" />


### ¿El contenedor se está ejecutando?

<img width="938" height="202" alt="image" src="https://github.com/user-attachments/assets/f9d18c0b-b1bd-4c87-84d5-7c7d2001beed" />


### Identificar el problema

El error surgió porque se intentó levantar un contenedor de MySQL sin especificar la variable obligatoria `MYSQL_ROOT_PASSWORD`, lo que provocó que no pudiera iniciarse correctamente. Para resolverlo, se borró el contenedor anterior y se creó uno nuevo, esta vez asignando una contraseña al usuario root mediante dicha variable, permitiendo así que MySQL arrancara sin inconvenientes.


### Para crear un contenedor con variables de entorno especificadas
- Portabilidad: Las aplicaciones se vuelven más portátiles y pueden ser desplegadas en diferentes entornos (desarrollo, pruebas, producción) simplemente cambiando el archivo de variables de entorno.
- Centralización: Todas las configuraciones importantes se centralizan en un solo lugar, lo que facilita la gestión y auditoría de las configuraciones.
- Consistencia: Asegura que todos los miembros del equipo de desarrollo o los entornos de despliegue utilicen las mismas configuraciones.
- Evitar Exposición en el Código: Mantener variables sensibles como contraseñas, claves API, y tokens fuera del código fuente reduce el riesgo de exposición accidental a través del control de versiones.
- Control de Acceso: Los archivos de variables de entorno pueden ser gestionados con permisos específicos, limitando quién puede ver o modificar la configuración sensible.

### ¿Qué bases de datos existen en el contenedor creado?
# COMPLETAR
