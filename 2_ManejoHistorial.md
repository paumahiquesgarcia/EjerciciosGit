# Ejercicios de manejo del historial de cambios

Para hacer estos ejercicios es necesario haber hecho antes los ejercicios de creación y actualización de repositorios

## Ejercicio 1

1. Mostrar el historial de cambios del repositorio.
2. Crear la carpeta **capitulos** y crear dentro de ella el fichero **capitulo1.txt** con el siguiente texto:

    ![Ejercicio 2.1](imagenes/ejercicio21.png)


3. Git es un sistema de control de versiones ideado por Linus Torvalds.
4. Añadir los cambios a la zona de intercambio temporal.
5. Hacer un commit de los cambios con el mensaje “Añadido capítulo 1.”
6. Volver a mostrar el historial de cambios del repositorio.

~~~
git log
mkdir capitulos
cd capitulos
gedit capitulo1.txt
git add .
git commit -m "Añadido capitulo 1."
git log
~~~

## Ejercicio 2

1. Crear el fichero capitulo2.txt en la carpeta capitulos con el siguiente texto.
   
    ![Ejercicio 2.1.2](imagenes/ejercicio212.png)

1. Añadir los cambios a la zona de intercambio temporal.
2. Hacer un commit de los cambios con el mensaje “Añadido capítulo 2.”
3. Mostrar las diferencias entre la última versión y dos versiones anteriores.

~~~
gedit capitulo2.txt
git add capitulo2.txt
git commit -m "Añadido capítulo 2."
git diff HEAD~2 (Como no se exactamente a que se refiere la pregunta te pongo dos opciones, con este te mostrar el ultimo commit y el antepenultimo, HEAD es el ultimo repositorio)
git log -p -2 (Este te mostrara los 3 ultimos commits))
~~~

## Ejercicio 3

1. Crear el fichero capitulo3.txt en la carpeta capitulos con el siguiente texto.

    ![Ejercicio 2.3.1](imagenes/ejercicio231.png)   

2. Añadir los cambios a la zona de intercambio temporal.
3. Hacer un commit de los cambios con el mensaje “Añadido capítulo 3.”
4. Mostrar las diferencias entre la primera y la última versión del repositorio.

~~~
gedit capitulo3.txt
git add capitulo3.txt
git commit -m "Añadido capitulo 3"
git log indice.txt (Usamos este comando para copiar el ID del primer repositorio)
git diff "ID del primer repositorio"..HEAD (..HEAD te mostrara todos los repositorios hasta HEAD)
~~~

## Ejercicio 4

1. Añadir al final del fichero indice.txt la siguiente línea:

    ![Ejercicio 2.4.1](imagenes/ejercicio241.png)

2. Añadir los cambios a la zona de intercambio temporal.
3. Hacer un commit de los cambios con el mensaje “Añadido capítulo 5 al índice.”
4. Mostrar quién ha hecho cambios sobre el fichero indice.txt.

~~~
cd ..
gedit indice.txt
git add indice.txt
git commit -m "Añadido capitulo 5 al indice."
git log --pretty=format:%an indice.txt
~~~