# Manual de Usuario: Mini Juego Piedra, Papel o Tijera con Persistencia

Laboratorio de Programación

Malek Cheheid  
E.E.S.T. N° 1 "Eduardo Ader", Vicente López  
Docente: Yamil Ganduglia  
16 de octubre de 2026

Repositorio: https://github.com/malekcheheid-art/piedrapapelotijera

---

## Resumen

Esta guía explica cómo utilizar el juego Piedra, Papel o Tijera desde la consola de Windows. El documento describe los requisitos necesarios para ejecutarlo, cómo iniciar el programa paso a paso, qué significa cada una de las tres opciones del menú principal, cómo se juega una partida completa contra la computadora y dónde queda guardado el historial de partidas. También se explican las reglas del juego, el formato del archivo de texto donde se registran los resultados, las preguntas más frecuentes y cómo resolver los problemas que suelen aparecer al ejecutarlo por primera vez. El manual está escrito para alguien que nunca compiló un programa, por lo que todas las instrucciones están escritas en pasos numerados y usan los mismos textos que aparecen en pantalla. No es necesario tener conocimientos de programación ni conexión a internet para seguir la guía. Todo el juego funciona en una única ventana de consola y los datos quedan almacenados en un archivo de texto de muy pequeño tamaño, que puede abrirse con cualquier editor para comprobar qué partidas se registraron.

*Palabras clave:* manual de usuario, juego de consola, cómo jugar, historial de partidas, Piedra, Papel o Tijera.

---

## Introducción

El programa es un juego de Piedra, Papel o Tijera que se juega desde una ventana de consola. El usuario elige su jugada, la computadora elige la suya al azar y el programa anuncia el resultado. Cada partida queda guardada en un archivo de texto, de modo que se puede volver a consultar el historial aunque se cierre la consola y se abra el programa otra vez.

Este manual está pensado para alguien que nunca compiló un programa. Todas las instrucciones están escritas paso a paso y usando los mismos textos que aparecen en pantalla, para que puedas seguirlas sin necesidad de ayuda.

## Requisitos para Usar el Juego

Para poder jugar necesitás cumplir solo cuatro condiciones:

- Una computadora con Windows 10 o Windows 11.
- La carpeta del proyecto completa, con la subcarpeta src y el archivo ejecutable.
- PowerShell o el Símbolo del sistema, que ya viene instalado en Windows.
- Ninguna instalación adicional: el programa usa solo la biblioteca estándar de C++.

No hace falta conexión a internet. Si ya tenés el ejecutable piedrapapelotijera.exe, ya tenés todo lo necesario para jugar.

## Cómo Iniciar el Juego

Abrí PowerShell. Para eso, presioná la tecla Windows, escribí PowerShell y abrilo. Una vez abierta la ventana, escribí el comando para entrar a la carpeta del proyecto:

```powershell
cd "C:\Users\Malek\OneDrive\Desktop\piedrapapelotijera"
```

Después iniciá el juego con este comando:

```powershell
.\src\piedrapapelotijera.exe
```

Es importante escribir el comando desde la carpeta del proyecto, porque el archivo del historial se guarda en la ruta src/historial_partidas.txt. Si el programa se abre desde otra carpeta, puede avisar que no encuentra el archivo.

Al iniciarse aparece una pantalla con el título de la actividad, tu nombre y el menú principal.

## El Menú Principal

El menú ofrece tres opciones:

```text
--- MENU PRINCIPAL DE JUEGO Y PERSISTENCIA ---
1. Jugar Partida (Piedra, Papel o Tijera)
2. Ver Historial de Partidas Guardadas en Disco (.txt)
3. Salir del Sistema
Ingrese una opcion (1-3):
```

Cada opción hace lo siguiente:

- La opción 1 empieza una partida nueva.
- La opción 2 muestra todas las partidas jugadas anteriormente.
- La opción 3 cierra el programa.

Si escribís un número que no sea 1, 2 o 3, el programa escribe [ERROR] Opcion invalida. Reintente. y vuelve a mostrar el menú. Lo mismo pasa si escribís letras en lugar de números.

## Cómo Jugar una Partida

Elegí la opción 1. El programa muestra el número de partida y te pide un nombre o apodo:

```text
--- NUEVA PARTIDA #1 ---
Ingrese su Nombre / Nickname:
```

Escribí tu nombre y presioná Enter. El nombre no puede quedar vacío: si presionás Enter sin escribir nada, aparece [ERROR] El nombre no puede estar vacio. y el programa vuelve a preguntar.

Después elegí tu jugada:

```text
Elija su jugada:
1. Piedra
2. Papel
3. Tijera
Opcion (1-3):
```

La computadora elige al azar y el programa anuncia ambas jugadas y el resultado:

```text
[JUGADA] Malek eligio: Piedra
[JUGADA] La IA eligio: Piedra
=> RESULTADO: Empate!
```

Finalmente aparece el aviso de guardado:

```text
[DISCO] Partida resguardada con exito en 'historial_partidas.txt'.
```

Ese mensaje confirma que la partida quedó guardada. Después el programa vuelve a mostrar el menú para que puedas seguir jugando.

### Reglas del Juego

El resultado de cada partida se define con estas cuatro reglas:

- Piedra le gana a Tijera.
- Papel le gana a Piedra.
- Tijera le gana a Papel.
- Si ambos eligen lo mismo, hay empate.

### Ver el Historial desde el Menú

Elegí la opción 2 del menú. El programa abre el archivo del disco y muestra todas las partidas guardadas:

```text
HISTORIAL DE PARTIDAS RECUPERADO DESDE DISCO
Partida #1 | Jugador: Malek | Piedra vs Piedra | Resultado: Empate
Partida #2 | Jugador: malek | Papel vs Piedra | Resultado: Victoria

[SISTEMA] Total de registros leidos desde disco: 2
```

Si todavía no jugaste ninguna partida, el programa avisa [AVISO] Aun no existen partidas guardadas en disco. Si el archivo existe pero está vacío, muestra [AVISO] El archivo de historial esta vacio.

### Salir del Programa

Elegí la opción 3. El programa muestra un último mensaje y se cierra:

```text
[SISTEMA] Saliendo del programa... Datos resguardados en disco.
```

También podés cerrar la ventana de la consola directamente. Las partidas que ya fueron guardadas no se pierden, porque están escritas en el archivo de texto.

## Dónde Queda Guardado el Historial

Las partidas se guardan en el archivo src/historial_partidas.txt, dentro de la carpeta del proyecto. Cada partida es una línea con los datos separados por comas:

```text
1,Malek,Piedra,Piedra,Empate
2,malek,Papel,Piedra,Victoria
```

Los campos son, en orden: número de partida, nombre, jugada del jugador, jugada de la computadora y resultado. El archivo se crea solo la primera vez que se juega, y las partidas nuevas se agregan al final sin borrar las anteriores. Se puede abrir con el Bloc de notas para ver el contenido.

Una característica importante del juego es que las partidas quedan guardadas aunque cierres la consola. La próxima vez que abras el programa y elijas la opción 2, vas a ver el historial completo, incluyendo las partidas de la sesión anterior.

## Preguntas Frecuentes

Estas son las consultas más comunes y sus respuestas:

- ¿Necesito internet? No. El juego funciona sin conexión.
- ¿Puedo jugar varias partidas? Sí, el menú permite repetir tantas veces como quieras.
- ¿Puedo usar otro nombre en cada partida? Sí, el nombre se pide de nuevo en cada partida.
- ¿Se borra el historial si reinstalo el juego? No, el archivo historial_partidas.txt sigue en la carpeta src.
- ¿Cuánto ocupa el archivo? Muy poco, porque solo guarda una línea de texto por partida.
- ¿Puedo borrar el historial? Sí, podés borrar el archivo historial_partidas.txt con el Bloc de notas y el juego crea uno nuevo la próxima partida.

## Qué Hacer si Algo No Funciona

Si tenés alguno de estos problemas, seguí estas indicaciones:

- Si el sistema no reconoce el ejecutable, revisá que estés dentro de la carpeta correcta antes de escribir el comando.
- Si aparece un aviso de que no hay partidas guardadas, jugá una partida con la opción 1.
- Si el programa no guarda nada, verificá que la carpeta src exista y que tengas permiso de escritura.
- Si el nombre se pasa por alto, asegurate de escribir el nombre antes de presionar Enter.
- Si aparece un error al compilar, revisá que el comando incluya exactamente -std=c++11.

## Referencias

cppreference.com. (s. f.). *std::basic_ofstream::open*. En cppreference.com. https://en.cppreference.com/w/cpp/io/basic_ofstream/open

GeeksforGeeks. (s. f.). *cin.ignore() function in C++*. GeeksforGeeks. https://www.geeksforgeeks.org/cpp/cin-ignore-function-in-cpp/

GeeksforGeeks. (s. f.). *Structs y estructuras de datos en C++*. GeeksforGeeks. https://www.geeksforgeeks.org/cpp/structures-in-cpp/

## Anexo A

### Ejemplo del Archivo de Historial

Este es el contenido de ejemplo del archivo src/historial_partidas.txt generado durante las pruebas del juego:

```text
1,Malek,Piedra,Piedra,Empate
2,malek,Papel,Piedra,Victoria
```