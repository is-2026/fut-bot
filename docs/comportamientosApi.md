# <center> **Contrato API Comportamientos** </center>

### **Estructura Obligatoria del Código (Plantilla)**

Para que el motor de simulación pueda interpretar y ejecutar el comportamiento de un jugador, todo código proporcionado por el usuario debe incluir obligatoriamente una función principal llamada `decidir_accion()`. El sistema invocará esta función automáticamente en cada *tick* (instante) del partido.

La función `decidir_accion()` no recibe parámetros de entrada. Para que el jugador conozca el estado actual del partido (dónde está la pelota, dónde están los rivales, etc.), el usuario debe invocar las **Primitivas de posición (Lectura de Entorno)** dentro del cuerpo de esta función.

**Ejemplo de plantilla:**
```python
def decidir_accion():
    # 1. Obtener el estado usando primitivas
    x, y = my_pos()
    px, py = ball_pos()
    
    # 2. Lógica del comportamiento
    if has_ball():
        shoot_arco()
    else:
        move(px, py)
```

### **Primitivas de estado (Lectura de Entorno)**

Estas funciones no reciben parámetros y se utilizan para obtener el estado actual del campo de juego.

| Primitiva | Parámetros | Retorno | Descripción | 
| :--- | :--- | :--- | :--- |
| `my_pos()` | Ninguno | `(x, y)` | Devuelve las coordenadas horizontales y verticales actuales del jugador. |
| `ball_pos()` | Ninguno | `(x, y)` | Devuelve las coordenadas actuales de la pelota en la cancha. |
| `has_ball()` | Ninguno | `Booleano` | Retorna `true` si el jugador tiene la posesión actual de la pelota, o `false` en caso contrario. |
| `team_pos()` | Ninguno | `Lista de tuplas` | Retorna una lista con el ID y las coordenadas de los compañeros de equipo, ej: `[(id, x, y), ...]`. |
| `enemy_pos()`| Ninguno | `Lista de tuplas` | Retorna una lista con el ID y las coordenadas de los jugadores rivales. |
| `score()` | Ninguno | `(int, int)` | Devuelve el marcador actual del partido con el formato goles (propios, rival). |
| `time()` | Ninguno | `int` | Retorna el tiempo actual del partido. |
| `total_time()` | Ninguno | `int` | Retorna la duracion total del partido. |

### **Primitivas de Acciones**

Estas funciones requieren parámetros de entrada y dictan la próxima acción del jugador en el tick de simulación basándose en sus atributos PACSS.

| Primitiva | Parámetros | Descripción |  Atributo Asociado |
| :--- | :--- | :--- | :--- |
| `move(x, y)` | `x`: Destino horizontal.<br>`y`: Destino vertical. | Desplaza al jugador hacia la coordenada especificada en la cancha. | Speed y Agility |
| `pass(jugador_id)` | `jugador_id`: ID del compañero. | Toca la pelota hacia la posición del compañero seleccionado. | Agility y Power |
| `shoot(x, y, porcentaje_power)` | `x`: Destino horizontal.<br>`y`: Destino vertical. `porcentaje_power`: Porcentaje de fuerza del golpe al balón. | Ejecuta un remate. | Power |
| `shoot_arco()` | Ninguno | Ejecuta un remate en dirección al arco. | Power |
| `tackle()` | Ninguno | Intenta quitarle la pelota al jugador rival cercano que tenga la posesión. | Control |

