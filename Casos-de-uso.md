﻿# Casos de Uso: FutBot


### Caso de Uso 1: Registrar Usuario y Club
- **Actor primario:** Usuario visitante
- **Precondición:** El usuario se encuentra en la pantalla de inicio del sistema.
- **Escenario exitoso principal:**
  1. El usuario selecciona la opción de registrarse.
  2. El sistema solicita nombre de usuario, email, contraseña, avatar y el nombre del club.
  3. El usuario ingresa los datos solicitados y confirma la operación.
  4. El sistema valida los datos, crea la nueva cuenta.
- **Escenarios excepcionales:**
  4. a) El email ingresado ya se encuentra registrado. 
  - El sistema informa al usuario que el email proporcionado ya está en uso.

### Caso de Uso 2: Iniciar sesión
- **Actor primario:** Usuario
- **Precondición:** El usuario se encuentra cargado en el sistema.
- **Escenario exitoso principal:**
  1. El usuario selecciona la opción de iniciar sesión.
  2. El sistema solicita email y contraseña.
  3. El usuario ingresa los datos solicitados y confirma la operación.
  4. El sistema valida los datos e inicia sesión.
- **Escenarios excepcionales:**
  4. a) El email ingresado es incorrecto. 
  - El sistema informa al usuario que el email proporcionado es incorrecto.
  4. b) La contraseña ingresada es incorrecta. 
  - El sistema informa al usuario que la contraseña proporcionada es incorrecta.

### Caso de Uso 3: Crear Jugador
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
 
 ### Caso de Uso 4: Eliminar Jugador
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado y se encuentra en la pantalla de gestión de su plantilla.
- **Escenario exitoso principal:**
  1. El usuario selecciona un jugador de su club y elige la opción de eliminarlo.
  2. El sistema advierte sobre la acción irreversible y solicita confirmación.
  3. El usuario confirma la eliminación.
  4. El sistema valida que el jugador no esté inscripto en una liga activa ni jugando un partido, lo elimina de la base de datos y actualiza la lista.
- **Escenarios excepcionales:**
  4.a) El jugador se encuentra disputando ligas o partidos activos:
  - El sistema informa que el jugador está en uso y cancela la operación de eliminación.



### Caso de Uso 5: Redactar y guardar Comportamiento
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
- **Precondición:** El usuario está logueado
- **Escenario exitoso principal:**
1. El usuario selecciona el comportamiento que desea eliminar.
2. El sistema pide confirmación para eliminar el comportamiento.
3. El usuario confirma la eliminación del comportamiento.
4. El sistema verifica que el comportamiento no este en uso, lo elimina y desasocia el comportamiento de los jugadores que lo tienen guardado.
- **Escenarios Excepcionales:**
4.a) El comportamiento se encuentra en uso por un jugador jugando un partido:
- El sistema informa al usuario que el comportamiento se encuentra en uso y no es posible eliminarlo.

### Caso de Uso 7: Editar comportamiento -> Confirmar
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado
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
  1. El usuario selecciona a uno de sus jugadores en cancha y elige la opción de cambiar su comportamiento.
  2. El sistema muestra la lista de comportamientos guardados por el usuario y solicita elegir uno.
  3. El usuario selecciona el nuevo comportamiento y confirma el cambio.
  4. El sistema valida la existencia del comportamiento, lo asigna al jugador y actualiza sus acciones para el siguiente "tick" del simulador.
- **Escenarios excepcionales:**
  4.a) El comportamiento seleccionado fue eliminado o es inválido:
  - El sistema informa el error y mantiene el comportamiento anterior del jugador.

### Caso de Uso 9: Eliminar Jugador
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado y se encuentra en la pantalla de gestión de su plantilla.
- **Escenario exitoso principal:**
  1. El usuario selecciona un jugador de su club y elige la opción de eliminarlo.
  2. El sistema advierte sobre la acción irreversible y solicita confirmación.
  3. El usuario confirma la eliminación.
  4. El sistema valida que el jugador no esté inscripto en una liga activa ni jugando un partido, lo elimina de la base de datos y actualiza la lista.
- **Escenarios excepcionales:**
  4.a) El jugador se encuentra disputando ligas o partidos activos:
  - El sistema informa que el jugador está en uso y cancela la operación de eliminación.

### Caso de Uso 10: Abandonar Liga
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


### Caso de Uso 11: Jugar amistoso
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado
- **Escenario exitoso principal:**
  1. El usuario acepta desafío amistoso, o envía desafío amistoso y se lo aceptan.
  2. El sistema solicita elegir 3 jugadores titulares y 3 suplentes para el partido.
  3. El usuario selecciona sus 6 jugadores.
  4. El sistema inicia el partido amistoso.


### Caso de uso 12: cancelar liga
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


### Caso de uso 13: observar partido como espectador
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado, pertenece a la liga y hay al menos 1 partido en curso en la liga
- **Escenario exitoso principal:** 
  1. El usuario selecciona la opción de ver partidos en curso.
  2. El sistema muestra los partidos que se están jugando en vivo.
  3. El usuario selecciona el partido que quiere observar
  4. El sistema muestra en tiempo real la interfaz 2D de la cancha con sus jugadores y las habilidades de los mismos.


### Caso de Uso 14: Iniciar liga

- **Actor primario:** Usuario
- **Precondición:** El usuario es dueño de  la liga y la liga posee mas de 3 jugadores

- **Escenario exitoso principal:**
  1. El usuario ingresa a los detalles de la liga  y selecciona la opción de iniciar.
  2. El sistema solicita confirmación para iniciar la liga informando la cantidad de participantes actuales.
  3. El usuario confirma la operación.
  4. El sistema cambia la liga de estado de "No iniciada" a "Iniciada" ,calcula el fixture con el orden de los partidos a realizarse, se actualiza la vista de ligas del los participantes.

### Caso de Uso 15: Eliminar comportamiento
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

