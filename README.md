# SALVANDO-LAS-COSTAS-DE-VERACRUZ

# Nombre del Proyecto

Breve descripción de qué trata su juego o sistema (2 o 3 líneas).

## Diseño de Interfaces
* [Ver prototipo interactivo en Figma/Canva](Pega_aquí_el_link_de_Figma_o_Canva)

## Integrantes
| Nombre Completo | Usuario de GitHub |
| :--- | :--- |
| Mario Adrian Magallon Barajas | https://github.com/Magallon25 |
| Justo Raúl Almeida Ruiz | https://github.com/rulexr375-oss |

classDiagram
    class Juego {
        -int puntajeTotal
        -String estado
        +iniciarPartida()
        +pausarJuego()
        +finalizarNivel()
    }

    class Nivel {
        -int numeroNivel
        -String nombrePlaya
        -float tiempoLimite
        -int metaLimpieza
        +actualizarTemporizador()
        +verificarVictoria()
    }

    class Jugador {
        -String nombre
        -float posX
        -float posY
        -int capacidadInventario
        +mover(direccion)
        +recogerResiduo(residuo)
        +depositarResiduo(contenedor)
        +rescatarFauna(animal)
    }

    class Residuo {
        -int id
        -String tipo
        -int valorPuntos
        +aparecer()
        +serRecolectado()
    }

    class Contenedor {
        -String tipoAceptado
        +validarResiduo(residuo) boolean
    }

    class FaunaMarina {
        -String especie
        -boolean estaAtrapado
        -int puntosRescate
        +liberar()
    }

    Juego "1" *-- "1..*" Nivel : contiene
    Nivel "1" *-- "1" Jugador : controla
    Nivel "1" o-- "*" Residuo : genera
    Nivel "1" o-- "3" Contenedor : incluye
    Nivel "1" o-- "*" FaunaMarina : alberga
    Jugador ..> Residuo : recolecta
    Jugador ..> Contenedor : deposita en
    Jugador ..> FaunaMarina : rescata
