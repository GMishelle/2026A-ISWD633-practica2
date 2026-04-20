
# Mi aprendizaje

Antes de esta práctica, no tenía conocimientos sobre Docker ni sobre cómo funcionan los contenedores. Todo este tema era completamente nuevo para mí.

Después de realizar la práctica, aprendí conceptos importantes, especialmente sobre el manejo de datos confidenciales usando **Docker Secrets**. Entendí que no es correcto guardar contraseñas o claves directamente en el código, y que existen mecanismos más seguros para proteger esta información dentro de los contenedores.

Uno de los principales retos que tuve fue configurar correctamente los secretos, ya que al inicio no funcionaban como esperaba. Sin embargo, al revisar los pasos y practicar varias veces, logré solucionarlo y comprender mejor el proceso.

Comparando mi conocimiento antes y después, considero que avancé bastante, ya que pasé de no saber nada a entender el uso básico de Docker y la importancia de la seguridad en aplicaciones.

Como futura Ingeniera de Software, sé que este aprendizaje me será útil para trabajar con aplicaciones reales, donde la protección de datos y el uso de buenas prácticas son fundamentales.

# Consulta 

## Gestión de datos confidenciales con Docker Secrets

Docker Secrets es una funcionalidad que permite gestionar datos confidenciales de forma segura dentro de contenedores. Se utiliza principalmente para almacenar información sensible como contraseñas, claves API o certificados, evitando que estos datos se expongan en el código fuente o en archivos de configuración.

El funcionamiento de Docker Secrets se basa en almacenar los datos de manera segura y permitir que los contenedores accedan a ellos únicamente cuando es necesario. Estos secretos no se guardan como variables de entorno visibles, sino que se montan dentro del contenedor como archivos temporales, lo que aumenta el nivel de seguridad.

Para utilizar Docker Secrets, primero se debe crear el secreto utilizando un comando específico. Luego, este se asocia a un servicio o contenedor, permitiendo que la aplicación lo lea desde una ruta protegida dentro del sistema.

La principal ventaja de este enfoque es que reduce el riesgo de filtración de información sensible, ya que los datos no quedan expuestos directamente en el código ni en repositorios. Además, facilita la gestión segura en entornos de producción, especialmente en arquitecturas basadas en microservicios y despliegues automatizados.

En conclusión, Docker Secrets es una herramienta clave para aplicar buenas prácticas de seguridad en el desarrollo de software, protegiendo la información crítica de las aplicaciones.
