# DESIGN SYSTEM v2 — App Cursos
## "Taller de Resultados"

> Destino: `docs/DESIGN_SYSTEM.md` (reemplaza la v1 por completo)
> Estado: propuesta v2, pendiente de aprobación del Product Owner.
> Fuente de verdad visual. Si un componente contradice este documento, el componente está mal.

---

## 1. Concepto y personalidad de marca

Esto no es una plataforma de cursos: es **un taller donde entras con un problema y sales con una pieza terminada**. El comprador es un dueño de negocio de 35 a 55 años en México —cancelería, consultorio, taller mecánico, restaurante— que ya pagó por un curso de internet que no sirvió y no piensa repetirlo. No le impresiona la tecnología; le impresiona el trabajo bien hecho, y sabe reconocerlo porque él lo hace todos los días. Por eso el producto no se comporta como software: se comporta como una herramienta de oficio. Materiales honestos —papel sin blanquear, tinta, cobre, verde de taller—, tolerancias apretadas, nada de brillo. Cada lección se entrega como una **nota de taller foliada**: numerada, sellada al completarse, imposible de confundir con un archivo desechable. La personalidad es la de un maestro de oficio con veinte años de experiencia: habla poco, no exagera nada, y lo que promete lo entrega.

---

## 2. Principios de diseño

**1. Nada es blanco puro y nada es negro puro.**
El blanco `#FFFFFF` y el negro `#000000` están prohibidos en toda superficie y todo texto. El blanco puro es luz de pantalla; el papel real no es blanco. Este único principio elimina de golpe el 80% del aspecto de plantilla.

**2. La asimetría es información.**
El contenido no se centra por defecto. Existe un carril de margen izquierdo permanente donde viven los folios, los estados y los sellos. El texto vive a la derecha. Nunca se compone una página perfectamente simétrica: la simetría absoluta es el reposo visual de una máquina, no de un taller.

**3. Cada valor del sistema tiene una razón física.**
Un radio de 3px porque es una placa de metal biselada. Un radio de 8px porque es papel cortado. La perforación existe porque los talonarios se desprenden. Si un token no puede justificarse con una razón material, se elimina.

**4. El cobre se gana, el musgo se usa.**
El verde musgo es la estructura: navegación, acciones, marca. El cobre es la recompensa: se reserva para lo completado, lo sellado y el precio. Un usuario debe poder recorrer tres pantallas sin ver cobre, para que cuando aparezca signifique algo.

**5. Solo se mueve lo que el usuario toca — con una única excepción.**
Cero animaciones al hacer scroll, cero parallax, cero entradas escalonadas. La única animación no disparada por el usuario en todo el producto es el estampado del sello al completar una lección. Una sola, y por eso se recuerda.

---

## 3. Paleta de color

Ningún valor es aleatorio: los verdes derivan del tono H≈100 (verde de máquina y pintura de taller) y los cobres del H≈20 (cobre oxidado y óxido de hierro). Son complementarios reales, no una combinación de moda.

### 3.1 Papeles — fondos

| Nombre | Hex | Uso exacto |
|---|---|---|
| `papel` | `#F2EEE4` | Fondo global de la aplicación. Papel sin blanquear. **Nunca se usa blanco en su lugar.** |
| `papel-hundido` | `#E7E1D3` | Zonas rebajadas: pista de la barra de progreso, estados vacíos, fondo del carril de margen, bloques de código dentro de lecciones. |
| `lienzo` | `#FBF9F4` | Superficie elevada: cards, panel de lectura de la lección, modales. Es el punto más claro del sistema y aun así no es blanco. |
| `lienzo-tinte` | `#F7F3E9` | Filas alternas en tablas y en el índice de lecciones. |

### 3.2 Tintas — texto

| Nombre | Hex | Uso exacto |
|---|---|---|
| `tinta` | `#1E2A1C` | Texto principal, titulares. Negro verdoso, nunca neutro. |
| `tinta-media` | `#4C5847` | Texto secundario, descripciones de curso, metadatos de lección. |
| `tinta-tenue` | `#78826F` | Placeholders, texto deshabilitado, ayuda. Mínimo 16px. |
| `tinta-inversa` | `#F4F1E7` | Texto sobre fondos musgo o cobre. |

### 3.3 Musgo — estructura y acción

| Nombre | Hex | Uso exacto |
|---|---|---|
| `musgo-900` | `#22301F` | Pie de página, barra de navegación del área de aprendizaje. |
| `musgo-700` | `#31432C` | Hover de superficies musgo, borde inferior del botón primario. |
| `musgo-600` | `#3E5236` | **Color de marca.** Botón primario, enlaces, borde de foco. |
| `musgo-500` | `#4B6141` | Estado presionado del primario. |
| `musgo-300` | `#94A288` | Iconografía inactiva, líneas de conexión del índice, sello pendiente. |
| `musgo-100` | `#DFE5D7` | Fondo de badge, fila activa, resaltado suave. |
| `musgo-anillo` | `rgba(62,82,54,0.34)` | Anillo de foco por teclado. |

### 3.4 Cobre — recompensa y venta

| Nombre | Hex | Uso exacto |
|---|---|---|
| `cobre-700` | `#7E3714` | Hover de elementos cobre. |
| `cobre-600` | `#9C481C` | **Sello de completado, precio, curso destacado.** Nada más. |
| `cobre-400` | `#C2703F` | Arco de progreso del sello, progreso parcial. |
| `cobre-100` | `#F2DFCF` | Fondo de la etiqueta de precio y del sello estampado. |
| `patina` | `#6E7F5E` | Verde-gris de óxido. Línea de perforación y separadores sobre superficies cobre. |

### 3.5 Líneas

| Nombre | Hex | Uso exacto |
|---|---|---|
| `linea` | `#D7CFBD` | Borde lateral de cards y separadores. |
| `linea-firme` | `#BCB09A` | Borde de inputs, bordes que delimitan estructura. |
| `linea-luz` | `#FDFBF6` | Borde **superior** de superficies elevadas. Simula luz cenital (ver §6.1). |
| `linea-sombra` | `#C4B9A2` | Borde **inferior** de superficies elevadas. Contraparte de `linea-luz`. |

### 3.6 Estados

| Nombre | Hex | Uso exacto |
|---|---|---|
| `logrado` | `#3E5236` | Completado. **Es el musgo de marca a propósito**: terminar el curso *es* la promesa. |
| `logrado-fondo` | `#DFE5D7` | Fondo de fila completada. |
| `atencion` | `#8A5D0C` | Quiz reprobado, avisos. Ocre, no amarillo. |
| `atencion-fondo` | `#F5E7C8` | Fondo de aviso. |
| `falla` | `#8E2A20` | Error destructivo, validación fallida. |
| `falla-fondo` | `#F4DCD6` | Fondo de error. |
| `bloqueado` | `#8C8878` | Contenido sin acceso. Gris cálido, nunca gris azulado. |

### 3.7 Contraste

Objetivo AA en todo texto e icono informativo. Ratios calculados sobre los pares reales de uso:

| Par | Ratio | Veredicto |
|---|---|---|
| `tinta` sobre `papel` | ~13.9:1 | AAA |
| `tinta-media` sobre `papel` | ~7.1:1 | AAA |
| `tinta-tenue` sobre `papel` | ~4.6:1 | AA, solo ≥16px |
| `tinta-inversa` sobre `musgo-600` | ~7.9:1 | AAA |
| `tinta-inversa` sobre `cobre-600` | ~5.6:1 | AA |
| `cobre-600` sobre `papel` | ~5.4:1 | AA |

Re-verificar con herramienta al implementar los tokens. El color nunca es el único portador de estado: todo estado lleva además forma, icono o texto.

**No hay modo oscuro.** El concepto es papel. Un papel no se apaga.

---

## 4. Tipografía

### 4.1 Familias

Dos familias variables, ambas de licencia **SIL Open Font**, ambas gratuitas para uso comercial sin límite de tráfico ni atribución. Cero coste, cero riesgo legal.

**Titulares, interfaz y datos: Archivo** — Omnibus-Type (Buenos Aires). Google Fonts.
`https://fonts.google.com/specimen/Archivo`

Grotesca de linaje rotulista: se diseñó para señalización impresa de alto contraste, con terminaciones cortadas a escuadra, aperturas cerradas y un color de página compacto. Es la letra de un rótulo de taller, no la de una app.

Dos razones concretas para elegirla por encima de cualquier otra grotesca libre:

1. **Es una fuente latinoamericana.** Omnibus-Type dibuja para el español antes que para el inglés: `ñ`, `á`, `¿`, `¡` y las versalitas acentuadas están resueltas desde el diseño, no parcheadas después. Para un producto dirigido a dueños de negocio en México, esto no es un detalle romántico — es que los acentos no se vean pegados.
2. **Tiene eje de ancho variable real (`wdth` 62–125).** Esto habilita la decisión de composición de §4.2: el rótulo del hero se compone en ancho 118 y toda la interfaz en ancho 100. Un mismo dibujo, dos anchos distintos según jerarquía.

**Cuerpo y contenido de lección: Newsreader** — Production Type. Google Fonts.
`https://fonts.google.com/specimen/Newsreader`

Se mantiene sin cambios respecto a la v2: ya era gratuita. Serif de lectura con **eje de tamaño óptico real (`opsz` 6–72)**: a 19px las astas se engrosan y el espaciado se abre; a 42px se afinan y se aprietan. Tus lecciones son markdown de 3.000 a 4.000 caracteres y esa corrección se nota en la fatiga de lectura, no en la captura de pantalla.

**Prohibidas explícitamente:** Inter, Roboto, system-ui, Poppins, Montserrat, Space Grotesk, Lato, Open Sans, Nunito, Raleway, Work Sans, DM Sans.

```
--tipo-titular: 'Archivo', 'Archivo Narrow', sans-serif;
--tipo-cuerpo:  'Newsreader', Georgia, serif;
```

Carga: ambas en formato variable, subconjunto `latin` + `latin-ext`, `font-display: swap`. Se precarga únicamente el corte de Archivo del rótulo del hero. Alojar los `.woff2` en el propio dominio en lugar de servirlos desde Google evita el salto de red de terceros y mejora el LCP en conexiones móviles mexicanas.

**Verificación obligatoria antes de cerrar la fase:** componer la cadena `Ñoño, ¿cuánto ahorrás? — 5 horas · 3.400 días` en ambas familias, en `rotulo` y en `lectura`, y revisar acentos, apertura de interrogación y guion largo. Si algo se rompe, se reporta antes de construir componentes.

### 4.2 Escala

Progresión de 1.26 en interfaz, con saltos abiertos en display. La escala **no es geométrica pura**: los tamaños de lectura están corregidos a mano porque la corrección óptica gana a la matemática.

| Token | Tamaño / Interlineado | Familia · Peso · Tracking | Cuándo se usa |
|---|---|---|---|
| `rotulo` | 60 / 0.96 | Archivo 700 · **`wdth` 118** · −0.035em | Titular del hero. Máximo uno por sitio. |
| `titulo-1` | 42 / 1.04 | Archivo 700 · **`wdth` 118** · −0.03em | Titular de página, nombre del curso en su portada. |
| `titulo-2` | 31 / 1.14 | Archivo 600 · `wdth` 100 · −0.02em | Título de sección, título de módulo. |
| `titulo-3` | 23 / 1.28 | Archivo 600 · `wdth` 100 · −0.012em | Título de lección, encabezado de card. |
| `titulo-4` | 18 / 1.36 | Archivo 550 · `wdth` 100 · −0.005em | Subtítulos dentro de la lección (los `##` del markdown). |
| `lectura` | 19 / 1.74 | Newsreader 400 · `opsz` 19 | **Cuerpo de la lección.** El texto largo vive aquí. |
| `lectura-guia` | 21 / 1.62 | Newsreader 450 · `opsz` 21 | Párrafo de entrada de la lección y el campo `outcome`. |
| `cuerpo` | 17 / 1.62 | Newsreader 400 · `opsz` 17 | Texto general fuera de la lección. |
| `interfaz` | 16 / 1.45 | Archivo 500 · `wdth` 100 | Botones, navegación, etiquetas de formulario. |
| `dato` | 14 / 1.4 | Archivo 500 · `wdth` 100 · tabular | Metadatos, duración, contadores. |
| `folio` | 12 / 1.2 | Archivo 600 · **`wdth` 88** · +0.06em · tabular | **Solo** el número de folio del carril de margen. Único sitio con tracking positivo y único sitio con ancho estrecho. |

**La regla de los tres anchos.** El eje `wdth` de Archivo no es decoración: codifica jerarquía igual que el radio codifica material.
- **118 (expandido)** → solo `rotulo` y `titulo-1`. Un rótulo se estira porque tiene que leerse de lejos.
- **100 (normal)** → todo lo demás.
- **88 (estrecho)** → solo `folio`. Un número de serie impreso siempre es condensado, porque cabe en un margen.

Ningún otro ancho intermedio está permitido. Tres valores, tres significados.

En móvil (<640px): `rotulo` → 36/1.02, `titulo-1` → 29/1.1, `titulo-2` → 24/1.18. Los tamaños de lectura **no cambian**: 19px sigue siendo 19px en el celular, porque ahí es donde de verdad se lee.

### 4.3 Reglas de composición

- Ancho de línea: máximo **66ch** en lección, **54ch** en texto de venta. Nunca a ancho completo.
- Sentence case en absolutamente todo. Sin Title Case. Sin mayúsculas sostenidas en ningún sitio, incluidos badges y botones.
- Prohibido resaltar una sola palabra del titular en otro color, cursiva o peso.
- Prohibidos los *eyebrows*: si un título necesita una etiqueta encima para entenderse, el título está mal escrito.
- `font-variant-numeric: tabular-nums` obligatorio en precios, progreso, duración y folios.
- Comillas tipográficas españolas correctas y guion largo con espacios finos. Un guion recto en el copy es un defecto de fabricación.

---

## 5. Espaciado y ritmo

Base de 2px. La escala **no es lineal**: se comprime en los valores pequeños y se abre en los grandes, igual que las marcas de un flexómetro. Una escala geométrica uniforme produce el ritmo plano característico del diseño generado.

```
--e-1:   2px     --e-6:   24px
--e-2:   4px     --e-7:   36px
--e-3:   8px     --e-8:   54px
--e-4:  12px     --e-9:   80px
--e-5:  18px     --e-10: 120px
```

**Ritmo vertical entre secciones:** `--e-9` (80px) en escritorio, `--e-7` (36px) en móvil. Nunca el mismo valor dos secciones seguidas: se alterna 80 / 120 / 80 para que la página respire de forma irregular y no cadenciada.

**Padding interno de card:** `--e-6` (24px). Cards compactas `--e-4`. El padding superior es siempre **2px mayor** que el inferior: compensa la altura visual del texto y es la clase de corrección que un sistema automático nunca aplica.

### 5.1 La rejilla asimétrica

12 columnas, canalón `--e-6`, contenedor máximo 1240px. El reparto es fijo y desigual:

```
┌──────────┬───────────────────────────┬───────────┐
│ carril   │ contenido                 │ aire      │
│ 2 cols   │ 8 cols                    │ 2 cols    │
│          │                           │           │
│ folio    │ título                    │           │
│ sello    │ texto a 66ch              │           │
│ estado   │                           │           │
└──────────┴───────────────────────────┴───────────┘
```

El **carril de margen** de 2 columnas es permanente en escritorio y aloja folio, sello y estado. El contenido nunca se centra respecto al viewport. En móvil el carril colapsa a una franja horizontal de 44px sobre el contenido, conservando folio y sello.

---

## 6. Bordes y radios

El radio codifica **de qué está hecha** la cosa. Cinco valores, cada uno con una razón material.

```
--r-placa:  3px    metal biselado → botones, inputs, selects, badges de dato
--r-papel:  8px    papel cortado a guillotina → cards, paneles
--r-hoja:  14px    hoja gruesa → modales, hoja inferior en móvil
--r-sello: 999px   circular → sellos, avatares, badges de estado
--r-nulo:    0px   corte a ras → nota de taller y línea de perforación
```

### 6.1 Borde de luz cenital

Toda superficie elevada lleva **bordes de distinto color arriba y abajo**, no un borde uniforme:

```
border-top:    1px solid var(--linea-luz);      /* #FDFBF6 */
border-left:   1px solid var(--linea);          /* #D7CFBD */
border-right:  1px solid var(--linea);
border-bottom: 1px solid var(--linea-sombra);   /* #C4B9A2 */
```

Simula una fuente de luz única desde arriba y hace que la card se lea como una pieza física con canto, no como un rectángulo dibujado. Es el detalle que más aporta a la sensación táctil y el que casi nunca se replica, porque exige escribir cuatro declaraciones de borde en vez de una.

### 6.2 Grano

Sobre `papel` y `lienzo` se aplica una textura de ruido generada con `feTurbulence` (SVG en línea, `baseFrequency 0.8`, `numOctaves 3`) al **2.5% de opacidad**, en `mix-blend-mode: multiply`, sin repintado en scroll. Invisible si la buscas; determinante si la quitas. Se desactiva bajo `prefers-reduced-transparency`.

---

## 7. Sombras

**Prohibido el gris neutro.** Toda sombra se tinta con el musgo del sistema y se compone de **dos capas**: un contacto corto y oscuro, y una ambiental larga y suave. Las sombras de una sola capa son planas y son el tell más común del kit de cards genérico.

```
--sombra-apoyo:
  0 1px 1px rgba(34,48,31,0.10),
  0 2px 6px -2px rgba(34,48,31,0.06);

--sombra-alzada:
  0 2px 3px rgba(34,48,31,0.12),
  0 10px 22px -8px rgba(34,48,31,0.14);

--sombra-flotante:
  0 4px 6px rgba(34,48,31,0.14),
  0 26px 56px -18px rgba(34,48,31,0.26);

--sombra-hundida:
  inset 0 1px 2px rgba(34,48,31,0.14);
```

Reglas de uso:
- `--sombra-apoyo`: cards en reposo, **siempre junto al borde de luz cenital de §6.1**. Nunca sombra sin borde.
- `--sombra-alzada`: hover de card, dropdowns, popovers.
- `--sombra-flotante`: modales y hojas inferiores, exclusivamente.
- `--sombra-hundida`: pista de progreso e inputs. Es lo que hace que un campo se sienta troquelado en el papel.

---

## 8. Firma visual distintiva: **la nota de taller**

Un solo elemento, tres partes coordinadas, presente en todo el producto. Es lo que hace que la plataforma sea reconocible con la pantalla a un metro de distancia.

### 8.1 La perforación

**El separador del sistema no es una línea.** Es una línea de perforación de talonario:

- Trazo punteado de `2px` de diámetro, `--patina` (`#6E7F5E`), espaciado de `7px`, opacidad 0.55
- Implementada con `repeating-linear-gradient`, nunca con `border-dashed` — el guion de CSS es rectangular y aquí se necesitan puntos redondos
- En sus dos extremos, **dos semicírculos de `--papel` de 8px de diámetro** incrustados en el borde de la card, que simulan el troquel donde arranca el desprendible

Aparece entre módulos, entre el encabezado y el cuerpo de la lección, y en el pie de cada card de curso. Es el elemento repetido que da unidad a todo el producto.

### 8.2 El folio

Cada lección tiene un número de folio permanente, formado como `M02·L07` (módulo, lección), en el token `folio`, alineado a la izquierda en el carril de margen, en `--tinta-tenue`.

No es decoración: es la referencia que el alumno usa para volver a una lección, y aparece idéntico en el índice, en la lección y en cualquier comunicación de progreso. Es el único sitio del producto con tracking positivo, porque un folio impreso siempre lleva letra espaciada.

### 8.3 El sello

El indicador de completado es un **sello estampado**, no una palomita:

- Circunferencia de 34px, `--r-sello`, borde de 2px
- **Pendiente:** borde `--musgo-300`, interior transparente, sin texto
- **En curso:** borde `--musgo-600`, arco de progreso en `--cobre-400` recorriendo el perímetro
- **Completada:** borde e interior en `--cobre-600` sobre `--cobre-100`, palomita en `--tinta-inversa`, y una **rotación fija de −7°**

Esa inclinación de 7 grados es la decisión más importante del sistema. Un sello estampado a mano nunca queda recto. Un elemento perfectamente alineado se lee como render; uno inclinado 7 grados se lee como algo que alguien puso ahí. Es el mismo ángulo en todo el producto, siempre.

**La única animación no disparada por el usuario de toda la plataforma** vive aquí: al marcar una lección como completada, el sello entra desde `scale(1.14)` y `rotate(-14deg)` hasta `scale(1)` y `rotate(-7deg)` en 280ms con `cubic-bezier(0.34, 1.3, 0.64, 1)` — un solo rebote corto, como un cuño al golpear el papel. Bajo `prefers-reduced-motion`, el sello simplemente aparece.

---

## 9. Componentes prioritarios y cómo deben sentirse

Orden de construcción. No se instala un componente de shadcn/ui hasta que una pantalla aprobada lo necesita.

### Bloque 1 — catálogo y venta

**`button`** — Debe sentirse como una tecla de máquina, no como un rectángulo de color. Altura 46px, `--r-placa`, Archivo 500 en ancho 100, sentence case. El primario lleva un borde inferior de 1px en `--musgo-700` que **desaparece en el estado presionado** mientras el contenido baja 1px: el botón se hunde de verdad. Sin `transform: scale`. Sin flecha en el texto. Transición 130ms.

**`CourseCard`** (propio) — Una ficha física sobre el escritorio. `lienzo`, `--r-papel`, borde de luz cenital, `--sombra-apoyo`, perforación en el pie. En hover sube a `--sombra-alzada` **sin moverse**: cambia la luz, no la posición. Seis estados: reposo, hover, foco, destacado (filete de 3px en `cobre-600` en el canto izquierdo), inscrito (progreso visible y botón "Continuar"), bloqueado (opacidad 0.62, candado en `--bloqueado`).

**`badge`** — `--r-placa` para badges de dato; `--r-sello` para badges de estado. Esa diferencia es deliberada: lo que es dato tiene esquina, lo que es estado es redondo.

**`progress`** — Pista `--papel-hundido` con `--sombra-hundida`, relleno `--musgo-600`, altura 7px, `--r-sello`. Sin animación de brillo.

**`separator`** — **Siempre la perforación de §8.1.** No existe un separador liso en este producto.

### Bloque 2 — autenticación

**`input`** — Troquelado, no dibujado: fondo `--lienzo-tinte`, `--sombra-hundida`, borde `--linea-firme`, `--r-placa`. En foco el borde pasa a `--musgo-600`, aparece el anillo `--musgo-anillo` y **el fondo sube a `--lienzo`**, como si el campo se iluminara al recibir la pluma.

**`form` + `label` + `sonner`** — El error nunca se disculpa y nunca es vago: dice qué pasó y cómo se arregla, en `--falla` sobre `--falla-fondo`.

### Bloque 3 — aprendizaje

**`DeliverableBlock`** (propio) — El bloque de entregable al inicio de cada lección, construido sobre el campo `outcome`. `--r-nulo` arriba y `--r-papel` abajo, filete superior sólido de 4px (`--musgo-600` pendiente, `--cobre-600` completado), encabezado "Vas a salir con esto" en `titulo-3`, cuerpo en `lectura-guia`, sello de §8.3 en el carril.

**`LessonRow`** (propio) — Cinco estados, cada uno con su sello en el carril de margen: no empezada, en curso, completada, bloqueada, vista previa (etiqueta "Gratis" en `--musgo-100`).

**`accordion`** — Módulos plegables. El chevron rota 180°, sin rebote. Perforación entre módulos.

**`radio-group`** — Respuestas de quiz. El indicador seleccionado es un punto sólido `--musgo-600`, no un anillo hueco.

**`MissionChecklist`** (propio) — Alimentado por `mission_checklists`. Cada criterio cumplido recibe un sello de 20px, la versión pequeña de §8.3.

**`sheet`** — Patrón dominante en móvil, por encima de `dialog`. `--r-hoja` solo en las esquinas superiores, `--sombra-flotante`, y un tirador de 36×4px en `--linea-firme` centrado arriba.

**`skeleton`** — `--papel-hundido` sin barrido de brillo. El brillo animado es de plantilla.

### Bloque 4 — administración (última fase)

`table`, `select`, `textarea`, `alert-dialog`. Filas alternas con `--lienzo-tinte`.

**No se instalan en la v1:** `carousel`, `chart`, `command`, `calendar`, `menubar`, `navigation-menu`, `resizable`, `context-menu`, `toast` (en desuso, se usa `sonner`).

### Piso de calidad, sin excepciones

Contraste AA · foco visible en todo elemento interactivo · objetivo táctil de 44×44px · `prefers-reduced-motion` respetado · un solo `<h1>` por página · el estado nunca depende solo del color · `<label>` real asociado, el placeholder nunca sustituye a la etiqueta.

---

## 10. Qué hace que este sistema sea difícil de copiar

No es el color. La paleta se copia en cinco minutos. Lo difícil de replicar es el conjunto de decisiones que exigen escribir más código del que se escribe por defecto:

1. **Los ejes variables se usan de verdad, no se declaran.** La diferenciación ya no viene de una licencia de pago, sino de algo que ningún generador hace: componer `wdth` 118 / 100 / 88 en Archivo según jerarquía, y fijar `opsz` a mano en cada tamaño de Newsreader. El patrón automático carga la fuente en su ancho por defecto, ignora los ejes y produce un color de página plano. Copiar el nombre de la fuente toma un segundo; reproducir el sistema de tres anchos exige entender por qué existe.

2. **El borde de luz cenital son cuatro declaraciones donde el patrón por defecto escribe una.** `border: 1px solid X` es el reflejo automático; cuatro bordes de tres colores distintos es una decisión sobre de dónde viene la luz.

3. **Las sombras son de dos capas y están tintadas de musgo.** La sombra por defecto es `rgba(0,0,0,0.1)` de una sola capa. Reproducir el aspecto exige entender que la sombra hereda el color del entorno.

4. **Cinco radios asignados por material, no por tamaño.** El patrón automático usa un `--radius` único. Aquí un botón lleva 3px porque es metal y una card 8px porque es papel, y hay que conocer la regla para no romperla.

5. **La rotación de −7° del sello.** La perfección geométrica es gratis; la imperfección deliberada y consistente exige que alguien decida el ángulo, lo aplique igual en todas partes y lo defienda cuando pidan enderezarlo.

6. **Escala de espaciado no lineal y padding superior 2px mayor que el inferior.** Ambas son correcciones ópticas que solo se aplican si sabes por qué existen.

7. **El separador es una perforación con troquel, no una línea.** Un `<hr>` toma un segundo. Este toma un `repeating-linear-gradient` de puntos redondos más dos semicírculos incrustados en el canto de la card.

8. **La prohibición del blanco y el negro puros, sostenida en todo el sistema.** Fácil de enunciar, difícil de mantener: basta un `#FFF` en un componente para que toda la sensación de papel se rompa. Es la regla a vigilar en cada revisión de código.

9. **El grano al 2.5%.** Nadie lo nota. Todos notan cuando falta.

10. **El carril de margen asimétrico.** El reflejo por defecto es centrar el contenido. Sostener una composición desequilibrada a lo largo de un producto entero es una decisión editorial, y se nota en la primera pantalla.
