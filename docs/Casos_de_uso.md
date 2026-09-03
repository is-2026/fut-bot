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
  1. El usuario abre el apartado mi cuenta y selecciona la opción de cerrar sesión.
  2. El sistema cierra la sesión del usuario y actualiza la vista al apartado de inicio de sesión.

### Caso de Uso 4: Cambiar contraseña
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado.
- **Escenario exitoso principal:**
  1. El usuario abre el apartado mi cuenta.
  2. El sistema muestra las acciones que puede realizar el usuario con su cuenta.
  3. El usuario selecciona la opción cambiar contraseña.
  4. El sistema solicita la contraseña actual y la nueva contraseña.
  5. El usuario ingresa la información solicitada.
  6. El sistema valida las contraseñas ingresadas y las actualiza en la base de datos.
- **Escenarios excepcionales:**
  5. a) El usuario cancela el cambio de contraseña:
  - El sistema vuelve a mostrar el menú de editar perfil.
  6. a) La contraseña actual no es correcta:
  - El sistema informa al usuario que la contraseña actual proporcionada es incorrecta y solicita reingresar la contraseña.
  6. b) La nueva contraseña coincide con la actual:
  - El sistema informa al usuario que la nueva contraseña no puede ser igual a la actual y solicita ingresar otra contraseña.

### Caso de Uso 5: Cambiar avatar del club/usuario
- **Actor primario:** Usuario
- **Precondición:** El usuario esta logueado.
- **Escenario exitoso principal:**
  1. El usuario abre el apartado mi cuenta.
  2. El sistema muestra las acciones que puede realizar el usuario con su cuenta.
  3. El usuario selecciona la opción cambiar avatar.
  4. El usuario selecciona un nuevo avatar para modificar y confirma.
  5. El sistema valida el avatar, actualiza el avatar en la base de datos y refleja el cambio en la vista del usuario.
- **Escenarios excepcionales:**
  4. a) El usuario cancela el cambio de avatar:
  - El sistema vuelve a mostrar el menú de editar perfil.
  5. a) El archivo no cumple con los requisitos:
  - El sistema informa error y solicita un nuevo archivo.

## Jugadores

### Caso de Uso 6: Crear jugador
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado en el sistema.
- **Escenario exitoso principal:**
  1. El usuario entra al apartado mi equipo desde el menú principal.
  2. El sistema muestra los jugadores creados si los hay y la opción crear nuevo jugador.
  3. El usuario selecciona la opción crear nuevo jugador.
  4. El sistema solicita el nombre del jugador, número de camiseta y los valores para los atributos PACSS (Power, Agility, Control, Speed, Strength), con un valor mínimo de 20 y un valor máximo de 100 para cada uno, y avisa que su suma debe ser igual a 300.
  5. El usuario ingresa el nombre, el número de camiseta, asigna los valores a los atributos y confirma la creación.
  6. El sistema valida que los atributos sumen exactamente 300, crea al jugador y lo muestra en la plantilla.
- **Escenarios excepcionales:**
  5. a) El usuario cancela la creación del nuevo jugador:
  - El sistema vuelve a mostrar el menú de jugadores.
  6. a) La suma total de los atributos PACSS es distinta a 300.
  - El sistema informa que la suma total de los atributos de un jugador debe ser de 300.
  6. b) Algún atributo posee un valor fuera del rango permitido (20-100).
  - El sistema informa que el atributo posee un valor fuera del rango permitido.

### Caso de Uso 7: Ver mis jugadores
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado en el sistema.
- **Escenario exitoso principal:**
  1. El usuario entra al apartado mi equipo desde el menú principal.
  2. El sistema muestra los jugadores previamente creados.
- **Escenarios excepcionales:**
  2. a) El usuario no posee ningún jugador:
  - El sistema muestra una plantilla vacía.

### Caso de Uso 8: Asignar comportamiento a un jugador
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado en el sistema y tiene al menos un jugador y un comportamiento previamente creado.
- **Escenario exitoso principal:**
  1. El usuario entra al apartado mi equipo desde el menú principal.
  2. El sistema muestra los jugadores y la opción gestionar formaciones.
  3. El usuario selecciona el jugador al que quiere asignar/reasignar comportamiento.
  4. El sistema muestra la información del jugador y las acciones realizables.
  5. El usuario selecciona la opción asignar comportamiento.
  6. El sistema muestra los comportamientos disponibles.
  7. El usuario elige el nuevo comportamiento.
  8. El sistema asigna el comportamiento al jugador.
- **Escenarios excepcionales:**
  7. a) El usuario cancela la asignación de comportamiento:
  - El sistema vuelve al menú del jugador elegido.


### Caso de Uso 9: Eliminar jugador
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado en el sistema y tiene al menos un jugador previamente creado.
- **Escenario exitoso principal:**
  1. El usuario entra al apartado mi equipo desde el menú principal.
  2. El sistema muestra los jugadores y la opción gestionar formaciones.
  3. El usuario selecciona un jugador.
  4. El sistema muestra la información del jugador y las acciones realizables.
  5. El usuario selecciona la opción eliminar jugador.
  6. El sistema valida que el jugador no esté inscripto en una liga activa ni jugando un partido, advierte sobre la acción irreversible y solicita confirmación.
  7. El usuario confirma la eliminación.
  8. El sistema lo elimina de la base de datos y actualiza la plantilla de jugadores.
- **Escenarios excepcionales:**
  6. a) El jugador se encuentra disputando ligas o partidos activos:
  - El sistema informa que el jugador está en uso y cancela la operación de eliminación.
  7. a) El usuario cancela la eliminación del jugador:
  - El sistema vuelve a mostrar el menú del jugador.

### Caso de Uso 10: Elegir nueva formación 
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado en el sistema.
- **Escenario exitoso principal:**
  1. El usuario entra al apartado mi equipo desde el menú principal.
  2. El sistema muestra los jugadores y la opción gestionar formaciones.
  3. El usuario selecciona la opción gestionar formaciones.
  4. El sistema muestra todas las formaciones, indicando cuál está equipada, y la opción equipar.
  5. El usuario elige una formación distinta de la que tiene equipada y selecciona la opción equipar.
  6. El sistema desequipa la formación anterior y equipa la formación elegida.

## Comportamientos

### Caso de Uso 11: Ver comportamientos
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado en el sistema.
- **Escenario exitoso principal:**
  1. El usuario abre el apartado comportamientos desde el menú principal.
  2. El sistema despliega una lista con los comportamientos creados, y las acciones que puede realizar con ellos.
- **Escenarios excepcionales:**
  2. a) El usuario no posee ningún comportamiento:
  - El sistema muestra una lista vacía.

### Caso de Uso 12: Crear nuevo comportamiento
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado en el sistema.
- **Escenario exitoso principal:**
  1. El usuario abre el apartado comportamientos desde el menú principal.
  2. El sistema despliega una lista con los comportamientos creados si los hay, y las acciones que puede realizar con ellos.
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

### Caso de Uso 13: Editar comportamiento
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado y tiene al menos un comportamiento previamente creado.
- **Escenario exitoso principal:**
  1. El usuario abre el apartado comportamientos desde el menú principal.
  2. El sistema despliega una lista con los comportamientos creados, y las acciones que puede realizar con ellos.
  3. El usuario selecciona el comportamiento que desea cambiar y elige la opción editar.
  4. El sistema verifica que el comportamiento no esté en uso y abre la interfaz de edición del comportamiento.
  5. El usuario edita los datos del comportamiento y confirma la edición.
  6. El sistema verifica que el comportamiento sea válido y lo actualiza en la base de datos.
- **Escenarios excepcionales:**
  4. a) El comportamiento se encuentra en uso por un jugador jugando un partido:
  - El sistema informa al usuario que el comportamiento se encuentra en uso y no es posible editarlo.
  5. a) El usuario cancela la edición del comportamiento:
  - El sistema descarta los cambios y vuelve al comportamiento elegido.
  6. a) El código contiene errores de sintaxis o usa instrucciones prohibidas.
  - El sistema informa los errores detectados en el editor y solicita corregirlos.

### Caso de Uso 14: Eliminar comportamiento
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado y tiene al menos un comportamiento previamente creado.
- **Escenario exitoso principal:**
  1. El usuario abre el apartado comportamientos desde el menú principal.
  2. El sistema despliega una lista con los comportamientos creados y las acciones que puede realizar con ellos.
  3. El usuario selecciona el comportamiento que desea borrar y elige la opción eliminar.
  4. El sistema verifica que el comportamiento no esté en uso y pide confirmación para eliminar el comportamiento.
  5. El usuario confirma la eliminación del comportamiento.
  6. El sistema lo elimina y desasocia el comportamiento de los jugadores que lo tienen guardado.
- **Escenarios excepcionales:**
  4. a) El comportamiento se encuentra en uso por un jugador jugando un partido:
  - El sistema informa al usuario que el comportamiento se encuentra en uso y no es posible eliminarlo.
  5. a) El usuario cancela la eliminación del comportamiento:
  - El sistema vuelve a mostrar el comportamiento elegido.

## Club y perfil

### Caso de Uso 15: Ver club de un usuario
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado.
- **Escenario exitoso principal:**
  1. El usuario selecciona el apartado ranking.
  2. El sistema muestra el ranking de clubes.
  3. El usuario selecciona el club de interés.
  4. El sistema recolecta la información del usuario correspondiente y actualiza a la vista del club.

### Caso de Uso 16: Ver historial de mi club
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado.
- **Escenario exitoso principal:**
  1. El usuario selecciona el apartado mi cuenta.
  2. El sistema muestra las opciones de mi cuenta. 
  3. El usuario selecciona la sección historial.
  4. El sistema recolecta la información, actualiza la vista y muestra el historial.

### Caso de Uso 17: Ver historial compartido (revisar caso excepcional)
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado.
- **Escenario exitoso principal:**
  1. El usuario selecciona el apartado ranking.
  2. El sistema muestra el ranking de clubes.
  3. El usuario selecciona el club de interés.
  4. El sistema muestra la vista del club elegido.
  5. El usuario selecciona el apartado historial compartido con el club.
  6. El sistema recolecta la información, actualiza la vista y muestra el historial compartido.
- **Escenarios excepcionales:**
  5. a) No se puede visualizar el historial compartido de tu propio club:
  - El sistema informa la imposibilidad y se rechaza la operación.

## Partidos amistosos

### Caso de Uso 18: Enviar desafío amistoso privado
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado y tiene al menos seis jugadores, cada uno con un comportamiento asignado.
- **Escenario exitoso principal:**
  1. El usuario abre el ranking desde el menú principal.
  2. El sistema muestra los clubes en el ranking.
  3. El usuario selecciona un club del ranking y elige la opción desafío amistoso privado.
  4. El sistema solicita elegir 3 jugadores titulares y 3 jugadores suplentes, cada uno con un comportamiento asignado, y pide confirmar la acción.
  5. El usuario elige sus titulares y suplentes, y confirma el envío del desafío amistoso privado.
  6. El sistema valida la elección, envía el desafío al usuario del club seleccionado y avisa que el desafío fue enviado con éxito.
- **Escenarios excepcionales:**
  5. a) El usuario cancela el envío del desafío amistoso privado:
  - El sistema vuelve a mostrar el club elegido.
  6. a) El usuario elige menos de 6 jugadores:
  - El sistema avisa que deben elegirse 6 jugadores, y vuelve a pedir que elija 6 jugadores que tengan comportamiento asignado.

### Caso de Uso 19: Aceptar desafío amistoso privado
- **Actor primario:** Usuario desafiado
- **Precondición:** 
 El usuario está logueado, viendo el apartado mi club, y tiene al menos seis jugadores, cada uno con un comportamiento asignado, y un desafío amistoso privado pendiente de aceptar.
- **Escenario exitoso principal:**
  1. El usuario abre la sección desafíos pendientes.
  2. El sistema muestra los desafíos amistosos privados pendientes.
  3. El usuario elige, en un desafío pendiente, la opción aceptar desafío amistoso.
  4. El sistema solicita elegir 3 jugadores titulares y 3 jugadores suplentes, cada uno con un comportamiento asignado, y pide confirmar la acción.
  5. El usuario elige sus titulares y suplentes, y confirma la aceptación del desafío amistoso privado.
  6. El sistema valida la elección, e ingresa a los usuarios al lobby del partido si están conectados, mostrando la cuenta regresiva y la plantilla disponible, permitiendo modificar los titulares y suplentes que jugarán el partido, así como sus comportamientos.
- **Escenarios excepcionales:**
  3. a) El usuario rechaza el desafío amistoso:
  - El sistema elimina el desafío amistoso de la sección desafíos pendientes.
  3. b) El desafio amistoso expiró:
  - El sistema informa que el desafio ya no esta disponible y lo elimina de la seccion pendientes.
  4. a) El usuario decide cancelar la acción:
  - El sistema vuelve a la sección de desafíos pendientes sin eliminar el desafío.

### Caso de Uso 20: Cancelar desafío amistoso privado enviado
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado,  y tiene un desafío enviado que aún no ha sido aceptado.
- **Escenario exitoso principal:**
  1. El usuario abre el apartado jugar.
  2. El sistema muestra las opciones de ver ligas, partido amistoso público, desafíos pendientes y enviados.
  3. El usuario abre la sección desafíos enviados.
  4. El sistema muestra los desafíos amistosos enviados.
  5. El usuario elige, en un desafío enviado, la opción eliminar desafío.
  6. El sistema registra la eliminación y expira el desafío.

### Caso de uso 21: Buscar partido amistoso público
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado viendo el apartado mi club y tiene al menos 6 jugadores, cada uno con un comportamiento asignado.
- **Escenario exitoso principal:**
  1. El usuario abre el apartado jugar.
  2. El sistema muestra las opciones de ver ligas, partido amistoso público, desafíos pendientes y enviados.
  3. El usuario abre la sección partido amistoso público.
  4. El sistema muestra un menú con las opciones buscar partido.
  5. El usuario elige la opción crear desafío amistoso público.
  6. El sistema solicita elegir 3 jugadores titulares y 3 jugadores suplentes, cada uno con un comportamiento asignado, y pide confirmar la acción.
  7. El usuario elige sus titulares y suplentes, y confirma el desafío amistoso público.
  8. El sistema agrega el nuevo desafío al menú de desafíos públicos disponibles.
- **Escenarios excepcionales:**
  7. a) El usuario cancela el inicio de la búsqueda:
  - El sistema regresa al menú con todos los desafíos públicos disponibles.

### Caso de uso 21: Iniciar partido amistoso público
- **Actor primario:** Usuario
- **Actor secundario:** Oponente
- **Precondición:** El usuario está logueado y buscando un partido amistoso público.
- **Escenario exitoso principal:**
  1. Un oponente selecciona la opción de buscar partido amistoso público.
  2. El sistema empareja este oponente contra el usuario, y crea una instancia de partido amistoso para ambos. Los ingresa al lobby del partido si están conectados, mostrando la cuenta regresiva y la plantilla disponible, permitiendo modificar los titulares y suplentes que jugarán el partido, así como sus comportamientos y formaciones.

### Caso de uso 22: Cancelar busqueda
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado y está buscando partido amistoso público.
- **Escenario exitoso principal:**
  1. El usuario cancela la búsqueda de partido amistoso público.
  2. El sistema frena el emparejamiento y devuelve al usuario a la sección partido amistoso público.

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
  1. El usuario ingresa a los detalles de una liga en la que participa y selecciona la opción de abandonar.
  2. El sistema solicita confirmación para darse de baja.
  3. El usuario confirma la operación.
  4. El sistema valida que la liga se encuentre en estado "No iniciada", retira al club del torneo y actualiza la vista de ligas del usuario.
- **Escenarios excepcionales:**
  4. a) La liga ya comenzó o está en curso:
  - El sistema informa que no es posible abandonar una competencia iniciada y bloquea la acción.

### Caso de Uso 33: Cancelar liga
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado y creó una liga
- **Escenario exitoso principal:**
  1. El usuario ingresa al apartado ligas desde el menú principal.
  2. El sistema muestra las ligas asociadas al usuario.
  3. El usuario selecciona la liga creada por él y elige la opción de cancelar liga.
  4. El sistema solicita confirmación para cancelar la liga.
  5. El usuario confirma la cancelación.
  6. El sistema informa a los usuarios participantes que la liga fue cancelada y los retira de la misma.
- **Escenarios excepcionales:**
  6. a) La liga comenzó o está en curso:
  - El sistema informa que no es posible eliminar una liga ya iniciada y bloquea la acción.

### Caso de Uso 34: Iniciar liga
- **Actor primario:** Usuario
- **Precondición:** El usuario es dueño de la liga y la liga posee más de 3 jugadores
- **Escenario exitoso principal:**
  1. El usuario ingresa a los detalles de la liga y selecciona la opción de iniciar.
  2. El sistema solicita confirmación para iniciar la liga informando la cantidad de participantes actuales.
  3. El usuario confirma la operación.
  4. El sistema cambia la liga de estado de "No iniciada" a "Iniciada", calcula el fixture con el orden de los partidos a realizarse, se actualiza la vista de ligas de los participantes.

### Caso de Uso 35: Consultar fixture y tabla de posiciones
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado y es miembro de una liga.
- **Escenario exitoso principal:**
  1. El usuario ingresa a los detalles de una liga en la que participa y selecciona la opción de consultar fixture y tabla de posiciones.
  2. El sistema valida que la liga esté iniciada, solicita la información y actualiza la vista del usuario.
- **Escenarios excepcionales:**
  2. a) La liga no comenzó:
  - El sistema informa que no es posible visualizar el fixture y la tabla de posiciones de una competencia no iniciada y bloquea la acción.

## Ranking

### Caso de Uso 36: Consultar ranking global
- **Actor primario:** Usuario
- **Precondición:** El usuario está logueado.
- **Escenario exitoso principal:**
  1. El usuario selecciona la opción Ranking global.
  2. El sistema solicita la información y actualiza la vista del usuario.