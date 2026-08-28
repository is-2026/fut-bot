﻿# Casos de Uso: FutBot


### Caso de Uso 1: Registrar Usuario y Club
- **Actor primario:** Usuario visitante
- **Precondición:** El usuario se encuentra en la pantalla de ingreso del sistema.
- **Escenario exitoso principal:**
  1. El usuario selecciona la opción de registrarse.
  2. El sistema solicita ingresar nombre de usuario, email, contraseña, avatar y el nombre del club.
  3. El usuario ingresa los datos solicitados y confirma la operación.
  4. El sistema valida los datos y crea la nueva cuenta.
- **Escenarios excepcionales:**
  4. a) El email ingresado ya se encuentra registrado. 
  - El sistema informa al usuario que el email proporcionado ya está en uso.

### Caso de Uso 2: Iniciar sesión
- **Actor primario:** Usuario
- **Precondición:** El usuario se registró previamente.
- **Escenario exitoso principal:**
  1. El usuario selecciona la opción de iniciar sesión.
  2. El sistema solicita ingresar email y contraseña.
  3. El usuario ingresa los datos solicitados y confirma la operación.
  4. El sistema valida los datos e inicia la sesión.
- **Escenarios excepcionales:**
  4. a) El email ingresado es incorrecto. 
  - El sistema informa al usuario que el email proporcionado es incorrecto.
  4. b) La contraseña ingresada es incorrecta. 
  - El sistema informa al usuario que la contraseña proporcionada es incorrecta.

### Caso de Uso 3: Crear jugador
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado en el sistema.
- **Escenario exitoso principal:**
  1. El usuario selecciona la opción de crear un nuevo jugador.
  2. El sistema solicita el nombre del jugador y los valores para los atributos PACSS (Power, Agility, Control, Speed, Strength).
  3. El usuario ingresa el nombre, asigna los valores a los atributos y confirma la creación.
  4. El sistema valida que los atributos sumen exactamente 300, crea al jugador y lo muestra en la plantilla.
- **Escenarios excepcionales:**
  4.a) La suma total de los atributos PACSS es distinta a 300.
  - El sistema informa que la suma total de los atributos de un jugador debe ser de 300.
  4.b) Algún atributo posee un valor fuera del rango permitido (0-100).
  - El sistema informa que el atributo posee un valor fuera del rango permitido.
 
### Caso de Uso 4: Eliminar jugador
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado y se encuentra en la pantalla de gestión de su plantilla.
- **Escenario exitoso principal:**
  1. El usuario selecciona un jugador de su club y elige la opción de eliminar.
  2. El sistema advierte sobre la acción irreversible y solicita confirmación.
  3. El usuario confirma la eliminación.
  4. El sistema valida que el jugador no esté inscripto en una liga activa ni jugando un partido, lo elimina de la base de datos y actualiza la plantilla de jugadores.
- **Escenarios excepcionales:**
  4.a) El jugador se encuentra disputando ligas o partidos activos:
  - El sistema informa que el jugador está en uso y cancela la operación de eliminación.



### Caso de Uso 5: Crear nuevo comportamiento
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado en el sistema.
- **Escenario exitoso principal:**
  1. El usuario selecciona la opción de crear un nuevo comportamiento.
  2. El sistema muestra el editor de código integrado.
  3. El usuario escribe el código en Python, ingresa un nombre para el comportamiento y solicita guardarlo.
  4. El sistema valida el código (sintaxis y seguridad), guarda el comportamiento y muestra un mensaje de éxito.
- **Escenarios excepcionales:**
  **4.a) El código contiene errores de sintaxis o usa instrucciones prohibidas.
  - El sistema informa los errores detectados en el editor y solicita corregirlos.

### Caso de Uso 6: Eliminar comportamiento
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado y viendo la lista de comportamientos.
- **Escenario exitoso principal:**
1. El usuario selecciona el comportamiento que desea eliminar.
2. El sistema pide confirmación para eliminar el comportamiento.
3. El usuario confirma la eliminación del comportamiento.
4. El sistema verifica que el comportamiento no este en uso, lo elimina y desasocia el comportamiento de los jugadores que lo tienen guardado.
- **Escenarios Excepcionales:**
4.a) El comportamiento se encuentra en uso por un jugador jugando un partido:
- El sistema informa al usuario que el comportamiento se encuentra en uso y no es posible eliminarlo.

### Caso de Uso 7: Editar comportamiento 
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado y viendo la lista de comportamientos.
- **Escenario exitoso principal:**
1. El usuario selecciona el comportamiento que desea editar.
4. El sistema verifica que el comportamiento no este en uso, lo elimina y abre la interfaz de edición del comportamiento.
3. El usuario confirma la edición del comportamiento.
4. El sistema verifica que el comportamiento sea válido y lo actualiza.
- **Escenarios Excepcionales:**
4.a) El comportamiento se encuentra en uso por un jugador jugando un partido:
- El sistema informa al usuario que el comportamiento se encuentra en uso y no es posible editarlo.
4.b) El comportamiento no es válido:
- El sistema informa al usuario que el comportamiento no es válido y pide al usuario actualizarlo.

### Caso de Uso 8: Cambiar comportamiento durante el partido
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado y visualizando un partido en curso de su club.
- **Escenario exitoso principal:**
  1. El usuario selecciona a uno de sus jugadores titulares y elige la opción de cambiar su comportamiento.
  2. El sistema muestra la lista de comportamientos guardados por el usuario y solicita elegir uno.
  3. El usuario selecciona el nuevo comportamiento y confirma el cambio.
  4. El sistema valida la existencia del comportamiento, lo asigna al jugador y actualiza sus acciones para el siguiente "tick" del simulador.
- **Escenarios excepcionales:**
  4.a) El comportamiento seleccionado fue eliminado o es inválido:
  - El sistema informa el error y mantiene el comportamiento anterior del jugador.

### Caso de Uso 9: Abandonar Liga
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado y se encuentra inscripto en una liga.
- **Escenario exitoso principal:**
  1. El usuario ingresa a los detalles de una liga en la que participa y selecciona la opción de abandonar.
  2. El sistema solicita confirmación para darse de baja.
  3. El usuario confirma la operación.
  4. El sistema valida que la liga se encuentre en estado "No iniciada", retira al club del torneo y actualiza la vista de ligas del usuario.
- **Escenarios excepcionales:**
  4.a) La liga ya comenzó o está en curso:
  - El sistema informa que no es posible abandonar una competencia iniciada y bloquea la acción.


### Caso de Uso 10: Jugar amistoso
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado
- **Escenario exitoso principal:**
  1. El usuario acepta desafío amistoso, o envía desafío amistoso a otro usuario y éste se lo acepta.
  2. El sistema solicita elegir 3 jugadores titulares y 3 suplentes para el partido.
  3. El usuario selecciona sus 6 jugadores.
  4. El sistema inicia el partido amistoso.


### Caso de uso 11: cancelar liga
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado y creó la liga
- **Escenario exitoso principal:**
  1. El usuario selecciona la opción de cancelar liga.
  2. El sistema solicita confirmación para cancelar la liga.
  3. El usuario confirma la cancelación.
  4. El sistema informa a los usuarios participantes que la liga fue cancelada y los retira de la misma.

- **Escenarios excepcionales:**
  1.a) La liga comenzó o está en curso:
  -El sistema informa que no es posible eliminar una liga ya iniciada y bloquea la acción.


### Caso de uso 12: observar partido como espectador
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado, pertenece a la liga y hay al menos 1 partido en curso en la liga
- **Escenario exitoso principal:** 
  1. El usuario selecciona la opción de ver partidos en curso.
  2. El sistema muestra los partidos que se están jugando en vivo.
  3. El usuario selecciona el partido que quiere observar
  4. El sistema muestra en tiempo real la interfaz 2D de la cancha con sus jugadores y las habilidades de los mismos.


### Caso de Uso 13: Iniciar liga
- **Actor primario:** Usuario
- **Precondición:** El usuario es dueño de  la liga y la liga posee mas de 3 jugadores
- **Escenario exitoso principal:**
  1. El usuario ingresa a los detalles de la liga  y selecciona la opción de iniciar.
  2. El sistema solicita confirmación para iniciar la liga informando la cantidad de participantes actuales.
  3. El usuario confirma la operación.
  4. El sistema cambia la liga de estado de "No iniciada" a "Iniciada", calcula el fixture con el orden de los partidos a realizarse, se actualiza la vista de ligas del los participantes.

### Caso de Uso 14: Eliminar comportamiento
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado
- **Escenario exitoso principal:** 
 1. El usuario selecciona el comportamiento que desea eliminar.
  2. El sistema pide confirmación para eliminar el comportamiento.
  3. El usuario confirma la eliminación del comportamiento.
  4. El sistema verifica que el comportamiento no este en uso, lo elimina y desasocia el comportamiento de los jugadores que lo tienen guardado.
- **Escenarios Excepcionales:** 
  4.a) El comportamiento se encuentra en uso por un jugador jugando un partido:
    - El sistema informa al usuario que el comportamiento se encuentra en uso y no es posible eliminarlo.

### Caso de uso 15:  Observar partido como espectador
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado, pertenece a la liga y hay al menos 1 partido en curso en la liga
- **Escenario exitoso principal:**
1. El usuario selecciona la opción de ver partidos en curso.
2. El sistema muestra los partidos que se están jugando en vivo.
3. El usuario selecciona el partido que quiere observar
4. El sistema muestra en tiempo real la interfaz 2D de la cancha con sus jugadores y las habilidades de los mismos.
  
### Caso de Uso 16: Responder al desafío amistoso
- **Actor primario:** Usuario desafiado
- **Precondición:** El usuario está logueado y tiene un desafío pendiente de aceptar.
- **Escenario exitoso principal:**
1. El usuario selecciona el desafío que recibió.
2. El sistema muestra la información del desafío y opciones para aceptar o rechazar el desafío.
3. El usuario acepta el desafío.
4. El sistema registra la aceptación y establece el partido.
- **Escenarios Excepcionales:**
  4.a) El partido amistoso ya no está disponible:
  - El sistema informa al usuario que el desafío caducó o no se encuentra disponible.

### Caso de Uso 17: Programar sustitución de jugador
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado y visualizando un partido en curso de su club.
- **Escenario exitoso principal:**
  1. El usuario selecciona la opción de realizar un cambio táctico.
  2. El sistema muestra los jugadores titulares, los suplentes disponibles y solicita indicar quién sale y quién entra.
  3. El usuario selecciona al jugador saliente, al jugador entrante y confirma la sustitución.
  4. El sistema valida que el usuario disponga de cambios restantes (máximo 3) y registra la solicitud (actualizando los cambios restantes) para ejecutarse en la próxima pausa reglamentaria (hidratación o entretiempo).
- **Escenarios excepcionales:**
  4.a) El usuario ya agotó sus 3 cambios permitidos:
  - El sistema informa que no quedan cambios disponibles y deniega la operación.

### Caso de Uso 18: Consultar fixture y tabla de posiciones
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado y es miembro de una liga.
- **Escenario exitoso principal:**
  1. El usuario ingresa a los detalles de una liga en la que participa y selecciona la opcion de consultar fixture y tabla de posiciones.
  2. El sistema valida que la liga este iniciada, solicita la informacion y actualiza la vista del usuario.
- **Escenarios excepcionales:**
  2.a) La liga no comenzo:
  - El sistema informa que no es posible visualizar el fixture y la tabla de posiciones de una competencia no iniciada y bloquea la acción.

### Caso de Uso 19: Consultar ranking global
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado.
- **Escenario exitoso principal:**
  1. El usuario selecciona la opcion Ranking global.
  2. El sistema solicita la informacion y actualiza la vista del usuario.

### Caso de Uso 20: Cancelar sustitución de jugador
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado, visualizando un partido en curso de su club, y tiene al menos una solicitud de sustitucion registrada.
- **Escenario exitoso principal:**
  1. El usuario selecciona la opción de cancelar un cambio táctico.
  2. El sistema informa todos los cambios registrados a ejecutarse en la proxima pausa y solicita seleccionar aquel a ser cancelado.
  3. El usuario selecciona el cambio, el sistema cancela la solicitud de sustitución y actualiza los cambios restantes.

### Caso de Uso 21: Abandonar partido como espectador
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado, visualizando un partido como espectador.
- **Escenario exitoso principal:**
  1. El usuario selecciona la opcion de abandonar el partido como espectador.
  2. El sistema actualiza la vista y regresa al apartado de la liga correspondiente al partido que se estaba visualizando.

### Caso de Uso 22: Cerrar sesion
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado.
- **Escenario exitoso principal:**
  1. El usuario selecciona la opcion de cerrar sesion.
  2. El sistema cierra la sesion del usuario y actualiza la vista al apartado de inicio de sesion.

### Caso de Uso 23: Ver club de un usuario
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado, visualizando el ranking global.
- **Escenario exitoso principal:**
  1. El usuario selecciona el club de interes.
  2. El sistema solicita la informacion del usuario correspondiente y actualiza a la vista del club.

### Caso de Uso 24: Ver historial de un club
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado, en la vista de un club.
- **Escenario exitoso principal:**
  1. El usuario selecciona el apartado historial del club.
  2. El sistema recolecta la informacion, actualiza la vista y muestra el historial.

### Caso de Uso 25: Ver historial compartido
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado, en la vista de un club.
- **Escenario exitoso principal:**
  1. El usuario selecciona el apartado historial compartido con el club.
  2. El sistema recolecta la informacion, actualiza la vista y muestra el historial compartido.
- **Escenarios excepcionales:**
  2.a) No se puede visualizar el historial compartido de tu propio club:
  - El sistema informa la imposibilidad y se rechaza la operacion.

### Caso de Uso 26: Ver mi club
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado.
- **Escenario exitoso principal:**
  1. El usuario selecciona el apartado mi club.
  2. El sistema recolecta la informacion, actualiza y muestra la vista mi club, con todos los datos correspondientes.

### Caso de Uso 27: Cambiar contraseña
- **Actor primario:**
- **Precondición:** El usuario está logueado.
- **Escenario exitoso principal:**
  1. El usuario selecciona la opcion editar contraseña.
  2. El sistema solicita la contraseña actual y la nueva contraseña.
  3. El sistema valida las contraseñas ingresadas y las actualiza en la base de datos.
- **Escenarios excepcionales:**
  3.a) La contrseña actual no es correcta:
  - El sistema informa al usuario que la contraseña actual proporcionada es incorrecta.
  3.b) La nueva contraseña coincide con la actual:
  - El sistema informa al usuario que la nueva contraseña no puede ser igual a la actual