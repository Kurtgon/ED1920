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
 