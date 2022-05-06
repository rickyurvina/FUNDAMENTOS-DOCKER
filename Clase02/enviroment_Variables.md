### variables de entorno

### Para crear variables de entorno

```
docker run -d  -e <nombre variable> = <valor>

docker run --rm -it  -e username=rurvina -e password=12345 node:16.15.0-alpine3.14 sh

### crear un contenedor de mongo con variables de entorno
docker run -d --name servermongo -p 27017:27017 -e MONGO_INITDB_ROOT_USERNAME=admin -e MONGO_INITDB_ROOT_PASSWORD=12345  mongo:3.6

