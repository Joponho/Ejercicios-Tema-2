# Bibliotecas
## Define qué se entiende por biblioteca o librería y los tipos que existen.
Las bibliotacas son espacios dpnde se guardan archivos que posteriormente utilizan los programadores para ejecutar un programa. Hay diferentipos de bibliotecas; estas se usan dependiendo del programa o aplicación que se busque desarollar.

Los diferentes tipos de bibliotecas son:
- **Las bibliotecas estáticas**, son ficheros que contienen varios archivos de código objeto en su interior que se utilizan en los ficheros ejecutables, copiándolos y relocalizando según la necesidad. En este caso la biblioteca actúa como recipiente de archivos.
- **Las bibliotecas dinámicas**, son archivos que tienen código objeto que se construye de manera independiente a su ubicación. Esto nos indica que este tipo de bibliotecas se utilizan cargando los archivos en el tiempo de ejecución y no se enlazan en el tiempo de compilación.
- **Las bibliotecas remota**, se utiliza en ejecutables separados y por medio de un procedimiento reomoto. Estas bibliotecas trabajan con un enfoque que maximiza la reutilización del sistema operativo; el código que soporta la biblioteca es el que le da a la aplicación el soporte y seguridad para otro programa.

## Busca información y explica las ventajas y desventajas de usar bibliotecas estáticas.
### Ventajas de las bibliotecas estáticas:
- Es una biblioteca de carga rápida.
- Las actualizaciones de las bibliotecas no le afectan.
- El programa es autocontenido.

### Desventajas de la bibliotecas dinámicas:
- La biblioteca está empaquetada en la aplicación, lo que resulta en un gran tamaño de biblioteca.
- Si la biblioteca cambia es necesario volver a complar el programa.

## Busca información y explica las ventajas y desventajas de usar bibliotecas dinámicas.
### Ventajas de las bibliotecas dinámicas:
- Ahorra más memoria y reduce el intercambio de páginas.
- Es adecuado para el desarrollo de software a gran escala, lo que hace que el proceso de desarrollo sea independiente y menos acoplado, lo que es conveniente para el desarrollo y las pruebas entre diferentes desarrolladores y organizaciones de desarrollo.
- El programa se beneficia de las actualizaciones de la biblioteca.
- El archivo .so es independiente del archivo .EXE, siempre que la interfaz de salida permanezca igual, reemplazar el archivo .so no causará ningun daño al archivo .EXE, mejorando así la capacidad de mantenimiento y la escalabilidad de este.

### Desventajas  de las bibliotecas dinámicas:
- Las actualizaciones de la biblioteca le afectan para bien y para mal.
- El programa no es autocontenido.

 ## Crea una biblioteca dinámica en C que proporcione las funciones para sumar, restar, multiplicar y dividir 2 números enteros. Crea un programa que haga uso de ella y comprueba que se ejecuta correctamente.
 

