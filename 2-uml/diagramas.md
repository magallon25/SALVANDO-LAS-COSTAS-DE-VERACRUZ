# Diseño UML - Salvando las Costas de Veracruz

# Diseño UML - Salvando las Costas de Veracruz

## 1. Diagrama de Casos de Uso

```mermaid
flowchart LR
    Jugador((Jugador))
    subgraph Sistema [Salvando las Costas de Veracruz]
        UC1([Iniciar partida])
        UC2([Seleccionar nivel])
        UC3([Mover personaje])
        UC4([Recolectar residuos])
        UC5([Depositar basura en contenedores])
        UC6([Rescatar fauna marina])
        UC7([Pausar / Reiniciar nivel])
    end

    Jugador --> UC1
    Jugador --> UC2
    Jugador --> UC3
    Jugador --> UC4
    Jugador --> UC5
    Jugador --> UC6
    Jugador --> UC7
```

## 2. Diagrama de Clases

```mermaid
classDiagram
    class Nivel {
        -int numeroNivel
        -String nombrePlaya
        -float tiempoLimite
        -int metaLimpieza
        +iniciarTemporizador()
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
        +eliminarDeMapa()
    }

    class Contenedor {
        -String tipoAceptado
        +recibirResiduo(residuo) boolean
    }

    class FaunaMarina {
        -String especie
        -boolean estaAtrapada
        -int puntosRescate
        +liberar()
    }

    Juego "1" *-- "1..*" Nivel : contiene
    Nivel "1" *-- "1" Jugador : controla
    Nivel "1" *-- "*" Residuo : genera
    Nivel "1" *-- "*" Contenedor : incluye
    Nivel "1" *-- "*" FaunaMarina : alberga
    Jugador ..> Residuo : recolecta
    Jugador ..> Contenedor : deposita en
    Jugador ..> FaunaMarina : rescata
```

```
