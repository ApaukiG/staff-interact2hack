# Avance 1 · Preguntas al cliente y respuestas

**Proyecto:** Herramienta de organización del staff del Interact2Hack
**Cliente:** Andrés (organizador del Interact2Hack)
**Fecha de la reunión:** 11 de noviembre de 2026
**Fuente de las respuestas:** grabación de la reunión (transcrita). Las respuestas conservan las palabras del cliente, con limpieza mínima de la transcripción.

| # | Pregunta | Respuesta del cliente |
| --- | --- | --- |
| P-01 | ¿Qué pasa si una tarea se está ejecutando y alguien la borra? | «Cuando tú abres la tarea debería cambiar el estado a en ejecución. Y si está en ejecución no debería poderse borrar. Debería haber una restricción: si la tarea está en estado en ejecución no se puede borrar.» El tablero «también debería mostrarme si hay alguna tarea que está en ejecución». |
| P-02 | ¿Qué pasa si una tarea pasa su hora límite? ¿Desaparece o se vuelve más prioritaria? | «Debería aparecer en primer lugar en el tablero, como que esta tarea está vencida y no se ejecutó.» El administrador puede «cambiar la fecha de vencimiento y asignarla a otras personas». |
| P-03 | Si una tarea tiene varios estudiantes asignados, ¿la tienen que completar todos? | «No. Si asignas una tarea a tres estudiantes, aunque cualquiera de los tres la complete, ya está completada. No hace falta que pase por los tres, sino uno de los tres.» |
| P-04 | ¿Hay que completar todos los ítems del checklist para cerrar la tarea? | «Tendrías que darle check a todo. La caja de observaciones sería opcional, pero sí deberías darle clic al botón de finalizar tarea.» |
| P-05 | ¿Qué pasa si hacen clic en «finalizar tarea» sin marcar todo el checklist? | «No debería dejarles. Le debería decir: debes chequear todas estas subtareas antes de guardar.» «Es una verificación obligatoria.» |
| P-06 | ¿Hace falta un mecanismo de evidencia (por ejemplo, una foto)? | «Eso no es indispensable, pero sería chévere. Es como un nice to have, pero no es obligatorio. Si tú quieres subir una evidencia cuando completas la tarea, lo puedes hacer. Pero es opcional.» (Supabase permite subir archivos.) |
| P-07 | ¿Cómo se maneja la contraseña del estudiante? | «Inicialmente el administrador debería ponerle la contraseña, pero cuando el usuario ingresa a su perfil podría cambiarla por la que él quiera.» |
| P-08 | ¿Qué datos se necesitan para crear un usuario? | «Nombre, correo, que debería ser el correo del estudiante de la U, y teléfono.» |
| P-09 | ¿Para qué se usa el teléfono? ¿Habrá un chat dentro de la app? | Chat: «Creo que no, porque ahí sí se complica.» «Que sea solo informativo: abres la tarea y te salen los nombres y los teléfonos» de los compañeros asignados, con «un link de teléfono» para llamar. |
| P-10 | ¿La app debe tener una identidad visual? | «Debería ser con la misma identidad visual del Interact2Hack.» El cliente compartirá una carpeta con los materiales de marca. |
| P-11 | ¿Hace falta un temporizador del tiempo que queda? | «Podrían ponerle, cuando abres la tarea, un contador: te quedan 30 minutos, dependiendo de la fecha de vencimiento. Me parece útil.» |
| P-12 | ¿Las tareas tienen un orden o prioridad para el estudiante? | «No debería haber prioridades, al menos por ahora, todas son igual de importantes. Puedes ir en el orden que quieras.» |
| P-13 | ¿Cómo se crean los usuarios? ¿Hay registro? | «No hay registro. Desde la administración se crean todos los usuarios.» En la sección de administración de usuarios se escoge el perfil: administrador o staff, «pero solo uno de los dos, no podrían ser perfiles compartidos». |
| P-14 | ¿Se debe saber quién completó la tarea? | «Sí. Cualquiera de las tres que la abrió, se registra el nombre de esa persona como la que ejecutó la tarea.» |
| P-15 | ¿Cómo se gestiona el usuario administrador inicial? | «Debería haber un usuario inicial administrativo que me den a mí, y con eso ya puedo crear todos los demás.» |
| P-16 | ¿Qué pasa si alguien olvida la contraseña? | «Una opción de olvidé la contraseña, como en todos los sistemas: pones tu correo y te llega una contraseña temporal.» Aplica a staff y administradores, «sin que intervenga la administración». El administrador también puede cambiarla desde el panel. |
| P-17 | ¿Qué datos tiene una tarea? | Título, fecha y hora de vencimiento, lugar, «el check de la tarea, paso a paso, y el responsable, que puede ser uno o varios estudiantes». |
| P-18 | ¿Cómo se entregan las credenciales a los usuarios? | «Las enviamos en correo con sus credenciales.» También se podría enviar por WhatsApp. |
| P-19 | ¿Hay que incluir las categorías del hackatón (juegos, apps…)? | «No es tan relevante. Lo que necesitamos ahorita es que yo le pueda decir a un estudiante: ándate al aula tal, revisa tal cosa, y te pongo el check de lo que vas a hacer.» |
| P-20 | ¿Qué estados tiene una tarea? | Pendiente, en progreso, completada y vencida, más «no asignada» cuando se guarda sin responsables. «Pendiente es cuando ya tiene responsables.» La tarea pasa a en ejecución «cuando le haces el primer check», no solo al abrirla. |
| P-21 | ¿Se puede marcar una tarea como urgente / abierta a cualquiera? | «Un check que diga esta tarea es urgente. Cuando la marco como urgente, ya es una tarea abierta para todos. El primero que llegue la completa y ya se cierra.» |
| P-22 | ¿Se seguirá usando el grupo de WhatsApp? | «La idea de esto es no usar tanto el grupo de WhatsApp», porque «los mensajes se pierden» y se pierde «el hilo de lo que tenías que hacer». |
| P-23 | ¿El administrador puede editar una tarea que ya se está haciendo? | «Si está en ejecución, no. El rato que ya entras a ejecutar ya no debería cambiar. Se queda bloqueada y no se la puede ni borrar ni editar.» |
| P-24 | ¿Qué pasa si dos administradores editan la misma tarea a la vez? | «No debería poder editarse dos veces en simultáneo. Uno de los dos admins empieza a editar la tarea, el otro admin no debería poder editar.» |
| P-25 | ¿Quién ve qué tareas? | «Yo puedo ver todas las tareas como administrador, las mías o las de los otros organizadores. Los estudiantes solo ven las tareas que les asignan.» |
| P-26 | ¿El lugar es texto libre o una lista? | Una lista precargada, no texto libre. Seguros: Casa Blanca, Salón Azul, el de Da Vinci, el Teatro Calderón de la Barca y el Teatro Shakespeare. Debe haber una opción en la administración para crear aulas u otros lugares. |
| P-27 | ¿Qué pasa con las tareas completadas? | Una pestaña de completadas en el tablero general. «Mejor no borrarlas, necesitamos que queden como registro.» |
| P-28 | ¿Se registra la disponibilidad del staff? | Sí: al crear el usuario, el administrador indica qué días y horas está disponible. Al asignar, solo se ven los disponibles en ese horario. Si alguien no puede ir, avisa fuera del sistema y el administrador cambia su disponibilidad. |
| P-29 | ¿Puede un estudiante salir de una tarea en ejecución para hacer otra? | «Creo que es mejor bloquear: si arrancas la tarea, tienes que terminar.» Si sobra gente asignada, se pide a un organizador que edite la tarea. |
| P-30 | ¿Cómo se capacitará a los usuarios? | Un video tutorial o arrancar la app «en modo demo» con tareas de prueba. La app debería estar lista «tipo enero» para empezar a testear. |
| P-31 | ¿Se puede pagar un plan de Supabase si hace falta? | Sí, un mes durante el evento, si se pasa el límite gratuito. |
| P-32 | ¿Notificaciones por correo? | Mejor dentro de la app: «en la parte superior, que salga: esta tarea está por vencer». |
| P-33 | ¿Cuánto tiempo antes se considera «por vencer»? | «Si falta menos de una hora, debería aparecerte arriba en la pantalla: esta está por vencer.» |
| P-34 | ¿En qué orden aparece el tablero del administrador? | Primero las vencidas (para reasignar), luego las por vencer, luego las en ejecución, luego las sin asignar y por último las terminadas, solo como informativo. |
| P-35 | ¿Hace falta confirmar al marcar una tarea como completada? | «Sí, estaría bien una doble confirmación»: un pop-up de «¿estás seguro?» o un slider de «desliza para confirmar». |
| P-36 | ¿Qué dispositivo usará cada perfil? | Administradores: computadora. Staff: teléfono. «La parte de completar la tarea se vea súper bien y súper clara en el celular.» |
| P-37 | ¿Qué puede hacer el staff por su cuenta? | Ver tareas asignadas, ver su historial de tareas realizadas, ejecutar la tarea y cambiar su contraseña, «sin que intervenga la administración». |
| P-38 | ¿Un administrador también puede completar tareas? | Se dejan separados: administrador y staff no se combinan. |
| P-39 | ¿Qué pasa si no hay internet? | No guardar localmente ni sincronizar («sería muy complicado por ahora»). Si detecta que no hay internet, avisar «no tienes internet» o deshabilitar el botón de guardar. |
| P-40 | ¿Hace falta un log o bitácora de lo que se hace? | «No es un requisito indispensable, pero podría ser.» |
| P-41 | ¿Cómo se eliminan los datos? | No se borran de las tablas, solo se marcan como eliminados. |

## Preguntas sin respuesta clara en la reunión

- Detalle de la «presencia» o asistencia del staff durante el evento (la respuesta se mezcla con la pregunta de internet).
- Cuántos administradores habrá y cómo se reparten el trabajo («no sé muy bien cómo nos vamos a organizar por ahora»).

## Estado de los supuestos del Avance 1

En el documento del Avance 1 cada pregunta tenía un supuesto: lo que haría si el cliente no respondía. Después de la reunión, cada uno quedó así:

- **Confirmado:** el cliente dijo lo mismo.
- **Descartado:** el cliente decidió otra cosa.
- **Pendiente:** no se habló en la reunión o la respuesta no quedó clara.

Ojo: los Id de la primera columna son los de mi documento del Avance 1; los de la última columna son los de la tabla de respuestas de arriba.

| Id (Avance 1) | Mi supuesto | Estado | Respuesta que lo resuelve |
| --- | --- | --- | --- |
| P-01 | Cada usuario tiene un solo perfil. | Confirmado | P-13, P-38 |
| P-02 | Un administrador puede gestionar a cualquier usuario, excepto eliminarse a sí mismo. | Pendiente | No se habló. Sí quedó claro que hay un súper administrador inicial (P-15). |
| P-03 | El usuario eliminado se desactiva y su nombre se conserva en las tareas. | Confirmado | P-41: nada se borra, solo se marca como eliminado. |
| P-04 | Datos del usuario: nombre, correo y perfil. | Descartado | P-08 y P-28: también teléfono y disponibilidad. |
| P-05 | Al crear la cuenta le llega un correo con un enlace para crear su contraseña. | Descartado | P-07 y P-18: el administrador pone la contraseña inicial y se envía por correo; el usuario la cambia después. |
| P-06 | El usuario recupera su contraseña solo, por correo. | Confirmado | P-16 |
| P-07 | Título obligatorio y descripción opcional. | Confirmado en parte | P-17 confirma el título. La descripción no se mencionó: pendiente. |
| P-08 | El lugar se elige de una lista fija que mantiene el administrador. | Confirmado | P-26 |
| P-09 | Si el administrador edita el checklist, los pasos marcados se conservan. | Descartado | P-23: una tarea en ejecución no se puede editar. |
| P-10 | Una tarea completada no se edita ni se elimina. | Confirmado | P-27. Quién puede reabrirla quedó pendiente. |
| P-11 | Basta con marcar el check; no hay evidencia. | Confirmado en parte | P-06: la evidencia es opcional («nice to have»). |
| P-12 | Habrá una opción para duplicar tareas. | Pendiente | No se habló. |
| P-13 | Varios responsables comparten un solo checklist y se registra quién marcó cada paso. | Confirmado en parte | P-03 y P-14: basta con que uno la complete; se registra quién la ejecutó, no cada paso. |
| P-14 | Basta con que un responsable la confirme. | Confirmado | P-03 |
| P-15 | Solo el administrador cambia los responsables. | Confirmado | P-29: si sobra gente, se pide a un organizador que edite la tarea. |
| P-16 | No se validan choques de horario. | Descartado | P-28: al asignar solo aparece el staff disponible en ese horario. |
| P-17 | Cuatro estados: pendiente, en progreso, completada y vencida. | Descartado | P-20 y P-24: se suma «no asignada»; «en ejecución» empieza con el primer check; hay bloqueo de edición. |
| P-18 | Guardar conserva el avance parcial. | Pendiente | P-05 solo dice que no se puede finalizar sin todos los checks. |
| P-19 | La tarea queda cerrada con la confirmación del staff, sin aprobación. | Confirmado | P-35: doble confirmación, sin aprobación del administrador. |
| P-20 | Solo el administrador puede reabrir una tarea. | Pendiente | No se habló. |
| P-21 | «Próxima a vencer» = 1 hora antes. | Confirmado | P-33 |
| P-22 | El tablero muestra conteos, por vencer y vencidas. | Confirmado en parte | P-34 define el orden; P-27 agrega la pestaña de completadas. |
| P-23 | Una tarea vencida se puede completar y queda como tardía. | Descartado | P-02: queda «vencida» y el administrador la reasigna o cambia la fecha. |
| P-24 | Solo aviso visual dentro de la app, sin correos. | Confirmado | P-32 |
| P-25 | Staff en celular, administradores en computadora. | Confirmado | P-36 |
| P-26 | Unos 30 estudiantes, 5 administradores y 50–100 tareas por día. | Pendiente | No se dieron cifras. |
| P-27 | Se necesita conexión; la app avisa si algo no se guardó. | Confirmado | P-39 |
| P-28 | Uso el logo si existe y propongo la paleta y la tipografía. | Descartado | P-10: se sigue la identidad visual del Interact2Hack (brandboard «Señal Neón»). |
| P-29 | Solo esta edición; no se separan eventos. | Pendiente | No se habló. |
| P-30 | Chat, correos, reportes y app instalable quedan fuera. | Confirmado en parte | P-09 (sin chat) y P-32 (sin correos). Reportes y app instalable no se hablaron. |
