# Ejercicios6-11
---
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
*"Hola Mundo"* en Bash.

La máquina virtual con la que trabajamos interpreta bash, por ello no debemos descargar ningún añadido para que pueda interpretar bash.

Escribimos y ejecutamos el código para comprobar que es correcto.
~~~
echo "Hola Mundo"
~~~

## Script ejecutable
1. Creamos un archivo **.sh** donde irá el código de *"Hola Mundo"*.
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
*"Hola Mundo"* en Python.

Para abrir el intérperte de **Python** y probar el *"Hola Mundo"* tenemos escribir en la terminal
~~~
python3
~~~

Luego escribimos el programa para probarlo:
~~~
print("Hola Mundo")
~~~
>CTRL + D para salir del intérprete.


## Script ejecutable
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
*"Hola Mundo"* en PHP.
Para abrir el interpetre de **PHP** y poder probar el *"Hola Mundo"* tenemos que escribir en la terminal:
~~~
php -a
~~~
Para probar el programa escribimos:
~~~
echo "Hola Mundo";
~~~
>CTRL + D para salir del intérprete.
## Script ejecutable
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
*"Hola Mundo"* en Javascript(nodejs).
Para abrir el interpetre de **Javascript(nodejs)** y poder probar el *"Hola Mundo"* tenemos que escribir en la terminal:
~~~
node
~~~
Para probar el programa escribimos:
~~~
console.log('Hola Mundo');
~~~
>CTRL + D para salir del intérprete.
## Script ejecutable
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
*"Hola Mundo"* en C.
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
*"Hola Mundo"* en Javascript(nodejs).
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
## Script ejecutable
Realmente no es un script, si no un bytecode empaquetado en JAR
1. Empaquetamos:
~~~~
jar  cvfe  hola.jar  Hola  Hola.class
~~~~
> Nota: De forma habitual se suele ejecutar un archivo .jar de la siguiente forma.
> ~~~~
>java  -jar   hola.jar
>~~~~
2. Damos permiso de ejecución:
~~~~
chmod  +x  hola.jar
~~~~
3. Ejecutamos:
~~~
./hola.jar
~~~
---
# Esamblador(nasm)
*"Hola Mundo"* en Esamblador(nasm).
## Ejecutar el programa
1. Creamos un archivo de texto llamado **HolaMundo.asm** y escribimos el código:
~~~
 section .data
 
 msg     db "¡Hola Mundo!", 0Ah
 len     equ     $ - msg  
 
 section .text
 
 global _start
 
 _start:
        mov     eax, 04h
        mov     ebx, 01h
        mov     ecx, msg
        mov     edx, len
        int     80h
        mov     eax, 01h
        mov     ebx, 00h
        int     80h
~~~
2. Ensamblamos y enlazamos:
~~~
nasm  -f  elf64  hola.asm   
~~~
> Nota: Ensamblado
> Nota: Nos entrega un archivo en código objeo.
~~~~
ld  hola.o  -o  hola       
~~~~
> Nota: Enlazado
3. Ejecutamos el programa:
~~~
./hola
~~~
---
# Ruby
*"Hola Mundo"* en Javascript(nodejs).
Para abrir el interpetre de **Ruby** y poder probar el *"Hola Mundo"* tenemos que escribir en la terminal:
~~~
ruby
~~~
Para probar el programa escribimos:
~~~
print "Hola Mundo"
~~~
o
~~~~
puts "Hola Mundo"
~~~~
>CTRL + D para salir del intérprete.
## Script ejecutable
1. Creamos un archivo de texto llamado **HolaMundo.rb** y escribimos el código:
~~~
print "Hola Mundo
~~~
2. Le damos los permisos al programa:
~~~
chmod +x HolaMundo.rb
~~~
3. Abrimos el intérprete y ejecutamos el programa:
~~~
ruby ./Holamundo.rb
~~~
4. También nos podemos saltar el paso dos y hacer:
~~~~
ruby HolaMundo.rb
~~~~
5. Incluso podemos cambiar el código y poner:
~~~~
#!/usr/bin/env ruby
puts "Hola Mundo"
~~~~
6. Le damos los permisos:
~~~~
chmod +x HolaMundo.rb
~~~~
7. Ejecutamos el programa:
~~~
./Holamundo.rb
~~~
---
# Go
*"Hola Mundo"* en Javascript(nodejs).
## Script ejecutable
1. Creamos un archivo de texto llamado **HolaMundo.go** y escribimos el código:
~~~
package main

import "fmt"

func main() {
        fmt.Println("Hola mundo desde Go")
}
~~~
2. Compilamos y enlazamos:
~~~
go  build  hola.go
~~~
3. Abrimos el intérprete y ejecutamos el programa:
~~~
./Holamundo
~~~
4. También podemos interpretar el código y ejecutarlos:
~~~~
go  run  hola.go
~~~~
---
# Rust
*"Hola Mund"o* en Javascript(nodejs).
## Script ejecutable
1. Creamos un archivo de texto llamado **HolaMundo.rs** y escribimos el código:
~~~
fn main() {
    println!("¡Hola, mundo! Desde RUST ");
}
~~~
2. Compilamos y enlazamos:
~~~
rustc  hola.rs 
~~~
3. Ejecutamos el programa:
~~~
./Holamundo
~~~
---
# Lisp
*"Hola Mundo"* en Javascript(nodejs).
Para abrir el interpetre de **Lisp** y poder probar el *"Hola Mundo"* tenemos que escribir en la terminal:
~~~
node
~~~
Para probar el programa escribimos:
~~~
console.log('Hola Mundo');
~~~
>CTRL + D para salir del intérprete.
## Script ejecutable
1. Creamos un archivo de texto llamado **HolaMundo.lisp** y escribimos el código:
~~~
#!/usr/bin/env clisp
(format t "¡Hola, mundo!")
~~~
> Nota: Si no escribimos el *#!/usr/bin/env clisp* el programa no funcionará.
2. Le damos los permisos al programa:
~~~
chmod +x HolaMundo.lisp
~~~
3. Ejecutamos el programa:
~~~
./Holamundo.lisp
~~~
