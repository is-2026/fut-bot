### Primitivas para programacion de Comportamientos

**Primitivas de posicion (Lectura de Entorno)**
Estas funciones no reciben parámetros y se utilizan para que obtener el estado actual del campo de juego.

| Primitiva | Parámetros | Retorno | Descripción | 
| :--- | :--- | :--- | :--- |
| `my-pos()` | Ninguno | `(x, y)` | Devuelve las coordenadas horizontales y verticales actuales del jugador. |
| `ball-pos()` | Ninguno | `(x, y)` | Devuelve las coordenadas actuales de la pelota en la cancha. |
| `has-ball()` | Ninguno | `Booleano` | Retorna `true` si el jugador tiene la posesión actual de la pelota, o `false` en caso contrario. |
| `team-pos()` | Ninguno | `Lista de tuplas` | Retorna una lista con el ID y las coordenadas de los compañeros de equipo, ej: `[(id, x, y), ...]`. |
| `enemy-pos()`| Ninguno | `Lista de tuplas` | Retorna una lista con el ID y las coordenadas de los jugadores rivales. |

**Primitivas de Acciones **
Estas funciones requieren parámetros de entrada y dictan la próxima acción del jugador en el tick de simulación basándose en sus atributos PACSS.

| Primitiva | Parámetros | Descripción |  Atributo Asociado |
| :--- | :--- | :--- | :--- |
| `move(x, y)` | `x`: Destino horizontal.<br>`y`: Destino vertical. | Desplaza al jugador hacia la coordenada especificada en la cancha. | Speed y Agility |
| `pass(jugador_id)` | `jugador_id`: ID del compañero. | Toca la pelota hacia la posición del compañero seleccionado. | Agility y Power |
| `shoot()` | Ninguno | Ejecuta un remate al arco rival. | Power |
| `tackle()` | Ninguno | Intenta quitarle la pelota al jugador rival cercano que tenga la posesión. | Control |
| `carryball(x, y)` | `x`: Destino horizontal.<br>`y`: Destino vertical. | Avanza hacia las coordenadas manteniendo el control de la pelota. | Speed y Agility |
