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
        UC5([Clasificar basura en contenedores])
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
