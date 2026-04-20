# Redes

Las redes son un componente fundamental que permite la comunicación entre contenedores, así como la comunicación de los contenedores con el mundo exterior.


![Imagen](redes.PNG)

* Bridge: Esta es la red por defecto en Docker. Permite la comunicación entre contenedores en el mismo host. Cada contenedor conectado a la red bridge tiene una IP propia en la subred de la red bridge.

  * Brige por default: Cuando se ejecuta un contenedor, Docker crea automáticamente una red de tipo bridge por default. Esta red se utiliza para permitir la comunicación entre contenedores en el mismo host. Cada contenedor conectado a esta red obtiene su propia dirección IP en la subred de la red bridge.
  * Bridge creada por nosotros: Un usuario también puede crear sus propias redes de tipo bridge en Docker. Esto puede ser útil para organizar y segmentar los contenedores de una aplicación de manera más controlada. Al crear una red bridge personalizada, se puede especificar un rango de direcciones IP y otras configuraciones de red específicas. Los contenedores conectados a esta red utilizarán las direcciones IP de la subred definida por el usuario.
* Host: Con esta red, los contenedores comparten la red del host en lugar de tener su propia interfaz de red. Esto puede mejorar el rendimiento de red, pero los contenedores pueden entrar en conflicto con los puertos del host si intentan utilizar los mismos puertos.
* None: Con esta red, se deshabilita la configuración de red. Los contenedores que usan esta red tienen su propia red de loopback y no pueden comunicarse con otros contenedores a menos que se conecten explícitamente a una red.

### Crear una red de tipo bridge

```
docker network create <nombre red> -d bridge
```

### Crear un contenedor vinculado a una red

```
docker run -d --name <nombre contenedor> --network <nombre red> <nombre imagen>
```

### Para saber a qué red está conectado un contenedor

```
docker inspect <nombre contenedor>
```

ó

```
docker network inspect <nombre red> 
```

### Vincular contenedor a una red

```
docker network connect <nombre red> <nombre contenedor>
```

### Para desvincular un contenedor de una red

```
docker network disconnect <nombre red> <nombre contenedor>
```

### Para listar las redes existentes

```
docker network ls
```

### Crear los contenedores y las redes que se presentan en el esquema. Usar para todos los contenedores la imagen de nginx:alpine

![Imagen](esquema-ejercicio-redes.PNG)

# COLOCAR UNA CAPTURA DE LAS REDES EXISTENTES CREADAS

<img width="601" height="249" alt="image" src="https://github.com/user-attachments/assets/c930efef-7a48-493e-8299-520aca70fadc" />


# COLOCAR UNA(S) CAPTURAS(S) DE LOS CONTENEDORES CREADOS EN DONDE SE EVIDENCIE A QUÉ RED ESTÁN VINCULADOS

docker network inspect net-curso01

<img width="782" height="732" alt="image" src="https://github.com/user-attachments/assets/90dd305d-b8e6-4678-8b63-0e9257c3a2f9" />
<img width="779" height="353" alt="image" src="https://github.com/user-attachments/assets/4bb5438e-49b1-42f7-8de5-e670b0f2ad9d" />

docker network inspect net-curso02

<img width="777" height="715" alt="image" src="https://github.com/user-attachments/assets/a4b3a7fd-f89f-4c26-999a-d8f03c5e4982" />
<img width="778" height="262" alt="image" src="https://github.com/user-attachments/assets/e4ed0908-1bdb-45c6-ba48-825249d1a062" />

### Para eliminar las redes creadas

```
docker network rm <nombre de la red>
```

