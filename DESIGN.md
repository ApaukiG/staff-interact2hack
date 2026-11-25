# DESIGN.md · Staff Interact2Hack

Sistema de diseño **«Credencial Neón»**, versión 1.0 (noviembre de 2026).

Este archivo es la fuente de verdad de cómo se **ve** y se **siente** la herramienta de organización del staff del Interact2Hack. No define funcionalidad: qué hace la app lo dicen el PRD (`docs/prd/PRD.md`) y las specs. Cuando una tarea toque la interfaz, el agente lee este archivo antes de escribir código.

El sistema adapta la identidad visual oficial del evento, el brandboard **«Señal Neón» v1.0**, a una herramienta de trabajo. Lo que viene de la marca se marca como *marca*; lo que se agregó para el producto, como *producto*.

## 1. Cómo se usa este archivo

| Pregunta | Respuesta |
| --- | --- |
| ¿Quién lo lee? | El equipo y el agente. `AGENTS.md` lo referenciará para cualquier tarea visual. |
| ¿Qué decide? | Tokens (color, tipografía, espaciado, bordes, movimiento), componentes, layout, accesibilidad y reglas de estilo. |
| ¿Qué no decide? | Reglas de negocio, textos de la app ni comportamiento. Esos viven en el PRD y en las specs. |
| ¿Cómo se relaciona con una spec? | La spec de interfaz cita tokens y componentes **por su nombre** (`--color-vencida`, «Tarjeta señal»). No copia valores. |
| ¿Cómo se cambia? | Se edita este archivo y el archivo de tokens en el mismo commit, con un mensaje `docs(diseño): …`. El brand board se vuelve a generar desde aquí. |
| ¿Qué pasa si choca con una spec? | Gana la spec en lo que hace la app; gana este archivo en cómo se ve. Si la duda persiste, se pregunta antes de implementar. |
| ¿Y si choca con «Señal Neón»? | Gana este archivo dentro de la app. Cada desviación de la marca está escrita en §4 o en §11 con su razón. |

## 2. Brief

- **Personalidad:** amigable, ágil, confiable (`docs/diseno/brief.md`).
- **Referente:** «Señal Neón», la identidad del Interact2Hack: «una sala oscura a las tres de la mañana y una pantalla encendida». El cliente pidió «la misma identidad visual del Interact2Hack» (P-10).
- **Quién lo usa:** el staff, desde el celular, caminando entre aulas durante los tres días del hackathon, muchas veces de noche y con prisa; los organizadores, desde la computadora, siguiendo el tablero (P-36).
- **Dirección elegida:** B · «Credencial de staff», con «Desliza para finalizar» de la C y filas compactas de la A en escritorio (`docs/diseno/criticas/01-eleccion.md`).

El proceso que llevó a estas decisiones está en `docs/diseno/criticas/`: elección (01), crítica (02, hallazgos C-1 a C-19) y auditoría (03, hallazgos A-1 a A-15).

## 3. Principios

1. **Una sola señal por pantalla.** *(marca)* En cada pantalla hay como máximo un bloque morado sólido: la tarjeta señal o la acción primaria. Si hay dos, ninguna destaca (C-7).
2. **Lima = ahora.** *(marca)* El verde lima marca solo lo que está pasando en este momento: la tarea en ejecución y el anillo de foco. Nunca títulos, fondos grandes ni decoración (C-6).
3. **Qué, dónde y para cuándo.** *(producto)* En cada tarea se leen primero el título, el lugar y la hora de vencimiento. La hora pesa tanto como el título (C-11).
4. **Nunca solo color.** *(producto)* Todo estado lleva texto e icono. El color refuerza; no informa por sí solo.
5. **El negro manda, esquinas rectas.** *(marca)* Fondo negro, profundidad por contraste y bordes, nunca por sombras. Radio 0 en todo, salvo los puntos indicadores.
6. **Lo que dice la app es lo que pasó.** *(producto)* Ningún estado se insinúa: si una tarea está en edición, vencida o sin responsable, la interfaz lo dice con palabras.

## 4. Decisiones de diseño

| Decisión | Por qué |
| --- | --- |
| Tema oscuro único (sin modo claro) | Lo define «Señal Neón» para la app («la app es oscura por diseño»). Además, el staff la usa de noche y con el brillo bajo. |
| Big Shoulders Display para títulos, horas y cifras; Sora para todo lo demás | Son las dos familias de la marca. Big Shoulders hace que la hora se lea de un vistazo; Sora es legible en tamaños de interfaz. |
| Ámbar y coral agregados a la paleta | La marca no tiene colores de advertencia ni de error, y el producto necesita «por vencer» y «vencida» (R11, R12). Se eligieron con alto contraste sobre negro (§8). `[SUPUESTO S-D1]` |
| Estados con borde + icono + texto; solo «Vencida» con relleno sólido | Los bloques sólidos de todos los estados competían con la tarjeta señal (C-8). «Vencida» es lo único que el organizador no puede perderse (R11, R13). |
| La insignia muestra el ciclo de la tarea; «por vencer» y «urgente» son marcas aparte | Una tarea puede estar en ejecución y por vencer a la vez: son dos dimensiones (C-10). |
| Tarjetas en celular, filas en escritorio | El staff ve pocas tareas y las toca con el pulgar; el organizador ve muchas y necesita compararlas (dirección A). Hasta 640 px, el tablero también se ve en tarjetas compactas (A-9). |
| «Desliza para finalizar» en vez de botón + pop-up | Resuelve la doble confirmación (R9, P-35) en un solo gesto y evita cerrar una tarea por un toque accidental mientras se camina. |
| Bordes de control con 3:1 | El borde al 14 % de la marca no separa las tarjetas del fondo (1.37:1, A-2). El 14 % queda solo como separador decorativo. |
| Sin librerías de componentes | El sistema es pequeño; las variables CSS bastan y la app no hereda el aspecto genérico de un framework. |

## 5. Tokens

Todos los tokens vivirán en `src/styles/tokens.css`, dentro de `:root`. Ningún otro archivo escribe un color, una fuente o un tamaño literal. Los colores con transparencia de la marca se fijan como hexadecimales sólidos ya mezclados sobre el fondo, para que el contraste calculado sea el real.

### 5.1 Color

**Base**

| Token | Valor | Origen | Uso |
| --- | --- | --- | --- |
| `--color-fondo` | `#050307` | marca (negro) | Fondo de toda pantalla |
| `--color-superficie` | `#0B0612` | marca (tinta) | Tarjetas, paneles, campos, avisos |
| `--color-texto` | `#FFFFFF` | marca | Texto principal |
| `--color-texto-suave` | `#A5A4A6` | marca (blanco 64 %) | Texto secundario, etiquetas de campo, «Completada» |
| `--color-borde` | `#28262A` | marca (blanco 14 %) | Separadores decorativos (filas, listas). Nunca como único límite de un control |
| `--color-borde-control` | `#69686A` | producto (blanco 40 %) | Borde de tarjetas, campos, casillas y botones secundarios (A-2) |
| `--color-acento` | `#A46CFB` | marca (morado neón) | Tarjeta señal, botón primario, enlaces |
| `--color-sobre-acento` | `#0B0612` | marca (tinta) | Texto sobre el acento, sobre lima y sobre coral |
| `--color-ahora` | `#5CF000` | marca (lima) | Tarea en ejecución, anillo de foco, punto de la pestaña activa |
| `--color-profundo` | `#5B2BB5` | marca (morado profundo) | Solo rellenos decorativos. **Nunca texto** (2.40:1, A-15) |

**Estados de una tarea (PRD, R4 a R11)**

La insignia muestra el **ciclo** de la tarea:

| Estado | Texto e icono | Borde | Relleno | Icono |
| --- | --- | --- | --- | --- |
| No asignada | `--color-texto` | 2 px punteado `--color-texto` | — | círculo punteado |
| Pendiente | `--color-acento` | 2 px `--color-acento` | — | reloj |
| En ejecución | `--color-ahora` | 2 px `--color-ahora` | — | play |
| Vencida | `--color-sobre-acento` | — | `--color-vencida` `#FF6B5E` | triángulo de alerta |
| Completada | `--color-texto-suave` | — | — | check |

Marcas aparte, que acompañan a la insignia (C-10):

| Marca | Token | Valor | Texto | Icono |
| --- | --- | --- | --- | --- |
| Por vencer (falta menos de 1 hora, R12) | `--color-por-vencer` | `#FFB547` | «Faltan 38 min» | reloj de arena |
| Urgente · abierta a todos (R18) | `--color-vencida` | `#FF6B5E` | «Urgente» | rayo |
| En edición (R17, solo escritorio) | `--color-texto-suave` | `#A5A4A6` | «En edición por Andrés» | candado |

Una tarea eliminada (R21) no se muestra, así que no tiene color.

### 5.2 Tipografía

| Token | Valor |
| --- | --- |
| `--fuente-display` | `"Big Shoulders Display", "Arial Narrow", sans-serif` (pesos 700 y 900) |
| `--fuente-texto` | `"Sora", "Segoe UI", sans-serif` (pesos 400 y 600) |

| Nivel | Fuente | Tamaño / alto de línea | Peso | Uso |
| --- | --- | --- | --- | --- |
| `--texto-cifra` | display | 40 / 36 px | 900 | Contador, conteos del tablero |
| `--texto-titulo` | display | 32 / 30 px (44 / 40 en escritorio) | 900 | Título de pantalla y de la tarea abierta. Mayúsculas |
| `--texto-tarjeta` | display | 24 / 24 px | 900 | Título de tarjeta (máximo 2 líneas, C-14) y hora de vencimiento. Mayúsculas |
| `--texto-destacado` | texto | 17 / 24 px | 600 | Nombre de compañeros, texto de la tarjeta señal |
| `--texto-base` | texto | 16 / 24 px | 400 | Texto general y campos (nunca menos de 16 px en campos, para evitar el zoom del celular) |
| `--texto-dato` | texto | 15 / 20 px | 600 | Lugar, hora y responsables: todo lo que dice «dónde» o «cuándo» (A-6) |
| `--texto-pequeno` | texto | 13 / 20 px | 400 | Ayudas y notas. Es el mínimo absoluto |
| `--texto-kicker` | texto | 13 / 16 px | 600 | Etiquetas en mayúsculas con espaciado de +0,16 em (encima de títulos y grupos) |

Big Shoulders nunca baja de 24 px *(marca)*. Ningún texto baja de 13 px.

### 5.3 Espaciado, bordes y radios

| Token | Valor |
| --- | --- |
| `--espacio-1` … `--espacio-8` | 4, 8, 12, 16, 24, 32, 48, 64 px *(marca, base 4)* |
| `--radio` | 0 *(marca: esquinas rectas)*. Excepción: `--radio-punto` 50 % para los puntos indicadores |
| `--borde-fino` | 1 px sólido (separadores) |
| `--borde-control` | 2 px sólido (tarjetas, campos, insignias, botón secundario) |
| `--borde-estado` | 4 px (barra izquierda de las filas del tablero y de los avisos) |
| `--alto-tactil` | 48 px *(marca: 48 dp en Android)* |
| `--anillo-foco` | 3 px sólido `--color-ahora`, separado 2 px |

### 5.4 Movimiento

| Token | Valor | Uso |
| --- | --- | --- |
| `--duracion-estado` | 200 ms | Cambios al pasar el cursor, al presionar o al marcar una casilla *(marca: «hover y estados 0,2 s»)* |
| `--duracion-panel` | 300 ms | Aparición de avisos y del panel de detalle |
| `--curva` | `cubic-bezier(0.16, 1, 0.3, 1)` | Todas las transiciones *(marca: `--i2h-ease`)* |

Sin rebotes ni animaciones decorativas. El contador cambia sin animación. Con `prefers-reduced-motion: reduce`, todas las duraciones pasan a 0.

## 6. Layout

| Ancho | Comportamiento |
| --- | --- |
| Hasta 640 px (celular del staff) | Una columna. Tareas como Tarjetas de tarea. Navegación inferior con tres destinos: Mis tareas, Historial, Cuenta (P-37). Márgenes laterales `--espacio-4`. |
| 641 a 1024 px | Dos columnas en las listas. El tablero ya se muestra en filas. |
| Más de 1024 px (computadora del organizador) | Contenedor de 1200 px máximo, márgenes `--espacio-6`. El tablero muestra el Resumen del tablero arriba y las filas agrupadas debajo. |

Sin desplazamiento horizontal a 360 px. Las rejillas usan `minmax(min(<ancho>, 100%), 1fr)` (A-4).

## 7. Componentes

### 7.1 Botón

| Variante | Fondo | Texto | Borde |
| --- | --- | --- | --- |
| Primario | `--color-acento` | `--color-sobre-acento` | — |
| Secundario | transparente | `--color-acento` | `--borde-control` `--color-acento` |
| Peligro | transparente | `--color-vencida` | `--borde-control` `--color-vencida` |
| Deshabilitado | transparente | `--color-texto-suave` | `--borde-control` `--color-borde-control` |

Alto mínimo `--alto-tactil`, texto `--texto-destacado`. Un solo botón primario por pantalla, y nunca junto a la tarjeta señal (principio 1). El botón deshabilitado usa `aria-disabled="true"` (sigue siendo enfocable) y su motivo en texto debajo, enlazado con `aria-describedby` (A-10, A-11, C-17).

### 7.2 Campo de formulario

Etiqueta arriba, en `--texto-dato` y `--color-texto-suave`. Campo sobre `--color-superficie`, con `--borde-control` `--color-borde-control` y alto `--alto-tactil`. Error: borde y mensaje en `--color-vencida`, con el mensaje debajo del campo y enlazado con `aria-describedby`.

Variantes del producto:

- **Lugar:** lista desplegable con los lugares que mantiene el administrador; nunca texto libre (P-26).
- **Responsables:** lista con casillas que muestra solo al staff disponible en ese horario (R15). Cada persona lleva su nombre y su franja de disponibilidad.
- **Urgente:** casilla «Esta tarea es urgente (abierta a todo el staff)» (R18).
- **Pasos del checklist:** lista editable con «Agregar paso».
- **Observaciones:** área de texto opcional, al final de la ejecución de una tarea (P-04).

### 7.3 Insignia de estado

Rectángulo sin redondeo, con icono de 16 px + texto en `--texto-dato`, padding `--espacio-1` `--espacio-2` y los colores de §5.1. El texto siempre es visible; el icono es decorativo (`aria-hidden`). Se usa la misma insignia en celular y en escritorio.

### 7.4 Marca de tiempo

Texto en `--texto-dato` con icono, sin borde: «⌛ Faltan 38 min» en `--color-por-vencer` cuando falta menos de 1 hora, o «⚡ Urgente» en `--color-vencida`. Va al lado de la hora de vencimiento, nunca en lugar de la insignia.

### 7.5 Tarjeta de tarea (celular)

Es un enlace a la tarea (A-8). Fondo `--color-superficie`, borde `--borde-control` `--color-borde-control`, padding `--espacio-4`.

- **Fila superior:** Insignia de estado a la izquierda; hora de vencimiento en `--texto-tarjeta` a la derecha.
- **Título:** encabezado `h3` en `--texto-tarjeta`, máximo 2 líneas con «…» (C-14).
- **Línea inferior:** lugar con icono en `--texto-dato` y Marca de tiempo si aplica.
- **Chevron** a la derecha. Al presionar, el borde pasa a `--color-texto` durante `--duracion-estado` (C-12).

El staff solo ve sus tareas y las urgentes; nunca una «No asignada» (C-1).

### 7.6 Tarjeta señal

El único bloque morado sólido de la pantalla «Mis tareas». Fondo `--color-acento`, texto `--color-sobre-acento` sólido (sin opacidad, A-3). Kicker («AHORA · FALTAN 38 MIN») en `--texto-kicker`; título en `--texto-titulo`; lugar y avance («2 de 4 pasos») en `--texto-destacado`. Es un enlace a la tarea.

**Qué tarea muestra (C-2):** la tarea **en ejecución** del staff; si no tiene ninguna, la que **vence primero**, con las vencidas antes. Si no tiene tareas, la tarjeta no aparece.

### 7.7 Ítem de checklist

Una casilla real (`input type="checkbox"`) con su `label`, dentro de un `fieldset` cuyo `legend` dice «Checklist · 2 de 4» (A-1, C-16). Toda la fila es el área táctil (mínimo `--alto-tactil`). Casilla de 28 px con `--borde-control` `--color-borde-control`. Marcada: la casilla toma `--color-texto` con el check en `--color-sobre-acento` (no lima: el lima es solo «ahora», C-6), y el texto pasa a `--color-texto-suave`. Sin tachado, para que siga siendo legible.

### 7.8 Contador

Tiempo hasta el vencimiento en `--texto-cifra`, en horas y minutos («00:38»); los segundos aparecen solo en los últimos 5 minutos (C-18). Toma `--color-por-vencer` cuando falta menos de 1 hora y `--color-vencida` al vencer. Su nombre accesible es una frase («Faltan 38 minutos»); solo se anuncia a 30, 15 y 5 minutos, nunca cada segundo (A-5).

### 7.9 Desliza para finalizar

Control de alto `--alto-tactil` + 8 px, con borde `--borde-control` `--color-acento` y una perilla cuadrada en `--color-acento` que se arrastra hasta el final. Mientras falten pasos está deshabilitado (borde `--color-borde-control`) con el motivo debajo: «Marca los 4 pasos para poder finalizar» (R8). Por accesibilidad, también se activa con teclado (Enter mantenido) y tiene el nombre «Finalizar tarea». Al terminar, aviso de éxito.

### 7.10 Avisos

Bloque sobre `--color-superficie` con barra izquierda de `--borde-estado`, icono y texto en `--texto-base`.

| Tipo | Color de la barra y del icono | Ejemplo | Rol |
| --- | --- | --- | --- |
| Por vencer (R12) | `--color-por-vencer` | «Revisar sonido y proyector vence a las 09:00.» | `status` |
| Error / sin conexión (R20) | `--color-vencida` | «No tienes conexión. Tus cambios no se guardaron.» | `alert` |
| Éxito | `--color-ahora` | «Tarea finalizada. Gracias, Apauki.» | `status` |
| Información | `--color-acento` | «Esta tarea está en edición por Andrés.» | `status` |

El aviso de «por vencer» va fijo arriba de la pantalla, debajo de la barra superior (C-5).

### 7.11 Contacto de compañero

Fila con el nombre en `--texto-destacado` y un enlace «Llamar» (`tel:`) en `--color-acento` con icono de teléfono, área táctil de `--alto-tactil` (P-09).

### 7.12 Navegación inferior (celular)

Tres destinos: Mis tareas, Historial, Cuenta. Texto en `--texto-pequeno` 600 e icono de 24 px. La pestaña activa va en `--color-texto` con un punto `--color-ahora` encima; las inactivas, en `--color-texto-suave` *(marca: navegación por actos)*. Se oculta mientras hay una tarea en ejecución (R19).

### 7.13 Indicador del tablero (Resumen del tablero)

Fila de cinco paneles arriba del tablero, uno por grupo de R13: Vencidas, Por vencer, En ejecución, Sin asignar, Completadas. Cada panel: número en `--texto-cifra` y nombre en `--texto-kicker`. El panel de Vencidas lleva relleno `--color-vencida` si el número es mayor que 0; si es 0, dice «Sin tareas vencidas». Los demás solo con borde.

### 7.14 Fila del tablero (escritorio)

Tabla con `caption` «Tablero de tareas, ordenado por prioridad» (A-14). Columnas: Vence (`--texto-tarjeta`), Tarea, Lugar, Responsables, Estado (Insignia + Marca de tiempo) y Acción. Barra izquierda de `--borde-estado` en el color del estado. Las filas van agrupadas con un título de grupo y su contador, en el orden de R13: vencidas, por vencer, en ejecución, sin asignar y completadas; dentro de cada grupo, la que vence primero arriba (C-13). Una fila en edición muestra la marca «En edición por …» y su botón «Editar» queda deshabilitado (R17).

### 7.15 Estados de pantalla

| Estado | Qué se muestra |
| --- | --- |
| Cargando | Bloques del tamaño de las tarjetas o filas en `--color-superficie`, sin brillo animado. |
| Vacío | Texto que explica qué falta: «No tienes tareas asignadas. Cuando un organizador te asigne una, aparecerá aquí.» |
| Sin conexión | Aviso de error fijo arriba y «Desliza para finalizar» deshabilitado con el motivo (R20). |
| Error | Aviso de error con la acción «Reintentar». |

## 8. Accesibilidad

Contraste calculado con la fórmula de WCAG 2.1.

| Par | Contraste | Mínimo |
| --- | --- | --- |
| `--color-texto` sobre `--color-fondo` | 20.54:1 | 4.5:1 |
| `--color-texto` sobre `--color-superficie` | 20.02:1 | 4.5:1 |
| `--color-texto-suave` sobre `--color-fondo` | 8.27:1 | 4.5:1 |
| `--color-texto-suave` sobre `--color-superficie` | 8.20:1 | 4.5:1 |
| `--color-acento` sobre `--color-fondo` | 5.98:1 | 4.5:1 |
| `--color-acento` sobre `--color-superficie` | 5.83:1 | 4.5:1 |
| `--color-sobre-acento` sobre `--color-acento` | 5.83:1 | 4.5:1 |
| `--color-ahora` sobre `--color-fondo` | 13.61:1 | 4.5:1 |
| `--color-ahora` sobre `--color-superficie` | 13.27:1 | 4.5:1 |
| `--color-sobre-acento` sobre `--color-ahora` | 13.27:1 | 4.5:1 |
| `--color-por-vencer` sobre `--color-fondo` | 11.69:1 | 4.5:1 |
| `--color-por-vencer` sobre `--color-superficie` | 11.39:1 | 4.5:1 |
| `--color-vencida` sobre `--color-fondo` | 7.35:1 | 4.5:1 |
| `--color-vencida` sobre `--color-superficie` | 7.17:1 | 4.5:1 |
| `--color-sobre-acento` sobre `--color-vencida` | 7.17:1 | 4.5:1 |
| `--color-borde-control` sobre `--color-fondo` | 3.71:1 | 3:1 |
| `--color-borde-control` sobre `--color-superficie` | 3.77:1 | 3:1 |
| `--color-acento` (borde) sobre `--color-fondo` | 5.98:1 | 3:1 |
| `--color-ahora` (anillo de foco) sobre `--color-fondo` | 13.61:1 | 3:1 |

Pares que **no** se usan para texto ni para límites de control:

| Par | Contraste | Regla |
| --- | --- | --- |
| `--color-borde` sobre `--color-fondo` | 1.37:1 | Solo separadores decorativos |
| `--color-profundo` sobre `--color-fondo` | 2.40:1 | Nunca texto |
| `--color-ahora` sobre `--color-acento` | 2.28:1 | Por eso el anillo de foco va separado 2 px, sobre el fondo y no sobre el morado |

Además:

- **Foco visible** en todo elemento interactivo: `--anillo-foco` definido en `:focus-visible` global, no por componente (A-7).
- **Áreas táctiles** de al menos 48 × 48 px.
- **Ningún estado depende solo del color**: insignias, marcas y avisos llevan texto e icono (principio 4).
- **Semántica:** casillas reales en el checklist (A-1); tarjetas como enlaces con encabezado `h3` (A-8, A-13); «Volver a mis tareas» como enlace (A-12); tabla con `caption` (A-14).
- **Contador:** nombre accesible en frase y anuncios solo en los cortes (A-5).
- **Texto:** nada que diga «cuándo» o «dónde» baja de 15 px; nada baja de 13 px (A-6).

## 9. Reglas para el agente

**DEBE:**

- Leer este archivo antes de cualquier tarea que toque la interfaz.
- Usar solo los tokens de §5, por su nombre.
- Mostrar cada estado con la Insignia de estado (icono + texto) y la urgencia de tiempo con la Marca de tiempo.
- Mostrar en cada tarea el título, el lugar y la hora de vencimiento, en ese orden de importancia.
- Usar un solo bloque morado sólido por pantalla.
- Usar casillas reales en el checklist y enlaces reales en las tarjetas.
- Ocultar la navegación y el «Volver» mientras haya una tarea en ejecución (R19).
- Probar cada pantalla a 360 px, a 390 px y a 1280 px.

**NO DEBE:**

- Escribir colores, fuentes o tamaños literales fuera del archivo de tokens.
- Usar el lima en títulos, fondos o decoración: solo para «ahora» y el foco.
- Usar `--color-profundo` o `--color-borde` para texto o como único borde de un control.
- Redondear esquinas, agregar sombras en superficies o degradados.
- Agregar animaciones que no estén en §5.4, ni rebotes.
- Instalar librerías de estilos o de componentes.
- Usar Big Shoulders por debajo de 24 px.
- Cambiar textos de la app: vienen de las specs.

## 10. Criterios verificables de diseño

| Id | Criterio | Cómo se verifica |
| --- | --- | --- |
| D-01 | No hay colores hexadecimales fuera del archivo de tokens. | `grep -rnE "#[0-9a-fA-F]{3,8}\b" src --include=*.css --include=*.tsx \| grep -v tokens.css` no devuelve nada. |
| D-02 | No hay `font-family` fuera del archivo de tokens. | `grep -rn "font-family" src \| grep -v tokens.css` no devuelve nada. |
| D-03 | No hay esquinas redondeadas salvo los puntos indicadores. | `grep -rn "border-radius" src \| grep -v tokens.css` solo devuelve usos de `--radio` o `--radio-punto`. |
| D-04 | Toda tarea muestra su estado con texto. | En el navegador, cada Tarjeta de tarea y cada Fila del tablero tiene una Insignia con texto visible. |
| D-05 | La hora de vencimiento y el lugar se ven a 360 px. | Vista de celular de «Mis tareas»: cada tarjeta muestra la hora y el lugar sin cortarse. |
| D-06 | Hay como máximo un bloque morado sólido por pantalla. | Revisar «Mis tareas», el detalle y el tablero: cuenta de elementos con fondo `--color-acento` ≤ 1. |
| D-07 | La tarjeta señal muestra la tarea correcta. | Con datos de prueba (una en ejecución, una vencida, una pendiente), la señal muestra la en ejecución; sin ella, la vencida. |
| D-08 | El tablero ordena vencidas, por vencer, en ejecución, sin asignar y completadas. | Con datos de prueba de los cinco grupos, el orden en pantalla es ese y cada grupo tiene título y contador. |
| D-09 | El checklist usa casillas reales. | En las herramientas del navegador, cada paso es un `input type="checkbox"` con `label`, dentro de un `fieldset` con `legend`. |
| D-10 | No se puede finalizar sin todos los pasos. | Con 2 de 4 pasos marcados, «Desliza para finalizar» está deshabilitado y muestra el motivo. |
| D-11 | Todo elemento interactivo tiene foco visible. | Recorrer la pantalla con Tab: cada elemento muestra el anillo lima. |
| D-12 | Las áreas táctiles miden al menos 48 px. | En las herramientas del navegador, botones, casillas, tarjetas y enlaces miden 48 px o más de alto. |
| D-13 | No hay desplazamiento horizontal a 360 px. | `document.documentElement.scrollWidth` es 360 en una ventana de 360 px. |
| D-14 | Ningún texto baja de 13 px y Big Shoulders no baja de 24 px. | En las herramientas del navegador, el tamaño calculado de todo texto es ≥ 13 px y el de Big Shoulders ≥ 24 px. |
| D-15 | Con movimiento reducido no hay transiciones. | Con `prefers-reduced-motion: reduce` activado en el navegador, las duraciones calculadas son 0. |

## 11. Supuestos de diseño

| Id | Supuesto | Por qué | Estado |
| --- | --- | --- | --- |
| S-D1 | Se agregan ámbar `#FFB547` y coral `#FF6B5E` a la paleta de la marca. | «Señal Neón» no tiene colores de advertencia ni de error, y el PRD necesita «por vencer» y «vencida» (C-8). | `[SUPUESTO]` · validar con el cliente en el Avance 3 |
| S-D2 | Se agrega un borde de control al 40 % de blanco (`#69686A`). | El borde de la marca (14 %) no cumple 3:1 (A-2). | `[SUPUESTO]` · validar con el cliente en el Avance 3 |
| S-D3 | La tarjeta señal elige la tarea en ejecución y, si no hay, la que vence primero. | El cliente no definió qué va primero para el staff; se sigue el orden del tablero (R13, C-2). | `[SUPUESTO]` · validar con el cliente en el Avance 3 |
