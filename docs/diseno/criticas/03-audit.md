# Auditoría de la dirección B · `/impeccable audit`

**Fecha:** 24 de noviembre de 2026 · **Objetivo:** `docs/diseno/direcciones/direccion-b.html`
**Herramienta:** Impeccable (`audit`), ejecutado en VS Code sin modificar archivos. Contrastes medidos con la fórmula WCAG; celular revisado a 390 px y 360 px.
**Resumen de la herramienta:** 1 crítico · 3 altos · 6 medios · 5 bajos.

## Clasificación de los hallazgos

El archivo auditado es un style tile, así que cada hallazgo aceptado pasa al `DESIGN.md` como token, regla para el agente o criterio verificable.

| # | Hallazgo | Gravedad | Decisión | Cómo queda en el sistema |
| --- | --- | --- | --- | --- |
| A-1 | El checklist no existe para el lector de pantalla (div sin `role`). | Crítico | Aceptado | Casillas reales (`input type="checkbox"` + `label`) dentro de un `fieldset` cuyo `legend` dice «Checklist · 2 de 4». Igual que C-16. |
| A-2 | El borde de las tarjetas no se ve (1.37:1). | Alto | Aceptado | Nuevo token de borde de control con al menos 3:1 sobre el fondo. El borde de 14 % queda solo como separador decorativo. |
| A-3 | La etiqueta de la tarjeta señal no llega a 4.5:1 (4.03:1, 11 px). | Alto | Aceptado | Tinta sólida sobre morado (5.83:1), sin opacidad, y a 13 px como mínimo. |
| A-4 | Desborde horizontal a 360 px por `minmax(340px,1fr)`. | Alto | Aceptado como regla | La página del tile no se vuelve a usar (C-19), pero el patrón no pasa a la app: rejillas con `min(…, 100%)` y criterio verificable sin scroll horizontal a 360 px. |
| A-5 | El contador no es accesible para el lector de pantalla. | Medio | Aceptado | Texto «Faltan 38 minutos» como nombre accesible; solo se anuncia en los cortes de 30, 15 y 5 minutos, junto con el aviso de R12. |
| A-6 | La hora y el lugar van en texto muy chico (11–13 px). | Medio | Aceptado | Nada que diga «cuándo» o «dónde» baja de 15 px. Va con C-11. |
| A-7 | El foco no tiene un estilo uniforme. | Medio | Aceptado | `:focus-visible` global: anillo lima de 3 px con 2 px de separación (13.6:1 sobre negro). |
| A-8 | Las tarjetas de tarea no son accionables. | Medio | Aceptado | Cada tarjeta es un enlace; su nombre accesible es el título, con estado y hora en el texto. Va con C-12. |
| A-9 | El tablero se corta en el celular. | Medio | Aceptado | El organizador usa la computadora (P-36), pero puede consultarlo en el evento: hasta 640 px las filas se muestran como tarjetas compactas. |
| A-10 | El botón deshabilitado no explica por qué. | Medio | Aceptado | Con `aria-disabled="true"` y el motivo enlazado con `aria-describedby`. Se aplica también a «Desliza para finalizar». |
| A-11 | El texto del botón deshabilitado es ilegible (1.96:1). | Bajo | Aceptado | Igual que C-17: borde y texto en gris suave, sin relleno apagado. |
| A-12 | «← Mis tareas» es un `span`. | Bajo | Aceptado | Enlace «Volver a mis tareas», con la flecha en `aria-hidden`. No aparece con una tarea en ejecución (R19, C-3). |
| A-13 | Los títulos de tarea son párrafos. | Bajo | Aceptado | Títulos de tarjeta como encabezados (`h3`) para navegar la lista. |
| A-14 | La tabla no tiene `caption`. | Bajo | Aceptado | «Tablero de tareas, ordenado por prioridad». |
| A-15 | El morado profundo tiene 2.40:1 sobre negro. | Bajo | Aceptado | Se anota en el sistema: solo para rellenos y fondos, nunca para texto. |

**Resumen:** 15 hallazgos · 15 aceptados (A-4 como regla para la app). Ninguno se rechaza: todos son requisitos de accesibilidad que el `DESIGN.md` debe cumplir.

## Resultado completo de Impeccable

> Auditoría · Dirección B: accesibilidad y celular a 390 px
> Medí los contrastes con la fórmula WCAG. Para ver la página a 390 px la cargué en un marco de ese ancho, porque la captura anterior había salido recortada. Así medí desbordes y el tamaño de cada área táctil.
> 
> El archivo es un style tile, así que varios hallazgos importan sobre todo como especificación para la app. Lo indico en cada caso.
> 
> Resumen
> Gravedad	Cantidad	Tema principal
> Crítico	1	El checklist no existe para el lector de pantalla
> Alto	3	Bordes de tarjeta invisibles, etiqueta de la señal bajo 4.5:1, desborde a 360 px
> Medio	6	Contador, texto chico, foco sin estilo propio, tarjetas no accionables, tablero en celular
> Bajo	5	Detalles de semántica y del botón deshabilitado
> Lo que ya está bien:
> 
> lang="es", y el viewport no bloquea el zoom.
> Los iconos llevan aria-hidden y los estados tienen texto, así que no dependen solo del color.
> El texto principal tiene buen contraste: 8.29:1 en el gris suave y 5.98:1 en el morado sobre negro.
> Las áreas táctiles cumplen 44 px.
> No hay animaciones que respetar con prefers-reduced-motion.
> Contraste
> Par	Ratio	Mínimo	Resultado
> Texto gris suave (64 %) / negro	8.29	4.5	✅
> Morado / negro (kicker, «Llamar», botón secundario)	5.98	4.5	✅
> Tinta / morado (señal, encabezado de tabla, botón primario)	5.83	4.5	✅
> Tinta / lima, ámbar y coral (badges)	13.27 / 11.39 / 7.17	4.5	✅
> Blanco / fondo de «Pendiente»	16.09	4.5	✅
> Etiqueta de la señal («AHORA · FALTAN 38 MIN», tinta al 72 % sobre morado, 11 px)	4.03	4.5	❌
> Borde de tarjeta y de «Completada» (blanco 14 %)	1.37	3 (no texto)	❌
> Separadores del checklist (blanco 9 %)	1.18	decorativo	⚠️
> Texto del botón deshabilitado	1.96	exento	⚠️
> Morado profundo / negro	2.40	4.5 si se usa en texto	⚠️
> Hallazgos
> Crítico
> El checklist no existe para el lector de pantalla (WCAG 4.1.2). Cada paso es un div.chk con tabindex="0", pero sin role="checkbox", sin aria-checked y sin manejo de Espacio o Enter. El lector lo anuncia como texto suelto. Que un paso está marcado solo se nota por el relleno lima y el tachado. Y el checklist es la función central del staff (R6, R8). En la app: <input type="checkbox"> con <label>, y el conteo «2 de 4» asociado al grupo (fieldset con su legend).
> Alto
> No se ve el borde de las tarjetas (1.37:1, WCAG 1.4.11). Es lo único que separa una tarjeta de otra y del fondo, y con el brillo bajo de noche las tarjetas se funden. Lo mismo pasa con el borde del badge «Completada». Para llegar a 3:1, el borde necesita alrededor de 40 % de blanco.
> La etiqueta de la tarjeta señal no llega al mínimo (4.03:1, a 11 px, WCAG 1.4.3). Además dice lo más importante de la pantalla: cuánto falta. Hay que quitar la opacidad .72 y usar la tinta sólida (5.83:1).
> Desborde horizontal a 360 px. .g2 usa minmax(340px,1fr).
> A 390 px el contenido mide 326 px y la columna 340, así que invade 14 px del margen derecho: queda 32 px a la izquierda y 18 px a la derecha. Se ve en la captura.
> A 360 px (Android comunes) el borde derecho llega a 372 px y aparece scroll horizontal.
> Se arregla con minmax(min(340px,100%),1fr). Afecta a la página del tile, pero el patrón no debe pasar a la app.
> Medio
> El contador no es accesible. El lector lee 00:38:12 como «cero cero, treinta y ocho, doce» y la etiqueta «Tiempo restante» no está asociada al número. Si en la app se actualiza cada segundo, no debe ir en aria-live: saturaría el lector. Conviene un texto alternativo («Faltan 38 minutos») que se anuncie solo en cortes (30, 15 y 5 min) junto con el aviso de R12.
> La información crítica va en texto muy chico. La hora de vencimiento y el lugar van a 13 px, el kicker a 12 px y la etiqueta de la señal a 11 px. Para leer caminando y de noche, nada que diga «cuándo» o «dónde» debería bajar de 15–16 px.
> El foco no tiene un estilo uniforme. El anillo lima solo está definido para .btn y .chk. El enlace «Llamar» usa el foco del navegador, que es distinto y sobre negro se ve poco. Hay que definir :focus-visible global con el anillo lima (13.6:1 sobre negro; el offset de 2 px lo deja sobre el negro y no sobre el morado, donde bajaría a 2.28:1).
> Las tarjetas de tarea no son accionables. No son <a> ni <button>: ni el teclado ni el lector pueden abrir una tarea. En la app: cada tarjeta es un enlace con el título como nombre accesible, y con el estado y la hora en el texto.
> El tablero se corta en el celular. A 390 px la tabla (min-width:760px) se desplaza en horizontal, y «Responsables», «Estado» y «Detalle» quedan fuera de vista sin ninguna pista visual. El contenedor .desk no tiene tabindex ni role="region" con nombre, así que en navegadores antiguos no se puede desplazar con el teclado. El organizador usa la computadora, pero en pleno evento lo consultará en el celular. Para ≤ 600 px conviene una vista en tarjetas compactas.
> El botón deshabilitado no explica por qué. El texto «Marca los 4 pasos para poder finalizar» no está ligado al botón (aria-describedby), y un botón disabled sale del orden de tabulación. Con teclado, el usuario no encuentra el botón ni sabe por qué falta. Alternativa: aria-disabled="true", que lo deja enfocable y anuncia el motivo.
> Bajo
> Botón deshabilitado ilegible (1.96:1). Está exento de WCAG, pero en la práctica el texto desaparece. Mejor borde y texto en gris suave.
> «← Mis tareas» es un <span>. En la app debe ser un enlace con nombre «Volver a mis tareas»; la flecha va con aria-hidden. Ojo: por R19 no debería existir con una tarea en ejecución.
> Los títulos de tarea son <p>. Dentro del mockup del celular deberían ser encabezados (h3) para navegar la lista con el lector.
> La tabla no tiene <caption>. Le falta un nombre como «Tablero de tareas, ordenado por prioridad». El orden de R13 solo se explica en el párrafo de arriba.
> El morado profundo (2.40:1 sobre negro) solo sirve para rellenos y fondos, nunca para texto. Conviene dejarlo anotado en el sistema.
> Áreas táctiles medidas a 390 px
> Elemento	Tamaño	Resultado
> Paso del checklist	304 × 52 (65 si ocupa dos líneas)	✅
> Casilla visual	28 × 28, dentro de una fila de 52	✅
> Enlace «Llamar»	73 × 44	✅ (justo en el mínimo)
> Botón «Finalizar tarea»	304 × 48	✅
> «Crear tarea» / «Reasignar»	127 × 48 / 118 × 48	✅
> Tarjeta de tarea	no es accionable	❌ (ver n.º 8)
> Orden sugerido
> Checklist con casillas reales (n.º 1).
> Bordes de tarjeta y etiqueta de la señal (n.º 2 y 3): son dos tokens y se resuelven en el sistema de diseño.
> Grid flexible y vista del tablero en el celular (n.º 4 y 9).
> Hora y lugar a 15–16 px, y contador accesible (n.º 5 y 6).
> No modifiqué ni creé archivos del proyecto. Las herramientas de medición y las capturas están en el scratchpad; la de 390 px es C:\Users\ASUS\AppData\Local\Temp\claude\367f735a5f40c851\963501a5-8d99-4d28-9871-e19f30fb6e29\scratchpad\b-390.png.