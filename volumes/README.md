# Docker Volumes – Ejemplo Simple

Este ejemplo muestra que un volumen guarda datos
aunque el contenedor se elimine.

## Comandos ejecutados (consola)

Crear un archivo dentro del volumen:

```bash
docker run --name contenedor-volumes \
  -v volumen-uno:/data \
  flor/portfolio:1.1 \
  sh -c "echo 'hola volumes' > /data/file.txt"
Una vez que el contenedor se elimina,
los datos creados dentro de la ruta /data
siguen existiendo porque pertenecen al volumen.

Para comprobarlo, se creó un contenedor temporal:

en consola : docker run --rm -it -v volumen-uno:/data alpine sh

Dentro del contenedor:

ls /data
cat /data/file.txt 


Salida esperada:

hola volumes
