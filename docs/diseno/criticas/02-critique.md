# Crítica de la dirección B · `/impeccable critique`

**Fecha:** 24 de noviembre de 2026 · **Objetivo:** `docs/diseno/direcciones/direccion-b.html`
**Herramienta:** Impeccable (`critique`), ejecutado en VS Code sin modificar archivos.
**Puntuación:** 22/40 · «Buena base; falla en reglas del PRD y en disciplina de color».

## Clasificación de los hallazgos

Impeccable recomienda; el `DESIGN.md` decide. Cada hallazgo queda aceptado, aceptado en parte o rechazado, con su razón.

| # | Hallazgo | Gravedad | Decisión | Razón y cómo queda |
| --- | --- | --- | --- | --- |
| C-1 | El staff ve una tarea «No asignada» en «Mis tareas». | P0 | Aceptado | R14: el staff solo ve sus tareas. Las tareas urgentes (R18) se le muestran con la marca «Urgente · abierta a todos», no como «No asignada». |
| C-2 | La tarjeta señal destaca la tarea equivocada. | P0 | Aceptado | Se escribe la regla: la señal muestra la tarea **en ejecución** del staff; si no tiene ninguna, la que **vence primero** (las vencidas antes). |
| C-3 | Se puede salir de una tarea en ejecución y hay dos en ejecución a la vez. | P0 | Aceptado | R19: mientras una tarea está en ejecución no hay «← Mis tareas»; solo hay una tarea en ejecución por persona. |
| C-4 | Faltan observaciones, doble confirmación y «Desliza para finalizar». | P0 | Aceptado | Se agregan el campo de observaciones (opcional) y el control «Desliza para finalizar» (R8, R9, P-04). |
| C-5 | Falta el aviso de «por vencer» arriba de la pantalla. | P0 | Aceptado | R12 es Must: aviso fijo arriba cuando falta menos de 1 hora. |
| C-6 | El lima marca lo que no importa. | P1 | Aceptado en parte | El brandboard dice «Lima = ahora: sesión en curso, estado activo», así que **«En ejecución» se queda en lima**. Sí se quita el lima del título y de las casillas: el lima marca solo lo que está pasando ahora. |
| C-7 | El morado está en todas partes. | P1 | Aceptado | Morado sólido solo en la tarjeta señal y en la acción primaria. El encabezado de la tabla y el contador dejan de ser bloques morados; «Pendiente» pasa a borde. |
| C-8 | Ámbar y coral no están en el brandboard y, con relleno, hacen mucho ruido. | P1 | Aceptado en parte | Se mantienen: la marca no tiene colores de advertencia ni de error, y el producto los necesita (se documenta como supuesto). Los estados pasan a **borde + icono + texto**, como los chips de la marca; solo «Vencida» conserva relleno sólido, porque es lo que el organizador no puede perderse. |
| C-9 | «No asignada» y «Completada» se ven casi iguales. | P1 | Aceptado | «No asignada»: borde punteado blanco y texto blanco (pide acción). «Completada»: texto al 64 % con check, sin borde (ya no pide nada). |
| C-10 | Se mezclan dos dimensiones del estado: ciclo y tiempo. | P1 | Aceptado | La insignia muestra el ciclo (no asignada, pendiente, en ejecución, completada, vencida). «Por vencer» es una marca aparte de tiempo (reloj de arena + minutos restantes). |
| C-11 | La hora de vencimiento es lo más débil de la tarjeta. | P2 | Aceptado | La hora va en Big Shoulders, al mismo peso visual que el título. |
| C-12 | Las tarjetas no parecen tocables y no hay acceso al historial. | P2 | Aceptado | Chevron y estado presionado en la tarjeta; navegación inferior: Mis tareas, Historial, Cuenta (P-37). |
| C-13 | El tablero no tiene grupos, la barra de color no se dibuja y falta el resumen. | P2 | Aceptado | Grupos con título y contador según R13, barra izquierda de color por fila y una fila de conteos por estado arriba. |
| C-14 | Títulos largos en mayúsculas ocupan 3 o 4 líneas. | P2 | Aceptado | Máximo 2 líneas en tarjetas (con «…»); el título completo se lee en el detalle. |
| C-15 | Las horas del mockup no cuadran. | P2 | Aceptado | El brand board usa datos coherentes con una misma hora de referencia. |
| C-16 | El checklist no es accesible (div sin role). | P3 | Aceptado | Regla para el agente: casillas reales (`input type="checkbox"` con `label`). |
| C-17 | El botón deshabilitado es ilegible. | P3 | Aceptado | Deshabilitado = borde gris y texto al 64 %, sin relleno apagado. |
| C-18 | El contador con segundos genera ansiedad. | P3 | Aceptado | Horas y minutos; los segundos solo en los últimos 5 minutos. |
| C-19 | La página del style tile desborda en celulares angostos. | P3 | Rechazado | Afecta solo a la página de comparación, que no se vuelve a usar. El brand board sí se comprueba a 360 y 390 px (criterio del `DESIGN.md`). |

**Resumen:** 19 hallazgos · 16 aceptados · 2 aceptados en parte · 1 rechazado.

## Resultado completo de Impeccable

> Crítica · Dirección B «Credencial de staff»
> La B fue una buena elección y la idea central se mantiene: una tarjeta morada arriba que dice qué hacer ahora y tarjetas cómodas para el pulgar. El problema es que el sistema de color va en contra de la regla de su propia marca. Además, los datos del mockup contradicen el PRD en varios puntos, y eso le pega directo a «Confiable».
> 
> Lo que funciona
> La tarjeta señal responde «¿qué hago ahora?» con título, lugar y avance (2 de 4 pasos). Es el mejor componente de las tres direcciones.
> La hora como cifra grande en el tablero (td.hora, Big Shoulders 24 px). El organizador puede leer la columna «Vence» de un vistazo.
> El checklist es cómodo para el pulgar: cada fila mide 52 px y la casilla 28 px. Debajo del botón deshabilitado se explica por qué no se puede finalizar («Marca los 4 pasos…»), en tú y sin regaños.
> Los estados no dependen solo del color: cada badge lleva icono y texto.
> Hallazgos, de más a menos grave
> P0 · Contradicen el PRD (rompen «Confiable»)
> El staff ve una tarea «No asignada» («Imprimir gafetes faltantes», en Celular · mis tareas). Según R14 el staff solo ve sus tareas, y una tarea sin responsables no es de nadie. Si la idea era mostrar una tarea urgente (R18), su estado es «Urgente · abierta a todos» y necesita su propio tratamiento visual.
> La tarjeta señal elige la tarea equivocada. Destaca «Revisar sonido» (por vencer), mientras la tarea «Reponer agua» ya venció y queda debajo, en una tarjeta normal. Eso invierte el orden de R13. Hay que definir y escribir la regla: ¿la señal es la tarea vencida más antigua, la más próxima a vencer o la que está en ejecución?
> Se puede salir de una tarea en ejecución. La pantalla de ejecutar tiene «← Mis tareas» con 2 de 4 pasos marcados, y R19 lo prohíbe. Lo mismo pasa con la lista: aparecen dos tareas en ejecución a la vez («Revisar sonido» con pasos marcados y «Recibir a los mentores»), algo que R19 hace imposible.
> Falta el campo de observaciones. La descripción del proyecto pide «un campo para colocar observaciones adicionales y el botón de guardar». Tampoco aparece la doble confirmación (R9) ni el «Desliza para finalizar» que se tomó de la C.
> Falta el aviso de «por vencer» en la parte superior (R12). El CSS tiene .aviso{display:none}: se pensó pero no se diseñó, y es un requisito Must.
> P1 · El color va contra «Señal Neón»
> El lima marca lo que no importa. La marca dice que el lima marca «lo único que no puedes perderte». Aquí lo usan «En ejecución» (el estado más tranquilo), las casillas marcadas, el anillo de foco y «DE STAFF» en el título. Lo que de verdad no puedes perderte, una tarea vencida, va en coral. Mi propuesta es reservar el lima para una sola cosa: la acción de finalizar, o la tarea vencida dentro de la señal.
> El morado está en todas partes, así que ya no señala nada. Lo usan la tarjeta señal, el badge «Pendiente», el encabezado sólido de la tabla (th{background:var(--morado)}), el botón primario y el bloque del contador. En la pantalla de ejecutar hay dos señales: el badge ámbar y el bloque morado del contador. El riesgo que anotó la elección se cumple: en la lista caben tres bloques sólidos fuertes en un mismo viewport (morado, coral y lima).
> El ámbar #FFB547 y el coral #FF6B5E no están en el brandboard. Agregarlos para estados es una adaptación válida, pero con relleno sólido son los bloques más ruidosos de la pantalla y se ven más que la marca. Propuesta: para los estados, solo borde y icono; el relleno sólido, solo en la señal.
> «No asignada» y «Completada» se ven casi iguales. La muestra de color incluso los junta en «No asignada / Completada». Son estados opuestos: una tarea sin responsable pide acción del organizador; una completada ya no pide nada. Así como están, el organizador puede pasar por alto una tarea sin asignar.
> Se mezclan dos dimensiones del estado. «Por vencer» depende del tiempo y «En ejecución» del ciclo de la tarea. «Revisar sonido» cumple las dos, pero el badge solo muestra «Por vencer» y se pierde que ya está en ejecución. Mi propuesta: badge para el ciclo y una marca aparte para la urgencia de tiempo.
> P2 · Jerarquía y escaneo
> El «para cuándo» es lo más débil de la tarjeta. «Vence 08:00» va a 13 px y en gris 64 %, mientras el título ocupa 24 px. El brief pide qué, dónde y para cuándo; para alguien que camina con prisa, la hora pesa tanto como el título.
> Las tarjetas no parecen tocables: no tienen chevron ni estado presionado. Tampoco hay forma de llegar a «Historial» (Should).
> El tablero no tiene grupos visibles. Sin separadores por grupo, la fila de 07:30 después de la de 11:00 parece un error de orden. Además, cada <tr> define --c pero ninguna regla de CSS lo usa: la barra de color por fila se pensó y nunca se dibujó. Falta también el resumen general que pide la descripción («resumen general del estado de las tareas»): conteos por estado arriba de la tabla.
> Títulos largos en mayúsculas condensadas. «REVISAR SONIDO Y PROYECTOR PARA LA APERTURA» a 40 px ocupa tres o cuatro líneas en el celular. Conviene probar el peor caso y fijar un límite de líneas.
> Las horas no cuadran. La barra del celular marca 8:22, pero «Venció hace 25 min» (sobre las 08:00) implica 8:25. En un mockup que promete «lo que dice la app es lo que pasó», el detalle importa.
> P3 · Para implementar
> El checklist no es accesible. Usa div tabindex="0" sin role="checkbox" ni aria-checked, así que un lector de pantalla no lo anuncia como casilla. En producción debe ser <input type="checkbox"> con su <label>.
> El botón deshabilitado es ilegible: con opacidad .45, el texto oscuro sobre morado apagado casi desaparece. Mejor un borde con texto en gris que un relleno apagado.
> El contador muestra segundos (00:38:12). Con prisa, los segundos solo agregan ansiedad. Minutos bastan, salvo en los últimos 5.
> La página desborda en celulares angostos. .g2 usa minmax(340px,1fr), y con 32 px de padding a cada lado se desborda en pantallas de 360 a 400 px (Android comunes, iPhone SE). Esto afecta a la página del style tile, no al producto.
> Puntuación (heurísticas, 0–4)
> Heurística	Nota	Motivo
> Visibilidad del estado	3	Estados claros, pero se pierde la doble dimensión (n.º 10)
> Coincidencia con el mundo real	3	Metáfora de gafete y lenguaje en tú
> Control y libertad	1	Contradice R19 y falta la doble confirmación
> Consistencia	2	El morado y el lima cumplen varios papeles a la vez
> Prevención de errores	2	El botón deshabilitado ayuda; faltan R9 y el aviso de conexión (R20)
> Reconocer antes que recordar	3	La señal resuelve «qué hago ahora»
> Eficiencia	3	Pocos toques en el celular; el tablero no tiene resumen
> Estética y minimalismo	2	Demasiados bloques sólidos compiten
> Recuperación de errores	1	No hay estados de error ni sin conexión
> Ayuda	2	Microcopy correcto; no hay estado vacío
> Total	22/40	Buena base; falla en reglas del PRD y en disciplina de color
> Lo que haría primero
> Corregir los datos del mockup según R13, R14 y R19, y escribir la regla que decide qué tarea va en la señal.
> Repartir el color con una función por tono: el morado solo para la señal y la acción primaria, el lima para una sola cosa, y los estados solo con borde e icono.
> Diseñar lo que falta: aviso de por vencer (R12), observaciones, «Desliza para finalizar», aviso sin conexión (R20) y resumen del tablero.
> No modifiqué ni creé archivos del proyecto. Las capturas de escritorio y celular están en el scratchpad: C:\Users\ASUS\AppData\Local\Temp\claude\367f735a5f40c851\963501a5-8d99-4d28-9871-e19f30fb6e29\scratchpad\b-desk.png y ...\b-mob.png.
> 
> Hice la crítica sin dos apoyos:
> 
> Herramientas de la skill: no se encontró en disco el lanzador de contexto ni su guía de crítica. Revisé contra el brief, el PRD, la descripción del proyecto y la nota de elección.
> Captura de celular: el navegador sin interfaz no bajó del todo a 390 px y la captura salió recortada. Los hallazgos de celular salen del código, más que de la imagen.