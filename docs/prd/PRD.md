# PRD · Herramienta de organización del staff del Interact2Hack

**Fuentes:** docs/cliente/preguntas.md (respuestas del cliente, 11 de noviembre de 2026).

> **Nota:** este PRD no se basó en la descripción del proyecto de D2L, que no estaba disponible en `docs/fuentes/`. Se construyó solo con las preguntas del avance 1 y las respuestas del cliente.

## 1. Problema y contexto

Durante el Interact2Hack, los organizadores coordinan al staff de estudiantes por un grupo de WhatsApp. Las tareas se pierden entre decenas de mensajes, nadie sabe con certeza quién hizo qué y los organizadores no ven de un vistazo qué está pendiente. El evento dura tres días (viernes a domingo) y se desarrolla en varios espacios del campus, por lo que la coordinación tiene que ser rápida y móvil.

## 2. Usuarios y perfiles

- **Administrador (organizador):** crea usuarios, tareas y lugares, asigna responsables, ve todas las tareas y supervisa el avance desde un tablero. No ejecuta tareas. Usa principalmente computadora.
- **Staff (estudiante):** ve las tareas que le asignaron, las ejecuta marcando un checklist y las finaliza, ve su historial de tareas realizadas y cambia su contraseña sin intervención del administrador. No ve tareas de otros, no crea ni edita tareas, usuarios ni lugares. Usa principalmente el celular.
- Un usuario tiene un solo perfil: administrador o staff.

## 3. Objetivos y éxito

- Reemplazar el grupo de WhatsApp como canal principal para asignar tareas.
- Que el administrador sepa en todo momento el estado de cada tarea.
- Que cada tarea completada quede registrada con el nombre de quien la ejecutó.
- Éxito: [SUPUESTO] ver «Supuestos y puntos abiertos»; la meta medible se confirmará con el cliente.

## 4. Alcance (MoSCoW)

**Must**
- Inicio de sesión con usuarios creados por el administrador (sin registro abierto).
- Gestión de usuarios: nombre, correo de la universidad, teléfono, perfil y disponibilidad.
- Gestión de tareas: título, fecha y hora de vencimiento, lugar, checklist y responsables.
- Lista de lugares precargada y editable.
- Ejecución de tareas por el staff con checklist obligatorio y doble confirmación.
- Estados de tarea y tablero ordenado por prioridad.
- Aviso de tareas próximas a vencer.
- Recuperación de contraseña por correo.

**Should**
- Contador del tiempo restante en la tarea.
- Tareas urgentes abiertas a todo el staff.
- Contactos de los compañeros asignados con enlace para llamar.
- Historial de tareas del staff.

**Could**
- Evidencia fotográfica al finalizar la tarea.
- Bitácora de acciones.
- Modo demo para capacitación.

**Won't (por ahora)**
- Chat interno.
- Categorías del hackatón.
- Funcionamiento sin conexión.
- Notificaciones push al celular (los avisos son dentro de la app).

## 5. No-alcance

- Gestión de participantes, equipos o jurados del hackatón.
- Mensajería entre usuarios.
- Fotos para redes sociales.
- Sincronización offline.

## 6. Reglas de negocio

- **R1.** No existe registro público: solo el administrador crea usuarios.
- **R2.** Cada usuario tiene un único perfil: administrador o staff.
- **R3.** El sistema arranca con un súper administrador que crea al resto.
- **R4.** Una tarea guardada sin responsables queda en estado «No asignada».
- **R5.** Una tarea con responsables y sin ejecución queda «Pendiente».
- **R6.** Una tarea pasa a «En ejecución» cuando el staff marca el primer ítem del checklist. Abrirla solo para verla no cambia su estado.
- **R7.** Una tarea en ejecución no se puede editar ni eliminar.
- **R8.** Solo se puede finalizar una tarea con todos los ítems del checklist marcados.
- **R9.** Finalizar una tarea exige una doble confirmación.
- **R10.** Si hay varios responsables, basta con que uno la complete; queda registrado su nombre.
- **R11.** Una tarea que pasa su fecha de vencimiento sin completarse queda «Vencida»; el administrador puede reasignarla y cambiar la fecha.
- **R12.** Una tarea está «por vencer» cuando falta menos de 1 hora para su vencimiento y no está completada; se muestra un aviso en la parte superior de la pantalla.
- **R13.** El tablero se ordena: vencidas, por vencer, en ejecución, sin asignar y completadas.
- **R14.** El staff solo ve sus tareas; el administrador ve todas.
- **R15.** Al asignar una tarea solo se muestran los miembros del staff disponibles en ese horario.
- **R16.** Las tareas completadas no se pueden eliminar.
- **R17.** Dos administradores no pueden editar la misma tarea a la vez; se usa un estado «En edición».
- **R18.** Una tarea urgente puede completarla cualquier miembro del staff; se cierra con el primero que la completa.
- **R19.** El staff no puede salir de una tarea en ejecución hasta terminarla.
- **R20.** Sin conexión, el sistema avisa «No tienes conexión» y no permite guardar. No hay modo offline.
- **R21.** Eliminar una tarea no la borra del registro: queda marcada como eliminada y deja de mostrarse.

## 7. Épicas

- **E1 · Acceso y cuentas (Must).** Inicio de sesión, recuperación de contraseña por correo y cambio de contraseña desde el perfil.
- **E2 · Administración de usuarios (Must).** Crear usuarios con perfil y disponibilidad, enviar credenciales por correo y editar disponibilidad.
- **E3 · Gestión de tareas (Must).** Crear, editar y reasignar tareas con lugar, checklist, vencimiento y responsables; marcar como urgentes.
- **E4 · Ejecución de tareas en el celular (Must).** Ver tareas asignadas, ejecutar el checklist, ver el contador y finalizar con doble confirmación.
- **E5 · Tablero del administrador (Must).** Vista única del estado de todas las tareas, ordenada por prioridad, con avisos de vencimiento.
- **E6 · Historial y registro (Should).** Historial del staff, pestaña de completadas y bitácora.

## 8. Supuestos y puntos abiertos

- [SUPUESTO] El evento dura tres días, de viernes a domingo.
- [SUPUESTO] La app usa la identidad visual del Interact2Hack, con los materiales que el cliente compartirá.
- [SUPUESTO] Meta de éxito propuesta: al menos el 90 % de las tareas del evento se asignan y cierran en la app. Pregunta: ¿cómo sabremos que la app funcionó en el evento?
- [SUPUESTO] La disponibilidad del staff se compara con la fecha y hora de vencimiento de la tarea (la tarea no tiene hora de inicio). Pregunta: ¿con qué hora se compara la disponibilidad al asignar?
- [SUPUESTO] Dentro de cada grupo del tablero, la tarea que vence primero va arriba. Pregunta: ¿qué orden prefiere dentro de cada grupo?
- [SUPUESTO] Las tareas urgentes y el contador de tiempo (Should) no entran en el avance funcional del 2 de diciembre. Pregunta: si no entra todo, ¿qué prefiere ver primero?
- Punto abierto: cuántos administradores habrá y cómo se reparten el trabajo. Pregunta: ¿alguno tendrá permisos distintos?
- Punto abierto: registro de presencia del staff durante el evento. Pregunta: ¿hace falta registrar quién llegó cada día, o basta con la disponibilidad?

## 9. Trazabilidad

| Regla | Origen |
| --- | --- |
| R1 | P-13 |
| R2 | P-13, P-38 |
| R3 | P-15 |
| R4 | P-20 |
| R5 | P-20 |
| R6 | P-01 |
| R7 | P-01, P-23 |
| R8 | P-04, P-05 |
| R9 | P-35 |
| R10 | P-03, P-14 |
| R11 | P-02 |
| R12 | P-32 |
| R13 | P-34 |
| R14 | P-25 |
| R15 | P-28 |
| R16 | P-27 |
| R17 | P-24 |
| R18 | P-21 |
| R19 | P-29 |
| R20 | P-39 |
| R21 | P-41 |
