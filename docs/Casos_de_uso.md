﻿# Casos de Uso: FutBot

## Cuenta y sesión

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
  1. El usuario selecciona la opción de iniciar sesión en la pantalla de ingreso del sistema.
  2. El sistema solicita ingresar email y contraseña.
  3. El usuario ingresa los datos solicitados y confirma la operación.
  4. El sistema valida los datos e inicia la sesión.
- **Escenarios excepcionales:**
  4. a) El email ingresado es incorrecto.
  - El sistema informa al usuario que el email proporcionado es incorrecto.
  4. b) La contraseña ingresada es incorrecta.
  - El sistema informa al usuario que la contraseña proporcionada es incorrecta.

### Caso de Uso 3: Cerrar sesión
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado.
- **Escenario exitoso principal:**
  1. El usuario abre el menú de usuario y selecciona la opción de cerrar sesión.
  2. El sistema cierra la sesión del usuario y actualiza la vista al apartado de inicio de sesión.

### Caso de Uso 4: Cambiar contraseña
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado.
- **Escenario exitoso principal:**
  1. El usuario abre el menú de usuario y selecciona la opción editar perfil.
  2. El sistema muestra un menú con la opción cambiar contraseña.
  3. El usuario selecciona la opción cambiar contraseña.
  4. El sistema solicita la contraseña actual y la nueva contraseña.
  5. El usuario ingresa la información solicitada.
  6. El sistema valida las contraseñas ingresadas y las actualiza en la base de datos.
- **Escenarios excepcionales:**
  5. c) El usuario cancela el cambio de contraseña:
  - El sistema vuelve a mostrar el menú de editar perfil.
  6. a) La contraseña actual no es correcta:
  - El sistema informa al usuario que la contraseña actual proporcionada es incorrecta y solicita reingresar la contraseña.
  6. b) La nueva contraseña coincide con la actual:
  - El sistema informa al usuario que la nueva contraseña no puede ser igual a la actual y solicita ingresar otra contraseña.


## Jugadores

### Caso de Uso 5: Crear jugador
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado en el sistema.
- **Escenario exitoso principal:**
  1. El usuario entra al menú de jugadores.
  2. El sistema muestra los jugadores creados si los hay, y la opción crear nuevo jugador.
  3. El usuario selecciona la opción de crear nuevo jugador.
  4. El sistema solicita el nombre del jugador y los valores para los atributos PACSS (Power, Agility, Control, Speed, Strength).
  5. El usuario ingresa el nombre, asigna los valores a los atributos y confirma la creación.
  6. El sistema valida que los atributos sumen exactamente 300, crea al jugador y lo muestra en la plantilla.
- **Escenarios excepcionales:**
  5. a) El usuario cancela la creación del nuevo jugador:
  - El sistema vuelve a mostrar el menú de jugadores.
  6. a) La suma total de los atributos PACSS es distinta a 300.
  - El sistema informa que la suma total de los atributos de un jugador debe ser de 300.
  6. b) Algún atributo posee un valor fuera del rango permitido (20-100).
  - El sistema informa que el atributo posee un valor fuera del rango permitido.

### Caso de Uso 6: Ver mis jugadores
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado en el sistema y tiene al menos un jugador previamente creado.
- **Escenario exitoso principal:**
  1. El usuario entra al apartado de gestión de jugadores.
  2. El sistema muestra los jugadores previamente creados.

### Caso de Uso 7: Editar comportamiento asignado a un jugador
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado en el sistema y tiene al menos un jugador y un comportamiento previamente creado.
- **Escenario exitoso principal:**
  1. El usuario entra al apartado de gestión de jugadores.
  2. El sistema muestra los jugadores disponibles.
  3. El usuario selecciona el jugador a asignar/reasignar comportamiento.
  4. El sistema muestra un menú con la informacion del jugador y las acciones realizables.
  5. El usuario selecciona la opcion editar asignacion de comportamiento.
  6. El sistema muestra los comportamientos disponibles.
  7. El usuario elige el nuevo comportamiento.
  8. El sistema efectua el cambio de comportamiento asociado al jugador.
- **Escenarios excepcionales:**
  7. a) El usuario cancela el cambio de comportamiento:
  - El sistema vuelve al menú del jugador elegido.

### Caso de Uso 8: Eliminar jugador
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado en el sistema y tiene al menos un jugador previamente creado.
- **Escenario exitoso principal:**
  1. El usuario entra al apartado de gestión de jugadores.
  2. El sistema muestra los jugadores disponibles.
  3. El usuario selecciona un jugador.
  4. El sistema muestra un menú con la informacion del jugador y las acciones realizables.
  5. El usuario selecciona la opción eliminar jugador.
  6. El sistema advierte sobre la acción irreversible y solicita confirmación.
  7. El usuario confirma la eliminación.
  8. El sistema valida que el jugador no esté inscripto en una liga activa ni jugando un partido, lo elimina de la base de datos y actualiza la plantilla de jugadores.
- **Escenarios excepcionales:**
  6. a) El jugador se encuentra disputando ligas o partidos activos:
  - El sistema informa que el jugador está en uso y cancela la operación de eliminación.
  7. a) El usuario cancela la eliminación del jugador:
  - El sistema vuelve a mostrar el menú del jugador.

## Comportamientos

### Caso de Uso 9: Ver comportamientos
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado en el sistema.
- **Escenario exitoso principal:**
  1. El usuario abre el menú de comportamientos.
  2. El sistema muestra los comportamientos creados si los hay.

### Caso de Uso 10: Crear nuevo comportamiento
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado en el sistema.
- **Escenario exitoso principal:**
  1. El usuario abre el menú de comportamientos.
  2. El sistema muestra los comportamientos creados si los hay, y la opción crear nuevo comportamiento.
  3. El usuario selecciona la opción crear nuevo comportamiento.
  4. El sistema abre una ventana que presenta el editor de código integrado, una casilla para agregar un nombre descriptivo del nuevo comportamiento y las opciones guardar y cancelar.
  5. El usuario escribe el código del nuevo comportamiento, ingresa un nombre para el mismo y solicita guardarlo.
  6. El sistema valida el código (sintaxis y seguridad), guarda el comportamiento y muestra un mensaje de éxito.
- **Escenarios excepcionales:**
  5. a) No se ingresa ningún nombre:
  - El sistema informa al usuario que la casilla de nombre está vacía y debe escribir un nombre.
  5. b) Se ingresa un nombre ya existente:
  - El sistema informa al usuario que ese nombre de comportamiento ya existe, y solicita cambiarlo.
  6. a) El código contiene errores de sintaxis o usa instrucciones prohibidas.
  - El sistema informa los errores detectados en el editor y solicita corregirlos.

### Caso de Uso 11: Editar comportamiento
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado y tiene al menos un comportamiento previamente creado.
- **Escenario exitoso principal:**
  1. El usuario va al menú de usuario y abre la sección comportamientos.
  2. El sistema despliega una lista con los comportamientos creados.
  3. El usuario selecciona el comportamiento que desea cambiar y elige la opción editar.
  4. El sistema verifica que el comportamiento no esté en uso, lo elimina y abre la interfaz de edición del comportamiento.
  5. El usuario edita los datos del comportamiento y confirma la edición.
  6. El sistema verifica que el comportamiento sea válido y lo actualiza en la base de datos.
- **Escenarios excepcionales:**
  4. a) El comportamiento se encuentra en uso por un jugador jugando un partido:
  - El sistema informa al usuario que el comportamiento se encuentra en uso y no es posible editarlo.
  6. a) El comportamiento no es válido:
  - El sistema informa al usuario que el comportamiento no es válido y pide al usuario actualizarlo.

### Caso de Uso 12: Eliminar comportamiento
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado y tiene al menos un comportamiento previamente creado.
- **Escenario exitoso principal:**
  1. El usuario va al menú de usuario y abre la sección comportamientos.
  2. El sistema despliega una lista con los comportamientos creados.
  3. El usuario selecciona el comportamiento que desea eliminar y elige la opción eliminar.
  4. El sistema verifica que el comportamiento no esté en uso y pide confirmación para eliminar el comportamiento.
  5. El usuario confirma la eliminación del comportamiento.
  6. El sistema lo elimina y desasocia el comportamiento de los jugadores que lo tienen guardado.
- **Escenarios excepcionales:**
  4. a) El comportamiento se encuentra en uso por un jugador jugando un partido:
  - El sistema informa al usuario que el comportamiento se encuentra en uso y no es posible eliminarlo.
  5. a) El usuario cancela la eliminación del comportamiento:
  - El sistema vuelve a mostrar el comportamiento elegido.

## Club y perfil

### Caso de Uso 13: Ver club de un usuario
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado, visualizando el ranking global.
- **Escenario exitoso principal:**
  1. El usuario selecciona el club de interés.
  2. El sistema recolecta la información del usuario correspondiente y actualiza a la vista del club.

### Caso de Uso 14: Ver historial de un club
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado, en la vista de un club.
- **Escenario exitoso principal:**
  1. El usuario selecciona el apartado historial del club.
  2. El sistema recolecta la información, actualiza la vista y muestra el historial.

### Caso de Uso 15: Ver historial compartido
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado, en la vista de un club.
- **Escenario exitoso principal:**
  1. El usuario selecciona el apartado historial compartido con el club.
  2. El sistema recolecta la información, actualiza la vista y muestra el historial compartido.
- **Escenarios excepcionales:**
  2. a) No se puede visualizar el historial compartido de tu propio club:
  - El sistema informa la imposibilidad y se rechaza la operación.

## Partidos amistosos

### Caso de Uso 16: Enviar desafío amistoso
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado
- **Escenario exitoso principal:**
  1. El usuario abre el menú del ranking global.
  2. El sistema muestra los clubes en el ranking global.
  3. El usuario selecciona un club del ranking y elige la opción desafío amistoso.
  4. El sistema solicita confirmar la acción.
  5. El usuario confirma el envío del desafío amistoso.
  4. El sistema envía el desafío al usuario del club seleccionado y avisa que el desafío fue enviado con éxito.
- **Escenarios excepcionales:**
  5. a) El usuario cancela el envío del desafío amistoso:
  - El sistema vuelve a mostrar el club elegido.

### Caso de Uso 17: Aceptar desafío amistoso
- **Actor primario:** Usuario desafiado
- **Precondición:** El usuario está logueado y tiene un desafío pendiente de aceptar.
- **Escenario exitoso principal:**
  1. El usuario abre la sección desafíos pendientes en el menú de usuario.
  2. El sistema muestra los desafíos amistosos pendientes.
  3. El usuario elige, en un desafío pendiente, la opción aceptar desafío amistoso.
  4. El sistema registra la aceptación y establece el partido.
- **Escenarios excepcionales:**
  3. a) El usuario rechaza el desafío amistoso:
  - El sistema elimina el desafío amistoso de la sección desafíos pendientes.

## Partidos (gestión en vivo)

### Caso de Uso 18: Gestionar alineación pre-partido
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado, se encuentra en la ventana temporal previa a un partido de su liga y tiene al menos seis jugadores.
- **Escenario exitoso principal:**
  1. El usuario ingresa a la sala de preparación del partido.
  2. El sistema muestra la cuenta regresiva, la plantilla disponible y solicita elegir 3 titulares, 3 suplentes y sus comportamientos.
  3. El usuario selecciona los titulares y suplentes, asigna los comportamientos y confirma su alineación.
  4. El sistema valida que el tiempo no haya expirado, registra la alineación y muestra la pantalla de espera.
- **Escenarios excepcionales:**
  4. a) El tiempo de la cuenta regresiva expiró antes de la confirmación:
  - El sistema selecciona automáticamente a los primeros 3 jugadores del club como titulares, y los siguientes 3 como suplentes, les asigna sus comportamientos por defecto y registra la alineación.

### Caso de Uso 19: Programar sustitución de jugador
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado y visualizando un partido en curso de su club.
- **Escenario exitoso principal:**
  1. El usuario selecciona la opción de realizar un cambio táctico.
  2. El sistema muestra los jugadores titulares, los suplentes disponibles y solicita indicar quién sale y quién entra.
  3. El usuario selecciona al jugador saliente, al jugador entrante y confirma la sustitución.
  4. El sistema valida que el usuario disponga de cambios restantes (máximo 3) y registra la solicitud (actualizando los cambios restantes) para ejecutarse en la próxima pausa reglamentaria (hidratación o entretiempo).
- **Escenarios excepcionales:**
  4. a) El usuario ya agotó sus 3 cambios permitidos:
  - El sistema informa que no quedan cambios disponibles y deniega la operación.

### Caso de Uso 20: Cancelar sustitución de jugador
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado, visualizando un partido en curso de su club, y tiene al menos una solicitud de sustitución registrada.
- **Escenario exitoso principal:**
  1. El usuario selecciona la opción de cancelar un cambio táctico.
  2. El sistema informa todos los cambios registrados a ejecutarse en la próxima pausa y solicita seleccionar aquel a ser cancelado.
  3. El usuario selecciona el cambio, el sistema cancela la solicitud de sustitución y actualiza los cambios restantes.

### Caso de Uso 21: Cambiar comportamiento durante el partido
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado, visualizando un partido en curso de su club y tiene más de un comportamiento creado.
- **Escenario exitoso principal:**
  1. El usuario selecciona a uno de sus jugadores titulares y elige la opción de cambiar su comportamiento.
  2. El sistema muestra la lista de comportamientos guardados por el usuario y solicita elegir uno.
  3. El usuario selecciona el nuevo comportamiento y confirma el cambio.
  4. El sistema valida la existencia del comportamiento, lo asigna al jugador y actualiza sus acciones para el siguiente "tick" del simulador.
- **Escenarios excepcionales:**
  4. a) El comportamiento seleccionado fue eliminado o es inválido:
  - El sistema informa el error y mantiene el comportamiento anterior del jugador.

### Caso de Uso 22: Observar partido como espectador
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado, pertenece a la liga y hay al menos un partido en curso en la liga
- **Escenario exitoso principal:**
  1. El usuario selecciona la opción de ver partidos en curso.
  2. El sistema muestra los partidos que se están jugando en vivo.
  3. El usuario selecciona el partido que quiere observar
  4. El sistema muestra en tiempo real la interfaz 2D de la cancha con sus jugadores y las habilidades de los mismos.

### Caso de Uso 23: Abandonar partido como espectador
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado, visualizando un partido como espectador.
- **Escenario exitoso principal:**
  1. El usuario selecciona la opción de abandonar el partido como espectador.
  2. El sistema actualiza la vista y regresa al apartado de la liga correspondiente al partido que se estaba visualizando.

## Ligas

### Caso de Uso 24: Crear Liga
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado en el sistema.
- **Escenario exitoso principal:**
  1. El usuario selecciona la opción de crear una nueva liga.
  2. El sistema solicita nombre, contraseña, cantidad máxima de clubes, duración de los partidos y privacidad.
  3. El usuario ingresa los datos solicitados y confirma la creación.
  4. El sistema valida los datos, crea la liga en estado "No iniciada" y anota al club del usuario creador en ella.
- **Escenarios excepcionales:**
  4. a) El usuario omite campos obligatorios:
  - El sistema informa los campos faltantes.

### Caso de Uso 25: Buscar ligas
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado exitosamente.
- **Escenario exitoso principal:**
  1. El usuario selecciona el apartado ligas.
  2. El usuario selecciona la opción de buscar una liga.
  3. El sistema muestra ligas recomendadas y disponibles.
  4. El usuario ingresa los criterios de búsqueda.
  5. El sistema busca las ligas que coinciden con los criterios de búsqueda.
  6. El sistema muestra las ligas.
- **Escenarios excepcionales:**
  3. a) No existen ligas disponibles.
  - El sistema informa que no existen ligas disponibles para buscar.
  6. a) No existen coincidencias de búsqueda.
  - El sistema informa que no se encontraron ligas con las coincidencias que pide el usuario.

### Caso de Uso 26: Unirse a Liga Privada
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado en el sistema.
- **Escenario exitoso principal:**
  1. El usuario selecciona el apartado ligas.
  2. El sistema muestra el apartado de ligas.
  3. El usuario selecciona unirse a una ligas.
  4. El sistema muestra ligas recomendadas y disponibles.
  5. El usuario selecciona una liga en estado "No iniciada" y elige unirse.
  6. El sistema solicita la contraseña de acceso a la liga.
  7. El usuario ingresa la contraseña y confirma.
  8. El sistema valida la contraseña y solicita seleccionar los 6 jugadores para el torneo.
  9. El usuario selecciona a sus 6 jugadores y confirma la inscripción.
  10. El sistema inscribe al usuario en la liga y lo dirige hacia la liga.
- **Escenarios excepcionales:**
  8. a) La contraseña ingresada por el usuario es incorrecta.
  - El sistema informa que la contraseña es incorrecta y solicita ingresarla nuevamente.

### Caso de Uso 27: Unirse a Liga Pública
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado en el sistema.
- **Escenario exitoso principal:**
  1. El usuario selecciona el apartado ligas.
  2. El sistema muestra el apartado de ligas.
  3. El usuario selecciona unirse a una ligas.
  4. El sistema muestra ligas recomendadas y disponibles.
  5. El usuario selecciona una liga en estado "No iniciada" y elige unirse.
  6. El sistema solicita seleccionar los 6 jugadores para el torneo.
  7. El usuario selecciona a sus 6 jugadores y confirma la inscripción.
  8. El sistema inscribe al usuario en la liga y lo dirige hacia la liga.

### Caso de Uso 28: Abandonar Liga
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado y se encuentra inscripto en una liga.
- **Escenario exitoso principal:**
  1. El usuario ingresa a los detalles de una liga en la que participa y selecciona la opción de abandonar.
  2. El sistema solicita confirmación para darse de baja.
  3. El usuario confirma la operación.
  4. El sistema valida que la liga se encuentre en estado "No iniciada", retira al club del torneo y actualiza la vista de ligas del usuario.
- **Escenarios excepcionales:**
  4. a) La liga ya comenzó o está en curso:
  - El sistema informa que no es posible abandonar una competencia iniciada y bloquea la acción.

### Caso de Uso 29: Cancelar liga
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado y creó una liga
- **Escenario exitoso principal:**
  1. El usuario navega al menú de ligas.
  2. El sistema muestra las ligas asociadas al usuario.
  3. El usuario selecciona la liga creada por él y elige la opción de cancelar liga.
  4. El sistema solicita confirmación para cancelar la liga.
  5. El usuario confirma la cancelación.
  6. El sistema informa a los usuarios participantes que la liga fue cancelada y los retira de la misma.
- **Escenarios excepcionales:**
  6. a) La liga comenzó o está en curso:
  - El sistema informa que no es posible eliminar una liga ya iniciada y bloquea la acción.

### Caso de Uso 30: Iniciar liga
- **Actor primario:** Usuario
- **Precondición:** El usuario es dueño de la liga y la liga posee más de 3 jugadores
- **Escenario exitoso principal:**
  1. El usuario ingresa a los detalles de la liga y selecciona la opción de iniciar.
  2. El sistema solicita confirmación para iniciar la liga informando la cantidad de participantes actuales.
  3. El usuario confirma la operación.
  4. El sistema cambia la liga de estado de "No iniciada" a "Iniciada", calcula el fixture con el orden de los partidos a realizarse, se actualiza la vista de ligas de los participantes.

### Caso de Uso 31: Consultar fixture y tabla de posiciones
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado y es miembro de una liga.
- **Escenario exitoso principal:**
  1. El usuario ingresa a los detalles de una liga en la que participa y selecciona la opción de consultar fixture y tabla de posiciones.
  2. El sistema valida que la liga esté iniciada, solicita la información y actualiza la vista del usuario.
- **Escenarios excepcionales:**
  2. a) La liga no comenzó:
  - El sistema informa que no es posible visualizar el fixture y la tabla de posiciones de una competencia no iniciada y bloquea la acción.

## Ranking

### Caso de Uso 32: Consultar ranking global
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado.
- **Escenario exitoso principal:**
  1. El usuario selecciona la opción Ranking global.
  2. El sistema solicita la información y actualiza la vista del usuario.