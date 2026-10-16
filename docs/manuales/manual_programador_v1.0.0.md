# Manual del Programador - v1.0.0

## Compilacion
```powershell
g++ -std=c++11 src/main.cpp -o src/piedrapapelotijera.exe
```

## Estructura
- `src/main.cpp`: codigo fuente principal.
- `src/historial_partidas.txt`: persistencia de partidas.

## Notas
- El archivo de historial se crea automaticamente al jugar la primera partida.
- La ruta del archivo es relativa a la raiz del proyecto.