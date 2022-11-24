# ¿Qué extensión tienen los archivos de código objeto?

## Lenguaje C. Código en varios archivos. Obtener el código objeto a partir del código fuente de los 3 archivos siguientes:

1. Primero tenemos que crear los archivos, empezaremos con el *main.c*:
~~~~
nano main.c
~~~~
2. Le añadimos el código fuente al *main.c*:
~~~~
#include <stdio.h>
int suma (int a, int b);
extern char *mensaje;
extern int num1, num2;
int main(){
printf("%s\n", mensaje);
printf("%d\n", suma (num1, num2) );
return 0;
}
~~~~
3. Guardamos el main.c y creamos el siguiente que va a ser *suma.c*:
~~~~
nano suma.c
~~~~
4. Le añadimos el código fuente a la *suma.c*:
~~~~
int suma (int a, int b) {
return a + b;
}
~~~~
5. Guardamos la suma.c y creamos el último archivo *datos.c*:
~~~~
nano datos.c
~~~~
6. Le añadimos el código fuente a *datos.c*:
~~~~
char *mensaje="Hola a todos y todas";
int num1 = 8;
int num2 = 10;
~~~~
7. Guardamos y compilamos los tres para obtener el código.
Lo hacemos de la siguiente manera:
~~~~
gcc -c main.c suma.c datos.c
~~~~
**Deberemos obtener 3 archivos: main.o, suma.o y datos.o**

# Lenguaje C. Código en varios archivos. Obtener el código binario ejecutable a partir del código objeto de los 3 archivos anteriores:
~~~~
gcc -o program main.o datos.o suma.o
~~~~

## Deberemos obtener un archivo programa binario ejecutable. Si lo ejecutamos obtenemos el siguiente resultado:
~~~~
./program
~~~~
~~~~
Hola a todos y todas
18
~~~~

> Nota: Obtenemos el "Hola a todos y todas porque está declarado en datos.

> Nota: Obtenemos el 18 porque en datos está declarado num1=8 y num2=10 y en suma que es una función que dice que *a *y b se suman y en el main se llama a la función suma y se declara que a es num1 y b es num2 lo que da por resultado 18.
