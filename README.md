# Piedra, Papel o Tijera - Persistencia de Datos

Proyecto de la materia Laboratorio de Programacion (LPR), 5to ano, Actividad 7.

## Autor
- Malek Cheheid
- Grupo A

## Institucion
E.E.S.T. N° 1 "Eduardo Ader" - Vicente Lopez

## Docente
Yamil Ganduglia

## Descripcion
Mini juego de Piedra, Papel o Tijera contra la IA de la consola, con persistencia de las partidas en un archivo de texto (`historial_partidas.txt`). Cada partida se registra en una estructura `Partida` y se guarda en disco en modo append (`ios::app`).

## Estructura del repositorio
- `src/main.cpp`: codigo fuente principal del juego.
- `src/historial_partidas.txt`: archivo de persistencia generado al jugar.
- `docs/`: documentacion y manuales.
- `capturas/`: evidencias de ejecucion.

## Compilacion
```powershell
g++ -std=c++11 src/main.cpp -o src/piedrapapelotijera.exe
```

## Ejecucion
```powershell
.\src\piedrapapelotijera.exe
```