# Especificación de Requerimientos de Software (SRS)
**Proyecto:** Salvando las Costas de Veracruz

## 1. Introducción
El presente documento define los requerimientos funcionales y no funcionales para el desarrollo de **Salvando las Costas de Veracruz**, un videojuego educativo y de acción ambiental enfocado en la limpieza de playas y protección de la fauna marina en el litoral veracruzano.

## 2. Descripción General
El sistema consiste en un videojuego donde el jugador controla a un brigadista ambiental que debe recolectar distintos tipos de residuos (plásticos, redes de pesca, desechos tóxicos) y rescatar especies marinas atrapadas (tortugas, aves costeras) a lo largo de distintos niveles ambientados en playas de Veracruz, cumpliendo objetivos antes de que se agote el tiempo o el ecosistema colapse.

## 3. Requerimientos Funcionales

| ID | Descripción | Prioridad | Criterio de Aceptación |
| :--- | :--- | :--- | :--- |
| **RF-01** | **Movimiento del jugador:** El usuario debe poder desplazar al personaje principal en cuatro direcciones dentro del escenario de la playa. | Alta | El personaje responde en menos de 100 ms a las teclas de dirección (WASD / Flechas) sin atravesar los límites del mapa ni obstáculos sólidos. |
| **RF-02** | **Recolección y clasificación de residuos:** El jugador debe poder recoger basura del suelo y depositarla en el contenedor correspondiente (orgánico, plástico, peligroso). | Alta | Al interactuar con un residuo, este se añade al inventario del jugador; al depositarlo en el contenedor correcto, se suman puntos al marcador. |
| **RF-03** | **Rescate de fauna marina:** El jugador debe poder liberar animales atrapados en residuos o redes mediante una acción de interacción. | Alta | Al acercarse a un animal atrapado y presionar la tecla de acción, se ejecuta la animación de rescate, el animal queda libre y se otorga una bonificación de puntaje. |
| **RF-04** | **Sistema de puntaje y temporizador:** La partida debe contar con un reloj en cuenta regresiva y un contador de puntos visibles en pantalla (HUD). | Media | El temporizador inicia según la configuración del nivel y disminuye cada segundo; al llegar a cero o alcanzar la meta de limpieza, se muestra la pantalla de resultados. |
| **RF-05** | **Gestión de niveles y menú principal:** El juego debe permitir iniciar una partida, pausar el juego, reiniciar el nivel y navegar entre niveles desbloqueados. | Media | Desde el menú principal se accede al selector de niveles; durante la partida, la tecla ESC detiene el tiempo y despliega las opciones de reanudar o salir. |

## 4. Requerimientos No Funcionales

| ID | Descripción | Prioridad | Criterio de Aceptación |
| :--- | :--- | :--- | :--- |
| **RNF-01** | **Rendimiento fluido:** El videojuego debe mantener una tasa de cuadros estable durante la ejecución de los niveles. | Alta | El juego se ejecuta a un mínimo de 30 FPS estables en navegadores modernos o equipos de gama básica sin caídas bruscas al generar múltiples objetos. |
| **RNF-02** | **Usabilidad e interfaz intuitiva:** Los controles, objetivos e indicadores visuales deben ser comprensibles sin necesidad de manuales externos. | Media | Cualquier usuario nuevo identifica cómo moverse, recoger basura y ver su tiempo restante en menos de 30 segundos de iniciar el primer nivel. |
| **RNF-03** | **Compatibilidad multiplataforma:** El sistema debe poder ejecutarse en los principales sistemas operativos de escritorio sin requerir configuraciones complejas. | Baja | El ejecutable o versión web funciona correctamente en Windows 10/11 y macOS/Linux con resolución estándar de 1280x720 o superior. |
