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

1. Ejecutamos el ant:
~~~~
ant
~~~~
Tambien obtenemos:
~~~~
Buildfile: /home/jose/Proyectos/DAW1-ED-Bibliotecas/java/build.xml

init:
    [mkdir] Created dir: /home/jose/Proyectos/DAW1-ED-Bibliotecas/java/build/classes
    [mkdir] Created dir: /home/jose/Proyectos/DAW1-ED-Bibliotecas/java/build/jar

compile:
    [javac] Compiling 2 source files to /home/jose/Proyectos/DAW1-ED-Bibliotecas/java/build/classes

jar:
      [jar] Building jar: /home/jose/Proyectos/DAW1-ED-Bibliotecas/java/build/jar/programa.jar

BUILD SUCCESSFUL
Total time: 2 seconds
~~~~
Luego para ejecutar escribimos:
~~~~
ant run
~~~~
# Automatiza el proceso de compilación de ejecutable y biblioteca, su enlazadoy la generación del archivo .jar para código fuente en Java con Maven. Haz uso de un buildfile.
1. Lo primero que haremos será entrar en la carpeta para el proyecto:

~~~~
cd  ~/Proyectos
~~~~
2. Creamos la estructura de carpetas con maven:

~~~~
mvn  archetype:generate  -DgroupId=com.miempresa.app  -DartifactId=mi-app  -Dversion=1.0.0 \
       -DarchetypeArtifactId=maven-archetype-quickstart  -DinteractiveMode=false
~~~~
3. Entramos en el direcotio *mi-app*:
~~~~
cd mi-app
~~~~
4. Creamos 2 clases dentro de la ruta src/main/java/com/miempresa/app:
~~~~
nano  src/main/java/com/miempresa/app/App.java
~~~~
Con el siguiente código:
~~~~
package com.miempresa.app;

public class App {

  private static final int NUM1 = 5;
  private static final int NUM2 = 2;


  public static void main (String[] args) {
    System.out.println ("Dados los números " + NUM1 + " y " + NUM2 );
    System.out.println ("La suma es " + Aritmetica.suma(NUM1, NUM2) );
    System.out.println ("La resta es " + Aritmetica.resta(NUM1, NUM2) );
    System.out.println ("La multiplicación es " + Aritmetica.multiplicacion(NUM1, NUM2) );
    System.out.println ("La división es " + Aritmetica.division(NUM1, NUM2) );
  }
}
~~~~
La segunda clase:
~~~~
nano  src/main/java/com/miempresa/app/Aritmetica.java
~~~~
Con el siguiente código:
~~~~
package com.miempresa.app;

public class Aritmetica {

  public static int suma (int sumando1, int sumando2) {
        return (sumando1+sumando2);
  }

  public static int resta  (int minuendo, int sustraendo) {
        return (minuendo-sustraendo);
  }

  public static int multiplicacion (int  numero1, int numero2) {
        return (numero1*numero2);
  }

  public static float division (int dividendo, int divisor) {
        return (dividendo/(float)divisor);
  }

}
~~~~
5. Creamos otras 2 clases dentro de la ruta src/test/java/com/miempresa/app:
~~~~
nano  src/test/java/com/miempresa/app/AppTest.java
~~~~
Con el siguiente código:
~~~~
package com.miempresa.app;

public class Aritmetica {

  public static int suma (int sumando1, int sumando2) {
        return (sumando1+sumando2);
  }

  public static int resta  (int minuendo, int sustraendo) {
        return (minuendo-sustraendo);
  }

  public static int multiplicacion (int  numero1, int numero2) {
        return (numero1*numero2);
  }

  public static float division (int dividendo, int divisor) {
        return (dividendo/(float)divisor);
  }

}
~~~~
La segunda clase:
~~~~
nano  src/test/java/com/miempresa/app/AritmeticaTest.java
~~~~
Con el siguiente código:
~~~~
package com.miempresa.app;

import org.junit.Test;
import static org.junit.Assert.*;

public class AritmeticaTest {

    @Test
    public void testSuma() {
        assertEquals("Suma (2,3) = 5", 5, Aritmetica.suma(2,3));
    }
}
~~~~
6. Editamos el archivo que estaba ya dentro del dierctorio mi-app antes de crear las clases pom.xml:
~~~~
nano  pom.xml
~~~~
~~~~
<project>

  <modelVersion>4.0.0</modelVersion>
  <groupId>com.miempresa.app</groupId>
  <artifactId>mi-app</artifactId>
  <version>1.0.0</version>
  <name>mi-app</name>

  <build>
    <plugins>
      <plugin>
        <!-- Para construir un JAR ejecutable -->
        <groupId>org.apache.maven.plugins</groupId>
        <artifactId>maven-jar-plugin</artifactId>
        <version>3.0.2</version>
        <configuration>
          <archive>   
            <manifest>
              <addClasspath>true</addClasspath>
              <classpathPrefix>./</classpathPrefix>
              <mainClass>com.miempresa.app.App</mainClass>
            </manifest>
          </archive>
        </configuration>
      </plugin>

      <plugin>
        <!-- Para ejecutar el JAR creado --> 
        <groupId>org.codehaus.mojo</groupId>
          <artifactId>exec-maven-plugin</artifactId>
          <version>1.2.1</version>
          <configuration>
            <mainClass>com.miempresa.app.App</mainClass>
          </configuration>
       </plugin>
    </plugins>
  </build>

  <dependencies>
    <dependency>
      <!-- Prueba de unidades -->
      <groupId>junit</groupId>
      <artifactId>junit</artifactId>
      <version>4.12</version>
      <scope>test</scope>
    </dependency>
  </dependencies>

</project>

~~~~
7. Para compilar hacemos:
~~~~
mvn  compile
~~~~
> Nota: Obtenemos en la carpeta target/classes el bytecode.
Podemos ejecutar el bytecode de la siguiente manera:
~~~~
cd target/classes  &&  java com.miempresa.app.App  &&  cd ../..
~~~~
8. Para empaquetar en .jar hacemos lo siguiente:
~~~~
mvn  package
~~~~
Para ejecutar el jar hacemos:
~~~~
mvn  exec:java
~~~~
Otra forma de ejecutar el .jar es:
~~~~
java  -jar  target/mi-app-1.0.0.jar
~~~~
# Automatiza el proceso de compilación de ejecutable y biblioteca, su enlazado y la generación del archivo .jar para código fuente en Java con Gradle. Haz uso de un buildfile
1. Entramos en la carpeta que tenemos para proyectos:
~~~~
cd  ~/Proyectos
~~~~
2. Creamos una nueva carpeta llamada miapp y entramos en ella:
~~~~
mkdir  miapp  &&  cd  miapp
~~~~
3. Creamos la estructura de carpetas con gradle:
~~~~
gradle  init  --type  java-application
~~~~
4. Vemos que se crea la estructura y un *buildfile* llamado **build.gradle**
~~~~
tree    

.
├── build.gradle
├── gradle    
│   └── wrapper
│       ├── gradle-wrapper.jar
│       └── gradle-wrapper.properties
├── gradlew
├── gradlew.bat
├── settings.gradle
└── src
    ├── main
    │   └── java  
    │       └── App.java
    └── test
        └── java
            └── AppTest.java
~~~~
5. Generamos el codigo fuente y borramos las clases que vienen por defecto:
~~~~
rm  src/main/java/App.java  src/test/java/AppTest.java
~~~~
Creamos 2 clases dentro de la ruta src/main/java:
~~~~
nano  src/main/java/Main.java
~~~~
Y su respectivo código:
~~~~
public class Main {

  private static final int NUM1 = 5;
  private static final int NUM2 = 2;


  public static void main (String[] args) {
    System.out.println ("Dados los números " + NUM1 + " y " + NUM2 );
    System.out.println ("La suma es " + Aritmetica.suma(NUM1, NUM2) );
    System.out.println ("La resta es " + Aritmetica.resta(NUM1, NUM2) );
    System.out.println ("La multiplicación es " + Aritmetica.multiplicacion(NUM1, NUM2) );
    System.out.println ("La división es " + Aritmetica.division(NUM1, NUM2) );
  }
}
~~~~
La segunda clase:
~~~~
nano  src/main/java/Aritmetica.java
~~~~
Y su respectivo código:
~~~~
public class Aritmetica {

  public static int suma (int sumando1, int sumando2) {
        return (sumando1+sumando2);
  }

  public static int resta  (int minuendo, int sustraendo) {
        return (minuendo-sustraendo);
  }

  public static int multiplicacion (int  numero1, int numero2) {
        return (numero1*numero2);
  }

  public static float division (int dividendo, int divisor) {
        return (dividendo/(float)divisor);
  }

}
~~~~
Creamos 2 clases de test dentro de la ruta src/test/java:
~~~~
nano  src/test/java/MainTest.java
~~~~
Y su respectivo código:
~~~~
import org.junit.Test;
import static org.junit.Assert.*;

public class MainTest {

  @Test
  public void testMain() {
      // Prueba vacía
  }
}
~~~~
La segunda clase
~~~~
nano  src/test/java/AritmeticaTest.java
~~~~
~~~~
import org.junit.Test;
import static org.junit.Assert.*;

public class AritmeticaTest {
    
    @Test 
    public void testSuma() {
        assertEquals("Suma (2,3) = 5", 5, Aritmetica.suma(2,3));
    }

}
~~~~
6. Editamos el archivo build.gradle:
~~~~
apply plugin: 'java'
apply plugin: 'application'

repositories {
    jcenter()  
}

dependencies {
    compile 'com.google.guava:guava:23.0' 
    testCompile 'junit:junit:4.12'         
}

jar {
    manifest {
       attributes ('Main-Class': 'Main')
    }
}

mainClassName = 'Main'
~~~~
7. Compilamos:
~~~~
./gradlew  assemble
~~~~
En la carpeta build/classes obtendremos el bytecode correspondiente a cada clase.
Para ejecutar el bytecode hacemos:
~~~~
cd build/classes/main  &&  java Main  &&  cd ../../..
8. El archivo .jar se ha guardado en la carpeta build/libs. Para ejecutarlo escribimos:
~~~~
./gradlew  run
~~~~
Otra forma de ejecutarlo es:
~~~~
java  -jar  build/libs/miapp.jar
~~~~
9. Para ejecutar las pruebas:
~~~~
./gradlew  test
~~~~
Luego podemos ver el informe de las pruebas con :
~~~~
firefox build/reports/tests/test/index.html
~~~~
# Automatiza el proceso de compilación de ejecutable y bibliotecas, su enlazado y la generación del archivo ejecutable para código fuente en C++. Crea un buildfile con CMake.
1. Entramos en la carpeta proyectos:
~~~~
cd Proyectos
~~~~
2. Descargamos el código fuente
~~~~
git clone *"tu repositorio de github"*
~~~~
3. Entramos en el directorio:
~~~~
cd Directorio.cpp
~~~~
3. Creamos un directoro de construccón y entramos en el:
~~~~
mkdir  build  &&  cd  build
~~~~
4. Generamos el archivo *Makefile*, el ejecutable y las bibliotecas:
~~~~
cmake  ..
~~~~
> Nota: *".."* indica el Directorio padre.
5. Comprobamos que se creo el **"Makefile"**:
~~~~
ls 
cat Makefile
~~~~
6. Ahora podemos realizar el proceso de construcción con el comando make:
~~~~
make
~~~~
7. Para realizar la instalación hacemos:
~~~~
sudo  make  install
~~~~
