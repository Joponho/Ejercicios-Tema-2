# Ejecuta el programa "Hola mundo" en los siguientes lenguajes:
En este documento especficaré las distintas formas de hacer el *"Hola Mundo"* en distintos lenguajes.

Utilize una máquina virtual en la que trabaje con **Linux**.

Los lenguajes utilizados son:
- Bash
- Python
- PHP
- Javascript (nodejs)
- C
- C++
- Java
- Ensamblador (nasm)
- Ruby
- Go
- Rust
- Lisp

Para poder instalar los paquetes de los anteriores lenguajes debes hacer un:
~~~
sudo apt-get update
~~~
Luego ya puedes instalar los paquetes de la siguinte forma:
 
    sudo apt-get install python3.6  php  nodejs  gcc  g++  openjdk-8-jdk  ruby  golang  rustc  clisp nasm
 
 ---
# Bash
*Hola Mundo* en Bash.

La máquina virtual con la que trabajamos interpreta bash, por ello no debemos descargar ningún añadido para que pueda interpretar bash.

Escribimos y ejecutamos el código para comprobar que es correcto.
~~~
echo "Hola Mundo"
~~~

## Ejecutar el programa
1. Creamos un archivo **.sh** donde irá el código de *Hola Mundo*.
~~~
cat > HolaMundo.sh
echo "Hola Mundo"
~~~
>CTRL + D para salir del cat.
2. Damos lo permisos de ejecución al archivo *HolaMundo.sh*
~~~
chmod +x HolaMundo.sh
~~~
3. Ejecutamos el programa
~~~
./HolaMundo.sh
~~~
---
# Python
*Hola Mundo* en Python.

Para abrir el intérperte de **Python** y probar el *"Hola Mundo"* tenemos escribir en la terminal
~~~
python3
~~~

Luego escribimos el programa para probarlo:
~~~
print("Hola Mundo")
~~~
>CTRL + D para salir del intérprete.


## Ejecutar el programa
1. Creamos un archivo de texto llamado **HolaMundo.py** y escribimos el código:
~~~
cat > HolaMundo.py

print("Hola Mundo")
~~~
2. Le damos los permisos al programa:
~~~
chmod +x HolaMundo.py
~~~
3. Abrimos el interprete y ejecutamos el programa:
~~~
python3 ./HolaMundo.py
~~~
---
# PHP
*Hola Mundo* en PHP.
Para abrir el interpetre de **PHP** y poder probar el *"Hola Mundo"* tenemos que escribir en la terminal:
~~~
php -a
~~~
Para probar el programa escribimos:
~~~
echo "Hola Mundo";
~~~
>CTRL + D para salir del intérprete.
## Ejecutar el programa
1. Creamos un archivo de texto llamado **HolaMundo.php** y escribimos el código:
~~~
<?php 
  echo "Hola mundo"; 
?>
~~~
2. Le damos los permisos al programa:
~~~
chmod +x HolaMundo.php
~~~
3. Abrimos el intérprete y ejecutamos el programa:
~~~
php ./Holamundo.php
~~~

---
# Javascript(nodejs)
*Hola Mundo* en Javascript(nodejs).
Para abrir el interpetre de **Javascript(nodejs)** y poder probar el *"Hola Mundo"* tenemos que escribir en la terminal:
~~~
node
~~~
Para probar el programa escribimos:
~~~
console.log('Hola Mundo');
~~~
>CTRL + D para salir del intérprete.
## Ejecutar el programa
1. Creamos un archivo de texto llamado **HolaMundo.js** y escribimos el código:
~~~
console.log('Hola Mundo');
~~~
2. Le damos los permisos al programa:
~~~
chmod +x HolaMundo.js
~~~
3. Abrimos el intérprete y ejecutamos el programa:
~~~
node ./Holamundo.js
~~~
---
# C
*Hola Mundo* en Javascript(nodejs).
Para abrir el interpetre de **C** y poder probar el *"Hola Mundo"* tenemos que escribir en la terminal:
~~~
gcc
~~~
Para probar el programa escribimos:
~~~
console.log('Hola Mundo');
~~~
>CTRL + D para salir del intérprete.
## Ejecutar el programa
1. Creamos un archivo de texto llamado **HolaMundo.c** y escribimos el código:
~~~
console.log('Hola Mundo');
~~~
2. Le damos los permisos al programa:
~~~
chmod +x HolaMundo.c
~~~
3. Abrimos el intérprete y ejecutamos el programa:
~~~
gcc ./Holamundo.c
~~~
---
# C++
*Hola Mundo* en Javascript(nodejs).
Para abrir el interpetre de **C++** y poder probar el *"Hola Mundo"* tenemos que escribir en la terminal:
~~~
g++
~~~
Para probar el programa escribimos:
~~~
console.log('Hola Mundo');
~~~
>CTRL + D para salir del intérprete.
## Ejecutar el programa
1. Creamos un archivo de texto llamado **HolaMundo.cpp** y escribimos el código:
~~~
console.log('Hola Mundo');
~~~
2. Le damos los permisos al programa:
~~~
chmod +x HolaMundo.cpp
~~~
3. Abrimos el intérprete y ejecutamos el programa:
~~~
g++ ./Holamundo.cpp
~~~
---
# Java
*Hola Mundo* en Javascript(nodejs).
Para abrir el interpetre de **Javascript(nodejs)** y poder probar el *"Hola Mundo"* tenemos que escribir en la terminal:
~~~
node
~~~
Para probar el programa escribimos:
~~~
console.log('Hola Mundo');
~~~
>CTRL + D para salir del intérprete.
## Ejecutar el programa
1. Creamos un archivo de texto llamado **HolaMundo.js** y escribimos el código:
~~~
console.log('Hola Mundo');
~~~
2. Le damos los permisos al programa:
~~~
chmod +x HolaMundo.js
~~~
3. Abrimos el intérprete y ejecutamos el programa:
~~~
node ./Holamundo.js
~~~
---
# Esamblador (nasm)
*Hola Mundo* en Javascript(nodejs).
Para abrir el interpetre de **Javascript(nodejs)** y poder probar el *"Hola Mundo"* tenemos que escribir en la terminal:
~~~
node
~~~
Para probar el programa escribimos:
~~~
console.log('Hola Mundo');
~~~
>CTRL + D para salir del intérprete.
## Ejecutar el programa
1. Creamos un archivo de texto llamado **HolaMundo.js** y escribimos el código:
~~~
console.log('Hola Mundo');
~~~
2. Le damos los permisos al programa:
~~~
chmod +x HolaMundo.js
~~~
3. Abrimos el intérprete y ejecutamos el programa:
~~~
node ./Holamundo.js
~~~
---
# Ruby
*Hola Mundo* en Javascript(nodejs).
Para abrir el interpetre de **Javascript(nodejs)** y poder probar el *"Hola Mundo"* tenemos que escribir en la terminal:
~~~
node
~~~
Para probar el programa escribimos:
~~~
console.log('Hola Mundo');
~~~
>CTRL + D para salir del intérprete.
## Ejecutar el programa
1. Creamos un archivo de texto llamado **HolaMundo.js** y escribimos el código:
~~~
console.log('Hola Mundo');
~~~
2. Le damos los permisos al programa:
~~~
chmod +x HolaMundo.js
~~~
3. Abrimos el intérprete y ejecutamos el programa:
~~~
node ./Holamundo.js
~~~
---
# Go
*Hola Mundo* en Javascript(nodejs).
Para abrir el interpetre de **Javascript(nodejs)** y poder probar el *"Hola Mundo"* tenemos que escribir en la terminal:
~~~
node
~~~
Para probar el programa escribimos:
~~~
console.log('Hola Mundo');
~~~
>CTRL + D para salir del intérprete.
## Ejecutar el programa
1. Creamos un archivo de texto llamado **HolaMundo.js** y escribimos el código:
~~~
console.log('Hola Mundo');
~~~
2. Le damos los permisos al programa:
~~~
chmod +x HolaMundo.js
~~~
3. Abrimos el intérprete y ejecutamos el programa:
~~~
node ./Holamundo.js
~~~
---
# Rust
*Hola Mundo* en Javascript(nodejs).
Para abrir el interpetre de **Javascript(nodejs)** y poder probar el *"Hola Mundo"* tenemos que escribir en la terminal:
~~~
node
~~~
Para probar el programa escribimos:
~~~
console.log('Hola Mundo');
~~~
>CTRL + D para salir del intérprete.
## Ejecutar el programa
1. Creamos un archivo de texto llamado **HolaMundo.js** y escribimos el código:
~~~
console.log('Hola Mundo');
~~~
2. Le damos los permisos al programa:
~~~
chmod +x HolaMundo.js
~~~
3. Abrimos el intérprete y ejecutamos el programa:
~~~
node ./Holamundo.js
~~~
---
# Lisp
*Hola Mundo* en Javascript(nodejs).
Para abrir el interpetre de **Javascript(nodejs)** y poder probar el *"Hola Mundo"* tenemos que escribir en la terminal:
~~~
node
~~~
Para probar el programa escribimos:
~~~
console.log('Hola Mundo');
~~~
>CTRL + D para salir del intérprete.
## Ejecutar el programa
1. Creamos un archivo de texto llamado **HolaMundo.js** y escribimos el código:
~~~
console.log('Hola Mundo');
~~~
2. Le damos los permisos al programa:
~~~
chmod +x HolaMundo.js
~~~
3. Abrimos el intérprete y ejecutamos el programa:
~~~
node ./Holamundo.js
~~~
