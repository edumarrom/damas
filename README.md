Ejercicios de Programación orientada a objetos: Damas
---
Programación — DAW - Ricardo Pérez López - IES Doñana - Curso 2020/2021
---

Programar en Python un modelo orientado a objetos que simule el juego de las damas. Para ello, habrá
que crear un tablero (una instancia de la clase Tablero) sobre el que se colocarán doce fichas blancas
y doce negras (instancias de la clase Ficha). Asimismo, habrá dos jugadores (instancias de la clase
Jugador). Cada jugador sabe cuál es su color y qué fichas son las suyas.

El tablero debe almacenar referencias a todas las fichas que haya en el tablero y saber en qué posición
está cada una.

Clase Ficha
---
La clase Ficha debe tener, al menos, los siguientes métodos:
| Método | Especificación |
|--------|----------------|
| **color()** | devuelve el color de la ficha, blanco ('B') o negro ('N'). |

---

Clase Tablero
---
La clase Tablero debe tener, al menos, los siguientes métodos:
| Método | Especificación |
|--------|----------------|
| **ficha(fila, columna)** | devuelve la ficha situada en una determinada casilla del tablero, o None si no hay ninguna. |
| **mover(ficha, direccion)** | mueve una ficha hacia la diagonal derecha o hacia la diagonal izquierda (direccion será 'DER' o 'IZQ'). Si la casilla de destino está ocupada por una ficha del color contrario, deberá comprobar si es posible comerla y, en tal caso, la comerá y la retirará del tablero. Si no puede moverse (porque la casilla de destino está ocupada por una ficha del mismo color, o bien porque ha llegado al extremo del tablero), no hará nada. Devuelve una tupla con la posición (fila, columna) donde ha quedado la ficha.|
| **siguiente_turno()** | llama al método siguiente_movimiento del jugador que le toque jugar, por turnos (empiezan las blancas). Si ese jugador no ha podido mover ninguna ficha, lo declara como perdedor. No devuelve nada. |
| **quien_gana()** | devuelve el jugador que ha ganado la partida o None si todavía no ha ganado nadie. |

---

Clase Jugador
---
La clase Jugador debe tener, al menos, los siguientes métodos:
| Método | Especificación |
|--------|----------------|
| **fichas()** | devuelve una lista con todas las fichas que son propiedad del jugador. |
| **siguiente_movimiento()** | elige al azar una ficha del jugador y trata de moverla. La dirección del movimiento (izquierda o derecha) también se seleccionará al azar. Si no es posible hacer el movimiento en una dirección, deberá probar en la otra. Si no es posible ningún movimiento con esa ficha, probará con otra ficha hasta que pueda mover una. Devuelve True si ha podido mover alguna, y False en caso contrario. |

> Indicación: Las fichas se crean en el constructor de la clase Jugador. El constructor del tablero le asigna el color blanco al primero y el negro al segundo.
