# Ejercicios de deshacer cambios

Para hacer estos ejercicios es necesario haber hecho antes los ejercicios sobre historial de cambios

## Ejercicio 1

1. Eliminar la última línea del fichero **indice.txt** y guardarlo.
2. Comprobar el estado del repositorio.
3. Deshacer los cambios realizados en el fichero **indice.txt** para volver a la versión anterior del fichero.
4. Volver a comprobar el estado del repositorio.

~~~
cd "directorio donde este indice.txt"
gedit indice.txt
git status
git checkout indice.txt
git status
~~~

## Ejercicio 2

1. Eliminar la última línea del fichero **indice.txt** y guardarlo.
2. Añadir los cambios a la zona de intercambio temporal.
3. Comprobar de nuevo el estado del repositorio.
4. Quitar los cambios de la zona de intercambio temporal, pero mantenerlos en el directorio de trabajo.
5. Comprobar de nuevo el estado del repositorio.
6. Deshacer los cambios realizados en el fichero **indice.txt** para volver a la versión anterior del fichero.
7. Volver a comprobar el estado del repositorio.

~~~
cd "directorio donde este indice.txt"
gedit indice.txt
git add .
git status
git reset
git status
git checkout .
git status
~~~

## Ejercicio 3

1. Eliminar la última línea del fichero **indice.txt** y guardarlo.
2. Eliminar el fichero **capitulos/capitulo3.txt**.
3. Añadir un fichero nuevo **capitulos/capitulo4.txt** vacío.
4. Añadir los cambios a la zona de intercambio temporal.
5. Comprobar de nuevo el estado del repositorio.
6. Quitar los cambios de la zona de intercambio temporal, pero mantenerlos en el directorio de trabajo.
7. Comprobar de nuevo el estado del repositorio.
8. Deshacer los cambios realizados para volver a la versión del repositorio.
9. Volver a comprobar el estado del repositorio.

~~~
cd "directorio donde este indice.txt"
gedit indice.txt
git clean -n capitulos/capitulo3.txt
git clean -f capitulos/capitulo3.txt (git clean es parecido a reset y checkout, solo que en vez de deshacer cambios en la zona temporal, git clean actua en el directorio de trabajo, la opcion -n te dice que vas a borrar y con -f lo borras)
touch capitulos/capitulo4.txt
git add .
git status
git reset
git status
git checkout .
git status
~~~

## Ejercicio 4

1. Eliminar la última línea del fichero **indice.txt** y guardarlo. 
2. Eliminar el fichero **capitulos/capitulo3.txt**.
3. Añadir los cambios a la zona de intercambio temporal y hacer un commit con el mensaje “Borrado accidental.” 
4. Comprobar el historial del repositorio. 
5. Deshacer el último commit pero mantener los cambios anteriores en el directorio de trabajo y la zona de intercambio temporal. 
6. Comprobar el historial y el estado del repositorio. 
7. Volver a hacer el commit con el mismo mensaje de antes. 
8. Deshacer el último commit y los cambios anteriores del directorio de trabajo volviendo a la versión anterior del repositorio.
9. Comprobar de nuevo el historial y el estado del repositorio.

~~~
gedit indice.txt
git clean -n capitulos/capitulo3.txt
git clean -f capitulos/capitulo3.txt
git add .
git commit -m "“Borrado accidental."
git log
git log --oneline
copiamos el hash del commit anterior a "Borrado accidental."
git reset "Aqui ponemos el hash que acabamos de copiar, pero sin las comillas"
git log --oneline
git status
git add .
git commit -m "Borrado accidental."
git reset --hard
git log --oneline
git status
~~~
