# Changelog

Registro de versiones del software del juego Piedra, Papel o Tijera con persistencia de datos.

## v1.0.0 - 16 de octubre de 2026

Primera version entregada para la Actividad 7 de Laboratorio de Programacion.

### Agregado

- Estructura `Partida` con los campos `idPartida`, `jugador`, `eleccionJugador`, `eleccionIA` y `resultado`.
- Menú principal en consola con las opciones jugar, ver historial y salir.
- Función `jugarPartida(int& contadorID)` con la lógica de la partida contra la IA.
- Elección aleatoria de la IA mediante `rand()` con semilla `srand(time(0))`.
- Evaluación de las reglas de Piedra, Papel o Tijera con resultado Victoria, Derrota o Empate.
- Persistencia en disco con `ofstream` en modo `ios::app` para no sobrescribir partidas anteriores.
- Lectura del historial con `ifstream` y `getline` delimitado por comas (formato CSV).
- Función `cargarContadorID()` que recupera el último ID usado para no repetir identificadores entre ejecuciones.
- Archivo de datos `src/historial_partidas.txt` generado automáticamente en la primera partida.
- Validación de la opción del menú: solo se aceptan los valores 1, 2 y 3.
- Validación de la jugada: se vuelve a preguntar mientras la opción no sea válida.
- Validación del nombre del jugador: no se permite una cadena vacía.
- Manejo del búfer de entrada con `cin.ignore()`, `cin.clear()` e `ignore` para evitar saltos y bucles infinitos.
- Avisos amigables cuando el historial no existe, está vacío o una línea está mal formada.

### Documentacion

- `README.md` con descripcion del proyecto, estructura, compilacion y ejecucion.
- Informe `docs/InformeEEST1_LPR2026_ACT07_G03_Informe_v1.0.0.pdf` en formato APA v7 con el cuestionario tecnico respondido.
- Manual del programador en PDF y Markdown con el analisis tecnico y el codigo fuente completo.
- Manual de usuario en PDF y Markdown con las instrucciones paso a paso del juego.
- Manuales redactados bajo norma APA v7 con numeros de pagina, margenes de 2.54 cm y doble espaciado.
- Referencias bibliograficas de GeeksforGeeks, Microsoft Learn y cppreference.

### Evidencias

- Captura de la partida jugada en la consola (`capturas/jugada_consola.png`).
- Captura del archivo de historial abierto en el Bloc de notas (`capturas/archivo_disco.png`).
- Captura del repositorio publicado en GitHub (`capturas/repo_github.png`).
- Captura del repositorio publicado en GitLab (`capturas/repo_gitlab.png`).
- Captura de la consola con la verificacion del dual push (`capturas/dual_push_consola.png`).

### Configuracion

- `.gitignore` para excluir ejecutables (`.exe`), archivos de salida (`*.out`) y `.vscode/`.
- `.gitattributes` para normalizar los finales de linea de texto.
- `LICENSE` con licencia MIT escolar.

### Repositorio

- Publicación inicial en GitHub: https://github.com/malekcheheid-art/piedrapapelotijera
- Publicación inicial en GitLab: https://gitlab.com/malekcheheid-art/piedrapapelotijera
- Sincronización dual-remote con historial de 21 commits ordenado y descriptivo.