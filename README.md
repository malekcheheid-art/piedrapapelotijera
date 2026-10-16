# Piedra, Papel o Tijera - Persistencia de Datos

Proyecto de la materia Laboratorio de Programacion (LPR), 5to ano, Actividad 7.

## Datos generales
- Institucion: E.E.S.T. N° 1 "Eduardo Ader" - Vicente Lopez
- Autor: Malek Cheheid
- Grupo: A
- Docente: Yamil Ganduglia
- Materia: Laboratorio de Programacion

## Descripcion
Mini juego de Piedra, Papel o Tijera contra la inteligencia artificial de la consola. Cada partida jugada se registra en una estructura `Partida` y se persiste en disco en el archivo `src/historial_partidas.txt`. La escritura se realiza en modo append (`ios::app`) para no sobrescribir las partidas anteriores.

## Objetivos
1. Modelar datos heterogeneos con `struct`.
2. Escritura en disco con `ofstream` en modo append.
3. Lectura desde disco con `ifstream`.
4. Programacion modular con funciones.

## Estructura del repositorio
```text
piedrapapelotijera/
├── .gitattributes
├── .gitignore
├── LICENSE
├── README.md
├── enunciado_actividad7.pdf
├── src/
│   ├── main.cpp
│   └── historial_partidas.txt
├── docs/
│   ├── CHANGELOG.md
│   └── manuales/
│       ├── manual_programador_v1.0.0.md
│       └── manual_usuario_v1.0.0.md
└── capturas/
```

## Estructura de datos
La estructura `Partida` agrupa los siguientes campos:
- `idPartida`: numero de partida.
- `jugador`: nombre o nickname.
- `eleccionJugador`: jugada elegida por el usuario.
- `eleccionIA`: jugada elegida por la IA.
- `resultado`: Victoria, Derrota o Empate.

## Persistencia
- Escritura: `ofstream archivo("src/historial_partidas.txt", ios::app);`
- Lectura: `ifstream archivo("src/historial_partidas.txt");`
- Formato de registro: CSV, campos separados por coma.
- El archivo se crea automaticamente la primera vez que se juega una partida.

## Funciones principales
- `jugarPartida(int& contadorID)`: procesa una partida contra la IA.
- `guardarEnDisco(const Partida& p)`: guarda el resultado en disco.
- `leerHistorialDisco()`: muestra el historial completo.
- `cargarContadorID()`: recupera el ultimo ID para no repetir numeros entre ejecuciones.

## Compilacion
```powershell
g++ -std=c++11 src/main.cpp -o src/piedrapapelotijera.exe
```

## Ejecucion
```powershell
.\src\piedrapapelotijera.exe
```

## Cuestionario tecnico
1. RAM vs Disco: al cerrar la consola se borran las variables en RAM, pero el archivo en disco conserva las partidas, por eso la opcion 2 sigue mostrando el historial.
2. Sin `ios::app`, `ofstream` sobrescribe el archivo y se pierden las partidas previas.
3. `cin.ignore()` limpia el caracter Enter pendiente en el bufer antes de `getline()`.
4. `struct` agrupa variables relacionadas, simplificando el paso de datos entre funciones frente a variables sueltas.
5. En el Proyecto Integrador Anual se podrian guardar logs de sensores, usuarios, stock o turnos.

## Versionado
Version actual: v1.0.0. Ver `docs/CHANGELOG.md`.