# Docker

## Comandos para docker:

- Crear imagen: _docker build -t myapp:v1_
- Listar imagenes: _docker images_
- Listar contenedores: _docker ps_
- Listar contenedores con detalle: _docker ps -a_
- Detener contenedores: _docker stop containerId_
- Eliminar imagenes: _docker rm repositoryName_
- Eliminar contenedores: _docker container rm tagName_
- ELIMINAR TODO: _docker system prune -a_

### Siempre crea un nuevo contenedor incluyendo nuevos cambios

- Correr imagen modo proceso: _docker run --name myapp_c -p 4000:4000 myapp:v1_

### Corre la imagen apartir del contenedor creado

- Correr imagen: _docker start NAME_
- Correr imagen: _docker start -i NAME_

### Volumes

Sirven para mapear el contenedor sin tener que recontruir la imagen con ayuda de nodemon

- Crear contenedor y eliminarlo cuando se baje o ya no se use, solo para desarrollo: _docker run --name myapp_c_nodemon -p 4000:4000 --rm myapp:nodemon_
- Crear contenedor mapeado con local Volumenes: _docker run --name myapp_c_nodemon -p 4000:4000 --rm -v C:\Users\JLMEI\Documents\Programacion\Docker\api:/app myapp:nodemon_
- Incluyendo nodemodules para volumen: _docker run --name myapp_c_nodemon -p 4000:4000 --rm -v C:\Users\JLMEI\Documents\Programacion\Docker\api:/app -v /app/node_modules myapp:nodemon_

### Docker compose

Conectar diferentes contenedores entre ellos

- Crear contenedor con .yaml: _docker-compose up_
- Detener y eliminar contenedor: _docker-compose down_
- Detener y eliminar todos los contenedores e imagenes: _docker-compose down --rmi all -v_
