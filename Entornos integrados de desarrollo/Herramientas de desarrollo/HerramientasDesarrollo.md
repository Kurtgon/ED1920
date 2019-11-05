# Entorno de desarrollo

___

## Introducción

**1.- ¿Para que sirve un compilador? ¿Qué tipo de archivo obtenemos tras compilar?**

Sirve para traducir un programa escrito en un lenguaje de programación a otro lenguaje de programación.

Tras compilar obtenemos un archivo que es **ejecutable** y es interpretado por la máquina.


**2.- ¿Para que sirve un enlazador? ¿Qué tipo de archivo obtenemos tras enlazar?**

Sirve para enlazar una serie de objetos obtenidos de la compilación de distintas fuentes, incluso escritos en lenguajes distintos siempre que sean del formato adecuado.

Aunque la función primordial del enlazador es resolver todas las referencias que puedan existir en el programa y agrupar todos los módulos en un solo fichero, que pueda ser cargado y ejecutado por el Sistema Operativo, realiza además otras funciones. Por ejemplo, insertar en el fichero resultante el código del módulo inicial, que es el encargado de iniciar la ejecución.

El archivo que tenemos es **un ejecutable o una biblioteca**.


**3.- ¿Para que sirve un interprete? ¿Obtenemos algún archivo tras interpretar?**

Sirve para analizar y ejecutar otros programas. Solo realizan la traducción a medida que sea necesaria, instrucción por instrucción y normalmente no se guardan el resultado de dicha traducción.

**No**.


**4.- Explica cada uno de los siguientes conceptos e indica la relación entre ellos.**

- **Código fuente**: es un conjunto de líneas de texto con los pasos que debe seguir el ordenador para ejecutar dicho programa.

- **Código objeto**: es un conjunto de instrucciones y datos escritos en binario o código máquina que provienen de la traducción a partir del código fuente de un programa.

- **Código binario**: es un sistema de representación de textos, imágenes o vídeos de los que se valen los ordenadores para procesar instrucciones, usando un sistema de enumeración que posee únicamente los digitos o bits cero o uno.

Hay una relación subordinada siendo el primer elemento el código binario, de este se desprende el código objeto del que a su vez parte el código fuente.


**5.- ¿Qué tipo de código es el `bytecode` generado por el compilador de Java?**

Es un código intermedio más abstracto que el código máquina. Habitualmente es tratado como un archivo binario que contiene un programa ejecutable similar a un módulo objeto, que es un archivo binario producido por el compilador cuyo contenido es el código objeto o código máquina.

---

## Herramientas de desarrollo

___

**1.- Ejecuta el programa "Hola mundo" en los siguientes lenguajes**:

    bash
    python
    php
    javascript (nodejs)
    c
    c++
    java
    ruby
    go
    rust
    lisp
    ensamblador (nasm)

Se ha ejecutado el "Hola mundo" siguiendo los pasos indicados en <https://github.com/jamj2000/DAW1-ED-HolaMundo>


**2.- Para cada uno de los lenguajes anteriores, indica el proceso realizado para conseguir ejecutar el código: ¿compilación o interpretación?**

    
    bash - Interpretación -
    python - Interpretación -
    php - Compilación -
    javascript (nodejs) - Interpretación -
    c - Compilación -
    c++ - Compilación -
    java - Compilación / Interpretación -
    ruby - Interpretación -
    go - Compilación -
    rust - Compilación -
    lisp - Interpretación -
    ensamblador (nasm) - Compilación -
    

**3.- Para cada uno de los lenguajes anteriores, indica el nombre del compilador o interprete utilizado en GNU/Linux.**

    bash -- Terminal --
    python -- Python --
    php -- php --
    javascript (nodejs) -- Node --
    c -- Gcc --
    c++ -- Gcc --
    java -- Javac(Compila) / Java(Interpreta y ejecuta) --
    ruby -- Ruby --
    go -- Go --
    rust -- Rustc --
    lisp -- Clips --
    ensamblador (nasm) -- (Nasm(Ensambla) / ld(Enlaza y ejecuta) --
    
    
**4.- Investiga y averigua que extensión tienen los archivos de código fuente de los siguientes lenguajes**:

    bash (.sh)
    python (.py)
    php (.php)
    javascript (.js)
    c (.c)
    c++ (.cpp)
    java (.java)
    ensamblador (.asm)
    ruby (.rb)
    go (.go)
    rust (.rs)
    lisp (.lisp)
    
    
**5.- Scripts ejecutables para los lenguajes interpretados. Edita los scripts para los siguientes lenguajes**:

    bash (echo "Hola Mundo")
    
    python (print "Hola mundo")
    
    php (<?php 
          echo "Hola mundo\n" 
         ?>)
    
    javascript (console.log('Hola mundo');)
    
    java (class Hola
          {
                public static void main(String[] args)
                 {
                    System.out.println("Hola Mundo");
                 }
            })
            
    ruby (puts "Hola Mundo")
    
    go (package main

        import "fmt"

        func main() {
                fmt.Println("Hola mundo desde Go")
        })
        
    rust (fn main() {
              println!("¡Hola, mundo! Desde RUST ");
            })
            
    lisp (format t "¡Hola, mundo!")
    
 Instrucciones en <https://github.com/jamj2000/DAW1-ED-HolaMundo>.
 
 
 **6.- ¿Qué extensión tienen los archivos de código objeto?**
 
 La extensión de los archivos de código objeto es ".o".
 
 
 **7.- Lenguaje C. Código en varios archivos. Obtener el código objeto a partir del código fuente de los 3 archivos siguientes**:
 
 
    //-------------
    // datos.c
    //-------------

    char *mensaje="Hola a todos y todas";
    int  num1 = 8;
    int  num2 = 10;
    
    //-------------
    // suma.c
    //-------------

    int suma (int a, int b) {
    return a + b;
    }
    
    //-------------
    // main.c
    //-------------

    #include <stdio.h>

    int suma (int a, int b);

    extern char *mensaje;
    extern int  num1, num2;

    int main(){
      printf("%s\n", mensaje);
      printf("%d\n", suma (num1, num2) );
      return 0;
     }
     
     # Para obtener código objeto

    gcc  -c  main.c  datos.c  suma.c
    
   Deberemos obtener 3 archivos: main.o, suma.o y datos.o
   
   **8.- Lenguaje C. Código en varios archivos. Obtener el código binario ejecutable a partir del código objeto de los 3 archivos anteriores**:
   
    # Para obtener código binario

    gcc  -o  programa  main.o  datos.o  suma.o
    
Deberememos obtener un archivo programa binario ejecutable. Si lo ejecutamos obtenemos el siguiente resultado:

    ./programa
    Hola a todos y todas
    18
    

**9.- Lenguaje C++. Código en varios archivos. Obtener el código objeto a partir del código fuente de los 3 archivos siguientes**:


      //-------------
     // datos.cpp
    //-------------
    # include <string>
    
    std::string mensaje = "Hola a todos y todas";
    
    int  num1 = 8;
    int  num2 = 10;


    //-------------
    // main.cpp
    //-------------
    #include <iostream>
    
    using namespace std;
    
    int suma (int a, int b);
    
    extern string mensaje;
    extern int  num1, num2;
    
    int main(){
      cout << mensaje << endl;
      cout << suma (num1, num2) << endl;
      return 0;
    }
    
    
    //-------------
    // suma.cpp
    //-------------
    int suma (int a, int b) {
      return a + b;
    }
    
    
    # Para obtener código objeto
    
    g++  -c  main.cpp  datos.cpp  suma.cpp
    
    
Deberemos obtener 3 archivos: main.o, suma.o y datos.o


**10.- Lenguaje C++. Código en varios archivos. Obtener el código binario ejecutable a partir del código objeto de los 3 archivos anteriores**:


    # Para obtener código binario
    
    g++  -o  programa  main.o  datos.o  suma.o
    
    
Deberememos obtener un archivo programa binario ejecutable. Si lo ejecutamos obtenemos el siguiente resultado:

    ./programa
    Hola a todos y todas
    18
    
    
**11.- Bibliotecas. Define que se entiende por biblioteca o librería y los tipos que existen**.


Es un conjunto de implementaciones funcionales, codificadas en un lenguaje de programación, que ofrece una interfaz bien definida para la funcionalidad que se invoca facilitando la programación.

Los tipos de biblioteca que podemos encontrar se clasifican en:

- Bibliotecas estáticas.
- Bibliotecas dinámicas.
- Bibliotecas remotas.

Por el tipo de trabajo que hacen nos podemos encontrar con:

- Entrada y salida.
- Matemáticas.
- De manejo de memoria.
- De manejo de textos.

En definitiva existen una gran cantidad de librerías disponibles y todas con una función concreta.


**12.- Bibliotecas. ¿Qué tipo es el más utilizado actualmente? ¿Por qué?**

Más información en <https://github.com/jamj2000/DAW1-ED-Bibliotecas>

Lo más habitual es distribuir la funcionalidad básica de una aplicación en bibliotecas dinámicas y la funcionalidad opcional en forma de plugins. De esta manera aprovechamos las ventajas de las bibliotecas dinámicas y mitigamos sus desventajas al prevenir el error de carga del programa que se produce cuando no se encuentra la biblioteca enlazada.


**13.- Bibliotecas. Crea una biblioteca dinámica en C que proporcione las funciones para sumar, restar, multiplicar y dividir 2 números enteros. Crea un programa que haga uso de ella y comprueba que se ejecuta correctamente**.

Instrucciones en <https://github.com/jamj2000/DAW1-ED-Bibliotecas>



**14.- Bibliotecas. Crea una biblioteca dinámica en Java que proporcione las funciones para sumar, restar, multiplicar y dividir 2 números enteros. Crea un programa que haga uso de ella y comprueba que se ejecuta correctamente**.

Instrucciones en <https://github.com/jamj2000/DAW1-ED-Bibliotecas>


**15.- Bibliotecas. Busca información y explica las ventajas y desventajas de usar bibliotecas estáticas**.

 **Ventajas**:
 
 - Al copiarse nuestra libreria cuando compilamos podriamos borrar la libreria que el programa seguiría funcionando. 
 - Solo copia la libreria que necesita.
 - Se puede llevar a otro ordenador y el programa funciona.
 - Es más rápido en ejecución.
 - No afecta a los ejecutables si cambiamos la libreria.
 
 
 **Desventajas**:
 
 - Pesa más el programa.
 - No se beneficia de las actualizaciones de las bibliotecas.

 
 **16.- Bibliotecas. Busca información y explica las ventajas y desventajas de usar bibliotecas dinámicas**.
 
 
  **Ventajas**:
  
  - Menor tamaño del programa con la reutilización no solo de código, sino de espacio físico(un mismo fichero de biblioteca compartida puede ser utilizada por varios programas sin que estos copien su contenido dentro de ellos).

  
  **Desventajas**:
  
  - El aumento del tiempo de carga (debido a tener que buscar el fichero de la biblioteca, cargarlo y relocalizar las llamadas en el programa) y el aumento de una indirección a la hora de llamar a las funciones de la biblioteca.
  
  
  
  **17.- Build. Automatiza el proceso de compilación de ejecutable y biblioteca, su enlazado y la generación del archivo ejecutable para código fuente en C con make. Haz uso de un buildfile**.

Instrucciones en <https://github.com/jamj2000/DAW1-ED-Bibliotecas/blob/master/Build.md>



**18.- Build. Automatiza el proceso de compilación de ejecutable y biblioteca, su enlazado y la generación del archivo .jar para código fuente en Java con Ant. Haz uso de un buildfile**.

Instrucciones en <https://github.com/jamj2000/DAW1-ED-Bibliotecas/blob/master/Build.md>


**19.- Build. Automatiza el proceso de compilación de ejecutable y biblioteca, su enlazado y la generación del archivo .jar para código fuente en Java con Maven. Haz uso de un buildfile**.

Instrucciones en <https://github.com/jamj2000/DAW1-ED-Bibliotecas/blob/master/Maven.md>


**20.- Build. Automatiza el proceso de compilación de ejecutable y biblioteca, su enlazado y la generación del archivo .jar para código fuente en Java con Gradle. Haz uso de un buildfile**.

Instrucciones en <https://github.com/jamj2000/DAW1-ED-Bibliotecas/blob/master/Gradle.md>



**21.- CMake. Automatiza el proceso de compilación de ejecutable y bibliotecas, su enlazado y la generación del archivo ejecutable para código fuente en C++. Crea un buildfile con CMake**.

Instrucciones en <https://github.com/jamj2000/DAW1-ED-Bibliotecas/blob/master/CMake.md>









   
   
   