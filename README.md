# Repo para EIEC - DevOps - UNIR

Este repositorio nos servirá para demostrar el uso de Git en la asignatura de EIEC y muchas cosas mas.

---

Los comandos del Makefile funcionarán en Linux y MacOS. En caso de usar Windows, necesitarás adaptarlos o ejecutarlos en una máquina virtual Linux.

## Ejecución

python3 main.py <filename> <dup>
  filename: **ruta** al fichero que contiene la lista de palabras, una por línea
  dup: **yes|no**, yes para eliminar palabras duplicadas, no para mantener la lista

1.- Crea un archivo words.txt en el mismo directorio con el siguiente contenido:
gryffindor
slytherin
hufflepuff
ravenclaw
gryffindor
hufflepuff

2.- Ejecuta el siguiente comando para ordenar las palabras y eliminar duplicados:
make run

3.- Esto ejecutará el siguiente comando Docker que está definido en el Makefile:
docker run --rm --volume `pwd`:/opt/app --env PYTHON_PATH=/opt/app -w /opt/app python:3.6-slim python3 main.py words.txt yes
El resultado será:

4.- Se leerán las palabras del fichero words.txt
['gryffindor', 'hufflepuff', 'ravenclaw', 'slytherin']