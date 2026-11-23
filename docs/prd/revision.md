# Revisión del PRD

**Equipo:** Pedro Apauki Guandinango Vinueza · **Fecha:** 23 de noviembre de 2026
**Fuentes:** docs/fuentes/descripcion-proyecto.md y docs/cliente/preguntas.md

## Huecos

| # | Sección | Frase exacta del PRD | Tipo (1–8) | Gravedad | Origen | Qué dicen las fuentes | Corrección |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | 6. Reglas | «R6. Una tarea pasa a "En ejecución" cuando el staff la abre.» | 4 · Contradicción resuelta en silencio | alta | IA | P-01 dice «cuando tú abres la tarea», pero P-20 lo corrige: «cuando le haces el primer check», porque el staff puede abrirla solo para verla. | R6: pasa a «En ejecución» cuando el staff marca el primer ítem del checklist. Abrirla para verla no cambia el estado. |
| 2 | 6. Reglas | «R12. Una tarea está "por vencer" cuando está próxima a su vencimiento» | 2 · Regla vaga o sin cifra | alta | IA | P-33: «si falta menos de una hora». | R12: está «por vencer» cuando falta menos de 1 hora para su vencimiento y no está completada. |
| 3 | 6. Reglas | «R20. Si no hay conexión, el sistema guarda los cambios localmente y los sincroniza después.» | 1 · Supuesto escrito como hecho | alta | IA | P-39: guardar localmente y sincronizar «sería muy complicado por ahora». Solo avisar «no tienes internet» o deshabilitar el botón de guardar. | R20: sin conexión, el sistema avisa «No tienes conexión» y no permite guardar. No hay modo offline. |
| 4 | 6. Reglas | «R21. … en la tabla `tasks` con un campo `deleted_at`.» | 7 · Detalle técnico | media | IA | P-41: no se borran, solo se marcan como eliminados. La tabla y el campo son decisiones técnicas. | R21: eliminar una tarea no la borra del registro; queda marcada como eliminada y deja de mostrarse. |
| 5 | 9. Trazabilidad | La tabla termina en R19; faltan R20 y R21. | 8 · Regla sin trazabilidad | media | IA | P-39 sostiene R20 y P-41 sostiene R21. | Agregar R20 → P-39 y R21 → P-41, y las reglas nuevas. |
| 6 | 3. Objetivos | «el 100 % de las tareas del evento se gestionan en la app y el staff la usa fácilmente.» | 2 · Regla vaga / 1 · Supuesto | media | IA | Las fuentes no dan una meta en cifras. P-22 solo dice «no usar tanto el grupo de WhatsApp». «Fácilmente» no es comprobable. | Pasa a supuestos con métrica propuesta y se pregunta al cliente. |
| 7 | 4. Alcance · Could | «Notificaciones push al celular.» | 3 · Alcance inflado / 1 · Supuesto | baja | IA | P-32: los avisos van «dentro de la app, en la parte superior». Las fuentes no piden push. | Se mueve a Won't: los avisos son solo dentro de la app. |
| 8 | 2. Usuarios | «Staff: ve las tareas que le asignaron, las ejecuta marcando un checklist y las finaliza.» | 6 · Perfil o permiso incompleto | media | IA | P-37: el staff también ve su historial y cambia su contraseña sin intervención del administrador. P-38: el administrador no ejecuta tareas. P-26: solo el administrador crea lugares. | Completar los permisos de cada perfil con lo que puede y no puede hacer. |
| 9 | 6. Reglas | «R13. El tablero se ordena: vencidas, por vencer, en ejecución, sin asignar y completadas.» | 5 · Pregunta abierta desaparecida | baja | IA | P-34 no deja claro el orden dentro de cada grupo (la grabación se entiende mal en esa parte). | Mantener R13 y agregar el orden interno como [SUPUESTO] con pregunta al cliente. |
| 10 | 8. Supuestos | Falta la pregunta sobre la asistencia («presencia») del staff. | 5 · Pregunta abierta desaparecida | baja | IA | En la reunión se preguntó por la presencia del staff, y la respuesta quedó mezclada con el tema de internet. | Agregar como punto abierto con pregunta al cliente. |
| 11 | 4. Alcance · Should | «Tareas urgentes abiertas a todo el staff.» y «Contador del tiempo restante» | 3 · Alcance inflado | media | IA | El cliente pidió ambas (P-11, P-21), pero el avance funcional es el 2 de diciembre y el Must ya es amplio. | Se quedan en Should y no entran al avance funcional del 2 de diciembre. Se declara en supuestos. |
| 12 | 6. Reglas | Falta una regla para la disponibilidad cuando una tarea no tiene horario de inicio. | 1 · Supuesto escrito como hecho | media | IA | P-28: «solo los disponibles en ese horario». P-17: la tarea tiene fecha y hora de vencimiento, pero no de inicio. | [SUPUESTO] La disponibilidad se compara con la fecha y hora de vencimiento de la tarea. Se pregunta al cliente. |

## Para presentar

1. **R6 · Cuándo empieza la ejecución (contradicción resuelta en silencio, alta).**
   - **Qué decía el PRD:** la tarea pasa a «En ejecución» cuando el staff la abre.
   - **Por qué era un problema:** el cliente primero dijo eso (P-01) y luego lo corrigió (P-20): solo cuenta desde el primer check. Con la regla vieja, mirar una tarea la bloqueaba para edición y borrado.
   - **Cómo quedó:** cambia de estado con el primer ítem marcado.
   - **Quién lo encontró:** IA.
2. **R20 · Modo sin conexión (supuesto escrito como hecho, alta).**
   - **Qué decía el PRD:** se guarda localmente y se sincroniza después.
   - **Por qué era un problema:** el cliente dijo lo contrario (P-39). Además, sumaba un alcance técnico grande que no cabe en el avance funcional.
   - **Cómo quedó:** solo un aviso de «No tienes conexión» y no deja guardar.
   - **Quién lo encontró:** IA.
3. **R12 · «Por vencer» sin cifra (regla vaga, alta).**
   - **Qué decía el PRD:** «próxima a su vencimiento».
   - **Por qué era un problema:** no se puede probar.
   - **Cómo quedó:** menos de 1 hora, como dijo el cliente (P-33).
   - **Quién lo encontró:** IA.

## Preguntas para el cliente

1. Cuando un administrador asigna una tarea, ¿con qué hora se compara la disponibilidad del staff: la de vencimiento, o la tarea debe tener también una hora de inicio?
2. ¿Cómo sabremos que la app funcionó en el evento? Por ejemplo: «al menos el 90 % de las tareas se asignaron y cerraron en la app» o «ninguna tarea se asignó por WhatsApp».
3. ¿Cuántos administradores habrá en el evento y si alguno tendrá permisos distintos (por ejemplo, solo crear usuarios)?
4. Dentro de cada grupo del tablero (vencidas, por vencer…), ¿en qué orden van: la que vence primero arriba o la más reciente arriba?
5. Sobre la «presencia» del staff, ¿necesitan registrar quién llegó al evento cada día, o basta con la disponibilidad que carga el administrador?
6. Para el avance funcional, ¿qué prefiere ver primero si no entra todo: las tareas urgentes o el contador de tiempo?
