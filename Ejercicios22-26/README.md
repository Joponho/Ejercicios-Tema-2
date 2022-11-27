# Automatiza el proceso de compilación de ejecutable y biblioteca, su enlazado y la generación del archivo ejecutable para código fuente en C con make. Haz uso de un buildfile.
Para este ejercicio utilizaremos los siguientes archivos:
- main.c
- aritmetica.c
- aritmetica.h
- makefile con su respectivo código.
~~~~
###################################################
#
#  EJEMPLO DE ARCHIVO 	Makefile    (cc0) jamj2000
#
###################################################


###### MACROS

# Compilador de C
CC     = gcc

# Opciones del compilador, en este caso Optimización
CFLAGS = -O

# Directorio de instalación
PREFIX = /usr/local

# Ejecutable resultante
OUTPUT = programa


###### REGLAS

# .PHONY indica objetivos especiales, que no corresponden a archivos
#
# Las reglas tienen la forma
# objetivo(target) : dependencias
# <TAB>	comando1 
# <TAB>	comando2
# <TAB>	...
#
# La primera regla es la regla por defecto, puede invocarse simplemente con la orden make

all: main.o  libaritmetica.so
	$(CC) $(CFLAGS)  -Wl,-rpath=$(PREFIX)/lib  main.o  libaritmetica.so  -o  $(OUTPUT)
.PHONY: all


main.o: main.c  aritmetica.h
	$(CC) $(CFLAGS)  -c  main.c


aritmetica.o: aritmetica.c
	$(CC) $(CFLAGS)  -c  -fPIC  aritmetica.c


libaritmetica.so: aritmetica.o
	$(CC) $(CFLAGS)  -shared  -fPIC  -o  libaritmetica.so  aritmetica.o


clean:
	rm  *.o  *.so  $(OUTPUT)
.PHONY: clean


install: all
	[ -d $(PREFIX) ] || mkdir $(PREFIX)
	[ -d $(PREFIX)/bin ] || mkdir $(PREFIX)/bin
	[ -d $(PREFIX)/lib ] || mkdir $(PREFIX)/lib
	install -m 0755 $(OUTPUT) $(PREFIX)/bin
	install -m 0644 libaritmetica.so $(PREFIX)/lib
.PHONY: install


help:
	@echo "Objetivos válidos para make:"
	@echo ""
	@echo "  all (el objetivo por defecto si no se indica nada)"
	@echo "  clean"
	@echo "  install"
	@echo "  help"
	@echo ""
.PHONY: help
~~~~

1. Lo primero que haremos será ejecutar make:
~~~~
make
~~~~
2. Luego dentro del make ejecutamos todo lo siguiente:
~~~~
gcc -O  -c  main.c
~~~~

~~~~
gcc -O  -c  -fPIC  aritmetica.c
~~~~

~~~~
gcc -O  -shared  -fPIC  -o  libaritmetica.so  aritmetica.o
~~~~

~~~~
gcc -O  -Wl,-rpath=/usr/local/lib  main.o  libaritmetica.so  -o  programa
~~~~
Luego podemos ejecutar:
~~~~
make install
~~~~
> Nota: con esto instalamos la biblioteca y el ejecutable en el sistema.
# Automatiza el proceso de compilación de ejecutable y biblioteca, su enlazado y la generación del archivo .jar para código fuente en Java con Ant. Haz uso de un buildfile.
Para este ejericcio necesitaremos los siguientes programas:
- aritmetica.java
- main.java
- build.xml con su respectivo código:
~~~~
<?xml version="1.0" encoding="UTF-8"?>
<project name="programa" default="jar" basedir=".">
  <description>Programa que usa biblioteca aritmetica.</description>
    <!-- Ejemplo de archivo de construcción (buildfile)
         Para crear este archivo se ha consultado:
         https://ant.apache.org/manual/tutorial-HelloWorldWithAnt.html
         (cc0) jamj2000
    -->
    <property name="src.dir"     value="."/>
    <property name="build.dir"   value="build"/>
    <property name="classes.dir" value="${build.dir}/classes"/>
    <property name="jar.dir"     value="${build.dir}/jar"/>
    <property name="main-class"  value="Main"/>


    <!-- Creamos directorios para el resultado de la compilación --> 
    <target name="init">
      <mkdir dir="${classes.dir}"/>
      <mkdir dir="${jar.dir}"/>
    </target>


    <!-- Indicamos directorio donde se hallan las clases --> 
    <path id="compile.classpath">
        <fileset dir="aritmetica" />
    </path>


    <!-- Compilamos --> 
    <target name="compile" depends="init" >
      <javac srcdir="${src.dir}" destdir="${classes.dir}" includeantruntime="false" debug="true" >
        <classpath refid="compile.classpath"/>
      </javac>
    </target>


    <!-- Creamos archivo .jar --> 
    <target name="jar" depends="compile">
      <jar destfile="${jar.dir}/${ant.project.name}.jar" basedir="${classes.dir}">
        <manifest>
          <attribute name="Main-Class" value="${main-class}"/>
        </manifest>
      </jar>
    </target>


    <!-- Ejecutamos --> 
    <target name="run" depends="jar">
      <java jar="${jar.dir}/${ant.project.name}.jar" fork="true"/>
    </target>


    <!-- Borramos archivos generados --> 
    <target name="clean">
      <delete dir="build" />
    </target>


    <!-- Mostramos ayuda --> 
    <target name="help">      
      <echo level="info">
        Objetivos válidos para ant:

          jar (el objetivo por defecto si no se indica nada)
          compile
          run
          clean
          help
      </echo>
    </target>

</project>

~~~~
