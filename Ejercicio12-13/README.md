# ¿Qué extensión tienen los archivos de código objeto?

## Lenguaje C. Código en varios archivos. Obtener el código objeto a partir del código fuente de los 3 archivos siguientes:

Primero tenemos que crear los archivos, empezaremos con el *main.c*:
~~~~
nano main.c
~~~~
Le añadimos el código fuente al *main.c*:
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
Guardamos el main.c y creamos el siguiente que va a ser *suma.c*:
~~~~
nano suma.c
~~~~
Le añadimos el código fuente a la *suma.c*:
~~~~
int suma (int a, int b) {
return a + b;
}
~~~~
Guardamos la suma.c y creamos el último archivo *datos.c*:
~~~~
nano datos.c
~~~~
Le añadimos el código fuente a *datos.c*:
~~~~
char *mensaje="Hola a todos y todas";
int num1 = 8;
int num2 = 10;
~~~~
Guardamos y compilamos los tres para obtener el código.
Lo hacemos de la siguiente manera:
~~~~
gcc -c main.c suma.c datos.c
~~~~
**Deberemos obtener 3 archivos: main.o, suma.o y datos.o**
