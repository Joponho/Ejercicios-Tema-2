# Ejercicios6-11
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
*Hola Mundo* en C.
## Ejecutar el programa
1. Creamos un archivo de texto llamado **HolaMundo.c** y escribimos el código:
~~~
#include <stdio.h>
int main
{
printf("Hola Mundo");
return 0;
}
~~~
2. Compilamos y enlazamos:
~~~
gcc -o HolaMundo HolaMundo.c
~~~
3. Abrimos el intérprete y ejecutamos el programa:
~~~
gcc ./Holamundo
~~~
< También podemos ejecutarlo sin abrir el programa.
---
# C++
*Hola Mundo* en C++.
## Ejecutar el programa
1. Creamos un archivo de texto llamado **HolaMundo.cpp** y escribimos el código:
~~~
#include <iostream>
using namespace std;
int main()
{
cout << "Hola Mundo" << endl;
return 0;
}
~~~
2. Compilamos y enlazamos:
~~~
g++ -o HolaMundo Holamundo.cpp
~~~
3. Abrimos el intérprete y ejecutamos el programa:
~~~
g++ ./Holamundo
~~~
< También podemos ejecutarlo sin abrir el intérprete.
---
# Java
*Hola Mundo* en Javascript(nodejs).
Para abrir el interpetre de **Java** y poder probar el *"Hola Mundo"* tenemos que escribir en la terminal:
~~~
class HolaMundo
{
 public static void main (String[] args)
 {
  System.out.println("Hola Mundo");
 }
}
~~~
Para probar el programa escribimos:
~~~
javac HolaMundo.javac
~~~
Para probar el programa escribimos:
~~~
java HolaMundo
~~~
> Nota: A la hora de ejecutar el programa tenemos que escribir el nombre de la clase para que se ejecute.
>CTRL + D para salir del intérprete.
## Ejecutar el programa
1. Creamos un archivo de texto llamado **HolaMundo.java** y escribimos el código:
~~~
class HolaMundo
{
    public static void main(String[] args) {
        System.out.println("Hola Mundo");
    }
}
~~~
2. Le damos los permisos al programa:
~~~
chmod +x HolaMundo.java
~~~
3. Abrimos el intérprete y ejecutamos el programa:
~~~
node ./Holamundo.java
~~~
---
# Esamblador(nasm)
*Hola Mundo* en Javascript(nodejs).
Para abrir el interpetre de **Esamblador(nasm)** y poder probar el *"Hola Mundo"* tenemos que escribir en la terminal:
~~~
node
~~~
Para probar el programa escribimos:
~~~
console.log('Hola Mundo');
~~~
>CTRL + D para salir del intérprete.
## Ejecutar el programa
1. Creamos un archivo de texto llamado **HolaMundo.asm** y escribimos el código:
~~~
console.log('Hola Mundo');
~~~
2. Le damos los permisos al programa:
~~~
chmod +x HolaMundo.asm
~~~
3. Abrimos el intérprete y ejecutamos el programa:
~~~
node ./Holamundo.asm
~~~
---
# Ruby
*Hola Mundo* en Javascript(nodejs).
Para abrir el interpetre de **Ruby** y poder probar el *"Hola Mundo"* tenemos que escribir en la terminal:
~~~
node
~~~
Para probar el programa escribimos:
~~~
console.log('Hola Mundo');
~~~
>CTRL + D para salir del intérprete.
## Ejecutar el programa
1. Creamos un archivo de texto llamado **HolaMundo.rb** y escribimos el código:
~~~
console.log('Hola Mundo');
~~~
2. Le damos los permisos al programa:
~~~
chmod +x HolaMundo.rb
~~~
3. Abrimos el intérprete y ejecutamos el programa:
~~~
node ./Holamundo.rb
~~~
---
# Go
*Hola Mundo* en Javascript(nodejs).
Para abrir el interpetre de **Go** y poder probar el *"Hola Mundo"* tenemos que escribir en la terminal:
~~~
node
~~~
Para probar el programa escribimos:
~~~
console.log('Hola Mundo');
~~~
>CTRL + D para salir del intérprete.
## Ejecutar el programa
1. Creamos un archivo de texto llamado **HolaMundo.go** y escribimos el código:
~~~
console.log('Hola Mundo');
~~~
2. Le damos los permisos al programa:
~~~
chmod +x HolaMundo.go
~~~
3. Abrimos el intérprete y ejecutamos el programa:
~~~
node ./Holamundo.go
~~~
---
# Rust
*Hola Mundo* en Javascript(nodejs).
Para abrir el interpetre de **Rust** y poder probar el *"Hola Mundo"* tenemos que escribir en la terminal:
~~~
node
~~~
Para probar el programa escribimos:
~~~
console.log('Hola Mundo');
~~~
>CTRL + D para salir del intérprete.
## Ejecutar el programa
1. Creamos un archivo de texto llamado **HolaMundo.rs** y escribimos el código:
~~~
console.log('Hola Mundo');
~~~
2. Le damos los permisos al programa:
~~~
chmod +x HolaMundo.rs
~~~
3. Abrimos el intérprete y ejecutamos el programa:
~~~
node ./Holamundo.rs
~~~
---
# Lisp
*Hola Mundo* en Javascript(nodejs).
Para abrir el interpetre de **Lisp** y poder probar el *"Hola Mundo"* tenemos que escribir en la terminal:
~~~
node
~~~
Para probar el programa escribimos:
~~~
console.log('Hola Mundo');
~~~
>CTRL + D para salir del intérprete.
## Ejecutar el programa
1. Creamos un archivo de texto llamado **HolaMundo.lisp** y escribimos el código:
~~~
console.log('Hola Mundo');
~~~
2. Le damos los permisos al programa:
~~~
chmod +x HolaMundo.lisp
~~~
3. Abrimos el intérprete y ejecutamos el programa:
~~~
node ./Holamundo.lisp
~~~
