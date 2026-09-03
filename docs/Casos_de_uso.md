﻿
# <center> Casos de Uso: FutBot </center>
### Índice de Contenidos
  - [Cuenta y sesión](#cuenta-y-sesión)
    - [CU1: Registrar usuario y club](#caso-de-uso-1-registrar-usuario-y-club)
    - [CU2: Iniciar sesión](#caso-de-uso-2-iniciar-sesión)
    - [CU3: Cerrar sesión](#caso-de-uso-3-cerrar-sesión)
    - [CU4: Cambiar contraseña](#caso-de-uso-4-cambiar-contraseña)
  - [Jugadores](#jugadores)
    - [CU5: Crear jugador](#caso-de-uso-5-crear-jugador)
    - [CU6: Ver mis jugadores](#caso-de-uso-6-ver-mis-jugadores)
    - [CU7: Editar comportamiento asignado a un jugador](#caso-de-uso-7-editar-comportamiento-asignado-a-un-jugador)
    - [CU8: Eliminar jugador](#caso-de-uso-8-eliminar-jugador)
  - [Comportamientos](#comportamientos)
    - [CU9: Ver comportamientos](#caso-de-uso-9-ver-comportamientos)
    - [CU10: Crear nuevo comportamiento](#caso-de-uso-10-crear-nuevo-comportamiento)
    - [CU11: Editar comportamiento](#caso-de-uso-11-editar-comportamiento)
    - [CU12: Eliminar comportamiento](#caso-de-uso-12-eliminar-comportamiento)
  - [Club y perfil](#club-y-perfil)
    - [CU13: Ver club de un usuario](#caso-de-uso-13-ver-club-de-un-usuario)
    - [CU14: Ver historial de un club](#caso-de-uso-14-ver-historial-de-un-club)
    - [CU15: Ver historial compartido](#caso-de-uso-15-ver-historial-compartido)
  - [Partidos amistosos](#partidos-amistosos)
    - [CU16: Enviar desafío amistoso](#caso-de-uso-16-enviar-desafío-amistoso)
    - [CU17: Aceptar desafío amistoso](#caso-de-uso-17-aceptar-desafío-amistoso)
    - [CU18: Cancelar desafío amistoso enviado](#caso-de-uso-18-cancelar-desafío-amistoso-enviado)
  - [Partidos (gestión en vivo)](#partidos-gestión-en-vivo)
    - [CU19: Gestionar alineación pre-partido](#caso-de-uso-19-gestionar-alineación-pre-partido)
    - [CU20: Programar sustitución de jugador](#caso-de-uso-20-programar-sustitución-de-jugador)
    - [CU21: Cancelar sustitución de jugador](#caso-de-uso-21-cancelar-sustitución-de-jugador)
    - [CU22: Cambiar comportamiento durante el partido](#caso-de-uso-22-cambiar-comportamiento-durante-el-partido)
    - [CU23: Observar partido como espectador](#caso-de-uso-23-observar-partido-como-espectador)
    - [CU24: Abandonar partido como espectador](#caso-de-uso-24-abandonar-partido-como-espectador)
  - [Ligas](#ligas)
    - [CU25: Crear liga](#caso-de-uso-25-crear-liga)
    - [CU26: Buscar ligas](#caso-de-uso-26-buscar-ligas)
    - [CU27: Unirse a liga privada](#caso-de-uso-27-unirse-a-liga-privada)
    - [CU28: Unirse a liga pública](#caso-de-uso-28-unirse-a-liga-pública)
    - [CU29: Abandonar liga](#caso-de-uso-29-abandonar-liga)
    - [CU30: Cancelar liga](#caso-de-uso-30-cancelar-liga)
    - [CU31: Iniciar liga](#caso-de-uso-31-iniciar-liga)
    - [CU32: Consultar fixture y tabla de posiciones](#caso-de-uso-32-consultar-fixture-y-tabla-de-posiciones)
  - [Ranking](#ranking)
    - [CU33: Consultar ranking global](#caso-de-uso-33-consultar-ranking-global)

## Cuenta y sesión

### Caso de Uso 1: Registrar usuario y club
- **Actor primario:** Usuario visitante
- **Precondición:** El usuario se encuentra en la pantalla de ingreso del sistema.
- **Escenario exitoso principal:**
  1. El usuario selecciona registrarse.
  2. El sistema solicita ingresar nombre de usuario, email, contraseña, avatar y el nombre del club.
  3. El usuario ingresa los datos solicitados y confirma la operación.
  4. El sistema valida los datos y crea la nueva cuenta.
- **Escenarios excepcionales:**
  4. a) El email ingresado ya se encuentra registrado.
  - El sistema informa al usuario que el email proporcionado ya está en uso.

### Caso de Uso 2: Iniciar sesión
- **Actor primario:** Usuario
- **Precondición:** El usuario se registró previamente y no está logueado.
- **Escenario exitoso principal:**
  1. El usuario selecciona iniciar sesión .
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
  1. El usuario selecciona cerrar sesión.
  2. El sistema cierra la sesión del usuario y actualiza la vista al apartado de inicio de sesión.

### Caso de Uso 4: Cambiar contraseña
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado.
- **Escenario exitoso principal:**
  1. El usuario selecciona cambiar contraseña.
  2. El sistema solicita la contraseña actual y la nueva contraseña.
  3. El usuario ingresa la información solicitada.
  4. El sistema valida las contraseñas ingresadas y las actualiza en la base de datos.
- **Escenarios excepcionales:**
  4. a) La contraseña actual no es correcta:
  - El sistema informa al usuario que la contraseña actual proporcionada es incorrecta y solicita reingresar la contraseña.
  4. b) La nueva contraseña coincide con la actual:
  - El sistema informa al usuario que la nueva contraseña no puede ser igual a la actual y solicita ingresar otra contraseña.

### Caso de Uso 5: Cambiar avatar del club
- **Actor primario:** Usuario
- **Precondición:** El usuario esta logueado.
  1. El usuario selecciona cambiar avatar del club.
  2. El sistema solicita elegir la nueva imagen para el avatar. 
  3. El usuario selecciona un nuevo avatar y confirma el cambio.
  4. El sistema valida el avatar, lo actualiza en la base de datos y refleja el cambio en la vista del usuario.
- **Escenarios excepcionales:**
  4. a) El archivo no cumple con los requisitos:
  - El sistema informa error y solicita un nuevo archivo.

## Jugadores

### Caso de Uso 6: Crear jugador
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado en el sistema.
- **Escenario exitoso principal:**
  1. El usuario selecciona crear nuevo jugador.
  2. El sistema solicita el nombre del jugador, número de camiseta y los valores para los atributos PACSS (Power, Agility, Control, Speed, Strength), indicando que hay un valor mínimo y un valor máximo permitido para cada uno, y que que su suma debe ser igual a un valor determinado.
  3. El usuario ingresa la información solicitada y confirma la creación.
  4. El sistema valida que los atributos sumen exactamente el valor determinado, crea al jugador y lo muestra en la plantilla.
- **Escenarios excepcionales:**
  6. a) La suma total de los atributos PACSS es distinta al valor determinado.
  - El sistema informa que la suma total de los atributos de un jugador debe ser igual al valor determinado y solicita modificar los valores de los atributos.
  6. b) Algún atributo posee un valor fuera del rango permitido.
  - El sistema informa que el atributo posee un valor fuera del rango permitido, y solicita modificarlo.

### Caso de Uso 7: Ver mis jugadores
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado en el sistema.
- **Escenario exitoso principal:**
  1. El usuario selecciona visualizar jugadores.
  2. El sistema muestra los jugadores previamente creados.
- **Escenarios excepcionales:**
  2. a) El usuario no posee ningún jugador:
  - El sistema muestra una plantilla vacía.

### Caso de Uso 8: Asignar comportamiento a un jugador
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado en el sistema y tiene al menos un jugador y un comportamiento previamente creado.
- **Escenario exitoso principal:**
  1. El usuario selecciona asignar/reasignar comportamiento a un jugador.
  2. El sistema muestra los comportamientos disponibles.
  3. El usuario selecciona el nuevo comportamiento.
  4. El sistema asigna/reasigna el comportamiento al jugador.

### Caso de Uso 9: Eliminar jugador
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado en el sistema y tiene al menos un jugador previamente creado.
- **Escenario exitoso principal:**
  1. El usuario selecciona eliminar jugador.
  2. El sistema valida que el jugador no esté inscripto en una liga activa ni jugando un partido, advierte sobre la acción irreversible y solicita confirmación.
  3. El usuario confirma la eliminación.
  4. El sistema lo elimina de la base de datos y actualiza la plantilla de jugadores.
- **Escenarios excepcionales:**
  2. a) El jugador se encuentra disputando ligas o partidos activos:
  - El sistema informa que el jugador está en uso y cancela la operación de eliminación.

### Caso de Uso 10: Elegir nueva formación 
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado en el sistema.
- **Escenario exitoso principal:**
  1. El usuario selecciona gestionar formaciones.
  2. El sistema muestra todas las formaciones, indicando cuál está equipada, y la opción equipar.
  3. El usuario selecciona una formación distinta de la que tiene equipada y selecciona la opción equipar.
  4. El sistema desequipa la formación anterior y equipa la formación elegida.

## Comportamientos

### Caso de Uso 11: Ver comportamientos
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado en el sistema.
- **Escenario exitoso principal:**
  1. El usuario selecciona ver comportamientos.
  2. El sistema muestra los comportamientos creados por el usuario.


### Caso de Uso 12: Crear nuevo comportamiento
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado en el sistema.
- **Escenario exitoso principal:**
  1. El usuario selecciona crear nuevo comportamiento.
  2. El sistema solicita escribir código para el comportamiento así como un nombre descriptivo.
  3. El usuario escribe el código del nuevo comportamiento, ingresa un nombre para el mismo y confirma la creación.
  4. El sistema valida el código (sintaxis y seguridad), y guarda el comportamiento.
- **Escenarios excepcionales:**
  4. a) No se ingresa ningún nombre:
  - El sistema informa al usuario que la casilla de nombre está vacía y solicita escribirlo.
  4. b) Se ingresa un nombre ya existente:
  - El sistema informa al usuario que ese nombre de comportamiento ya existe, y solicita cambiarlo.
  4. a) El código contiene errores de sintaxis o usa instrucciones prohibidas.
  - El sistema informa los errores detectados en el editor y solicita corregirlos.

### Caso de Uso 13: Editar comportamiento
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado y tiene al menos un comportamiento previamente creado.
- **Escenario exitoso principal:**
  1. El usuario selecciona editar comportamiento.
  2. El sistema verifica que el comportamiento no esté en uso y permite su edición.
  3. El usuario edita los datos del comportamiento y confirma la edición.
  4. El sistema valida el comportamiento y lo actualiza en la base de datos.
- **Escenarios excepcionales:**
  2. a) El comportamiento se encuentra en uso por un jugador jugando un partido:
  - El sistema informa al usuario que el comportamiento se encuentra en uso y no es posible editarlo.
  4. a) El código contiene errores de sintaxis o usa instrucciones prohibidas.
  - El sistema informa los errores detectados en el editor y solicita corregirlos.

### Caso de Uso 14: Eliminar comportamiento
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado y tiene al menos un comportamiento previamente creado.
- **Escenario exitoso principal:**
  1. El usuario selecciona eliminar comportamiento.
  2. El sistema verifica que el comportamiento no esté en uso y solicita confirmación para eliminar el comportamiento.
  3. El usuario confirma la eliminación del comportamiento.
  4. El sistema elimina el comportamiento elegido. <!-- y lo desasocia de los jugadores que lo tienen asociado -->
- **Escenarios excepcionales:**
  2. a) El comportamiento se encuentra en uso por un jugador jugando un partido:
  - El sistema informa al usuario que el comportamiento se encuentra en uso y no es posible eliminarlo.

## Club y perfil

### Caso de Uso 15: Ver club de un usuario
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado.
- **Escenario exitoso principal:**
  1. El usuario selecciona ver club.
  2. El sistema muestra la vista del club elegido.

### Caso de Uso 16: Ver historial de mi club
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado.
- **Escenario exitoso principal:**
  1. El usuario selecciona el historial.
  2. El sistema actualiza la vista y muestra el historial.

### Caso de Uso 17: Ver historial compartido <!-- revisar caso excepcional)-->
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado.
- **Escenario exitoso principal:**
  1. El usuario selecciona ver historial compartido con el club.
  2. El sistema actualiza la vista y muestra el historial compartido.
- **Escenarios excepcionales:**
  2. a) No se puede visualizar el historial compartido de tu propio club:
  - El sistema informa la imposibilidad y se rechaza la operación.

## Partidos amistosos

### Caso de Uso 18: Enviar desafío amistoso
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado y tiene al menos la mínima cantidad de jugadores para jugar un partido, cada uno con un comportamiento asignado.
- **Escenario exitoso principal:**
  1. El usuario desafía un club del ranking.
  2. El sistema solicita elegir los jugadores titulares y suplentes, cada uno con un comportamiento asignado, y pide confirmar la acción.
  3. El usuario elige sus titulares y suplentes, y confirma el desafío amistoso.
  4. El sistema valida la elección, envía el desafío al club seleccionado y avisa que el desafío fue enviado con éxito.
- **Escenarios excepcionales:**
  4. a) El usuario no elige suficientes jugadores:
  - El sistema advierte que faltan jugadores por elegir, y vuelve a pedir que elija los jugadores faltantes, avisando que los mismos deben tener un comportamiento asignado.

### Caso de Uso 19: Aceptar desafío amistoso
- **Actor primario:** Usuario desafiado
- **Precondición:** 
 El usuario está logueado, tiene al menos la mínima cantidad de jugadores para jugar un partido, cada uno con un comportamiento asignado, y un desafío amistoso pendiente.
- **Escenario exitoso principal:**
  1. El usuario acepta un desafío amistoso.
  2. El sistema solicita elegir los jugadores titulares y suplentes, cada uno con un comportamiento asignado, y pide confirmar la acción.
  3. El usuario elige sus titulares y suplentes, y confirma la aceptación del desafío amistoso.
  4. El sistema valida la elección e inicia el partido.
- **Escenarios excepcionales:**
  4. a) El usuario no elige suficientes jugadores:
  - El sistema advierte que faltan jugadores por elegir, y vuelve a pedir que elija los jugadores faltantes, avisando que los mismos deben tener un comportamiento asignado.

### Caso de Uso 20: Cancelar desafío amistoso enviado
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado, y tiene al menos un desafío enviado que aún no ha sido aceptado.
- **Escenario exitoso principal:**
  1. El usuario selecciona cancelar desafío en un desafío enviado.
  2. El sistema registra la cancelación y elimina el desafío.

### Caso de uso 21: Buscar partido amistoso 
- **Actor primario:** Usuario
- **Actor secundario:** Oponente
- **Precondición:** El usuario está logueado viendo el apartado mi club y tiene al menos la mínima cantidad de jugadores para jugar un partido, cada uno con un comportamiento asignado.
- **Escenario exitoso principal:**
  1. El usuario selecciona buscar partido amistoso.
  2. El sistema solicita elegir los jugadores titulares y suplentes, cada uno con un comportamiento asignado, y pide confirmar la acción.
  3. El usuario elige sus titulares y suplentes, y confirma la acción.
  4. El sistema comienza a buscar un oponente para emparejar con el usuario.  
  5. Aparece un oponente.
  6. El sistema empareja este oponente con el usuario y crea un partido amistoso para ambos.

### Caso de uso 22: Cancelar busqueda
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado y está buscando partido amistoso.
- **Escenario exitoso principal:**
  1. El usuario cancela la búsqueda iniciada.
  2. El sistema finaliza la búsqueda, cancelando el emparejamiento.

## Partidos (gestión en vivo)

### Caso de Uso 22: Gestionar alineación pre-partido
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado, se encuentra en la ventana temporal previa a un partido de su liga y convocó previamente sus 6 jugadores con comportamiento asociado.
- **Escenario exitoso principal:**
  1. El usuario ingresa a la sala de preparación del partido.
  2. El sistema muestra la cuenta regresiva y la plantilla disponible, permitiendo modificar los titulares y jugadores que jugarán el partido, así como sus comportamientos y formación.
  3. El usuario selecciona los titulares y suplentes, asigna los comportamientos y confirma su alineación.
  4. El sistema registra la alineación y muestra la pantalla de espera. <!-- El menú para modificar elementos se cierra al terminar el timer -->

### Caso de Uso 23: Programar sustitución de jugador
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado y visualizando un partido en curso de su club.
- **Escenario exitoso principal:**
  1. El usuario selecciona la opción de realizar un cambio táctico.
  2. El sistema valida que queden cambios, muestra los jugadores titulares, los suplentes disponibles y solicita indicar quién sale y quién entra y un cambio opcional de comportamiento para el nuevo jugador.
  3. El usuario selecciona al jugador saliente, al jugador entrante, pudiendo llegar a elegir nuevo comportamiento para el entrante, y confirma la sustitución.
  4. El sistema registra la solicitud, la prepara para ejecutarse en la próxima pausa reglamentaria (hidratación o entretiempo).
- **Escenarios excepcionales:**
  2. a) El usuario ya agotó sus 3 cambios permitidos:
  - El sistema informa que no quedan cambios disponibles y deniega la operación.
  2. b) Hay una solicitud de cambio previo:
  - El sistema reemplaza la solicitud previa por la actual.
  3. a) El usuario cancela la sustitución:
  - El sistema cierra la ventana de sustitución y vuelve a mostrar el partido.

### Caso de Uso 24: Cancelar sustitución de jugador
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado, visualizando un partido en curso de su club, y tiene una solicitud de sustitución registrada.
- **Escenario exitoso principal:**
  1. El usuario selecciona la opción de cancelar un cambio táctico.
  2. El sistema cancela el cambio.

### Caso de Uso 25: Cambiar comportamiento durante el partido
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado, visualizando un partido en curso de su club.
- **Escenario exitoso principal:**
  1. El usuario selecciona a uno de sus jugadores titulares y elige la opción cambiar comportamiento.
  2. El sistema muestra la lista de comportamientos guardados por el usuario y solicita elegir uno.
  3. El usuario selecciona el nuevo comportamiento y confirma el cambio.
  4. El sistema lo asigna al jugador y actualiza sus acciones para el siguiente "tick" del simulador.

### Caso de Uso 26: Observar partido como espectador
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado, está viendo una liga a la que pertenece y hay al menos un partido en curso en la misma
- **Escenario exitoso principal:**
  1. El usuario selecciona la opción de ver partidos en curso.
  2. El sistema muestra los partidos que se están jugando en vivo.
  3. El usuario selecciona el partido que quiere observar.
  4. El sistema muestra en tiempo real la interfaz 2D de la cancha con sus jugadores y las habilidades de los mismos.

### Caso de Uso 27: Abandonar partido como espectador
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado, visualizando un partido como espectador.
- **Escenario exitoso principal:**
  1. El usuario selecciona la opción dejar de observar.
  2. El sistema actualiza la vista y regresa al apartado de la liga correspondiente al partido que se estaba visualizando.

## Ligas

### Caso de Uso 28: Crear liga
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado en el sistema y tiene al menos 6 jugadores con un comportamiento asignado cada uno.
- **Escenario exitoso principal:**
  1. El usuario ingresa al apartado ligas desde el menú jugar.
  2. El sistema muestra el apartado ligas.
  3. El usuario selecciona la opción crear liga.
  4. El sistema solicita nombre, contraseña, cantidad máxima de clubes, duración de los partidos, así como seleccionar 3 jugadores titulares y 3 jugadores suplentes, cada uno con un comportamiento asignado.
  5. El usuario ingresa los datos solicitados y confirma la creación.
  6. El sistema valida los datos, crea la liga en estado "No iniciada" y anota al club del usuario creador en ella.
- **Escenarios excepcionales:**
  5. a) El usuario cancela la creación de la liga:
  - El sistema regresa al apartado ligas.
  6. a) El usuario omite campos obligatorios:
  - El sistema informa los campos faltantes y solicita completarlos para crear la liga.
  6. b) El usuario elige menos de 6 jugadores:
  - El sistema informa que deben elegirse 6 jugadores para participar en la liga y solicita elegir los jugadores faltantes.

### Caso de Uso 29: Ver ligas disponibles
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado exitosamente.
- **Escenario exitoso principal:**
  1. El usuario ingresa al apartado ligas desde el menú jugar.
  2. El sistema muestra el apartado de ligas.
  3. El usuario selecciona la opción buscar liga.
  4. El sistema muestra las ligas no iniciadas.

### Caso de Uso 30: Unirse a liga privada
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado en el sistema y tiene al menos 6 jugadores con un comportamiento asignado cada uno.
- **Escenario exitoso principal:**
  1. El usuario ingresa al apartado ligas desde el menú jugar.
  2. El sistema muestra el apartado ligas.
  3. El usuario selecciona la opción buscar liga.
  4. El sistema muestra las ligas disponibles.
  5. El usuario selecciona unirse a una liga privada.
  8. El sistema solicita la contraseña de acceso a la liga.
  9. El usuario ingresa la contraseña y confirma.
  10. El sistema valida la contraseña y solicita elegir 3 jugadores titulares y 3 jugadores suplentes, cada uno con un comportamiento asignado, para confirmar la elección.
  11. El usuario selecciona 3 jugadores titulares y 3 jugadores suplentes con un comportamiento asignado cada uno, y confirma la elección.
  12. El sistema valida la elección, inscribe al usuario en la liga y lo dirige hacia ella.
- **Escenarios excepcionales:**
  10. a) La contraseña ingresada por el usuario es incorrecta.
  - El sistema informa que la contraseña es incorrecta y solicita ingresarla nuevamente.
  11. a) El usuario cancela la confirmación para unirse:
  - El sistema vuelve a mostrar las ligas disponibles.
  12. a) El usuario elige menos de 6 jugadores:
  - El sistema informa que deben elegirse 6 jugadores para participar en la liga y solicita elegir los jugadores faltantes.

### Caso de Uso 31: Unirse a liga pública
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado en el sistema y tiene al menos 6 jugadores con un comportamiento asignado cada uno.
- **Escenario exitoso principal:**
  1. El usuario ingresa al apartado ligas desde el menú jugar.
  2. El sistema muestra el apartado de ligas.
  3. El usuario selecciona la opción buscar liga.
  4. El sistema muestra las ligas disponibles.
  3. El usuario selecciona unirse a una liga pública.
  8. El sistema solicita elegir 3 jugadores titulares y 3 jugadores suplentes, cada uno con un comportamiento asignado, para confirmar la elección.
  9. El usuario selecciona 3 jugadores titulares y 3 jugadores suplentes con un comportamiento asignado cada uno, y confirma la elección.
  10. El sistema valida la elección, inscribe al usuario en la liga y lo dirige hacia ella.
- **Escenarios excepcionales:**
  9. a) El usuario cancela la confirmación para unirse:
  - El sistema vuelve a mostrar las ligas disponibles.
  10. a) El usuario eligió menos de 6 jugadores:
  - El sistema informa que deben elegirse 6 jugadores para participar en la liga y solicita elegir los jugadores faltantes.


### Caso de Uso 32: Abandonar liga
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado y se encuentra inscripto en una liga.
- **Escenario exitoso principal:**
  1. El usuario ingresa a los detalles de una liga en la que participa y selecciona la opción abandonar.
  2. El sistema solicita confirmación para darse de baja.
  3. El usuario confirma la operación.
  4. El sistema valida que la liga se encuentre en estado "No iniciada", retira al club del torneo y actualiza la vista de ligas del usuario.
- **Escenarios excepcionales:**
  4. a) La liga ya comenzó o está en curso:
  - El sistema informa que no es posible abandonar una competencia iniciada y bloquea la acción.

### Caso de Uso 33: Cancelar liga
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado y creó una liga, y está en el apartado ligas
- **Escenario exitoso principal:**
  1. El usuario ingresa a la sección mis ligas.
  2. El sistema muestra las ligas asociadas al usuario.
  3. El usuario selecciona una de las ligas creadas por él y elige la opción de cancelar liga.
  4. El sistema solicita confirmación para cancelar la liga.
  5. El usuario confirma la cancelación.
  6. El sistema informa a los usuarios participantes que la liga fue cancelada, los retira de la misma y elimina la liga de la base de datos.
- **Escenarios excepcionales:**
  5. a) El usuario cancela la confirmación:
  - El sistem avuelve a mostrar las ligas creadas por el usuario.
  6. a) La liga comenzó o está en curso:
  - El sistema informa que no es posible eliminar una liga ya iniciada y bloquea la acción.

### Caso de Uso 34: Iniciar liga
- **Actor primario:** Usuario
- **Precondición:** El usuario es dueño de al menos una liga, y está viendo sus ligas creadas.
- **Escenario exitoso principal:**
  1. El usuario ingresa a los detalles de una liga y selecciona la opción iniciar.
  2. El sistema valida la elección, solicita confirmación para iniciar la liga informando la cantidad de participantes actuales.
  3. El usuario confirma la operación.
  4. El sistema cambia el estado de la liga a "Iniciada", calcula el fixture con el orden de los partidos a realizarse, y se actualiza la liga en la base de datos.
- **Escenarios excepcionales:**
  2. a) La liga tiene menos de 3 jugadores:
  - El sistema informa que la cantidad de participantes es insuficiente y cancela la operación, volviendo a mostrar la lista de ligas creadas.
  3. a) El usuario cancela la confirmación:
  - El sistema vuelve a mostrar las ligas creadas por el usuario.

### Caso de Uso 35: Consultar fixture
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado y es miembro de al menos una liga.
- **Escenario exitoso principal:**
  1. El usuario ingresa a los detalles de una liga en la que participa y selecciona la opción de consultar fixture.
  2. El sistema valida que la liga esté iniciada, solicita la información y actualiza la vista del usuario al fixture de la misma.
- **Escenarios excepcionales:**
  2. a) La liga no comenzó:
  - El sistema informa que no es posible visualizar el fixture de una competencia no iniciada y bloquea la acción.

### Caso de Uso 36: Consultar tabla de puntos
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado y es miembro de al menos una liga.
- **Escenario exitoso principal:**
  1. El usuario ingresa a los detalles de una liga en la que participa y selecciona la opción de consultar tabla de puntos.
  2. El sistema valida que la liga esté iniciada, solicita la información y actualiza la vista del usuario a la tabla de puntos de la misma.
- **Escenarios excepcionales:**
  2. a) La liga no comenzó:
  - El sistema informa que no es posible visualizar la tabla de puntos de una competencia no iniciada y bloquea la acción.

## Ranking

### Caso de Uso 37: Consultar ranking global
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado.
- **Escenario exitoso principal:**
  1. El usuario selecciona la opción ranking.
  2. El sistema solicita la información y actualiza la vista del usuario mostrando el ranking de clubes.