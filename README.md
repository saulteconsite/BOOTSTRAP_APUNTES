# `BOOTSTRAP 5 - APUNTES COMPLETOS DEL CURSO UDEMY CODEIGNITER 4 🎨`

![img](https://i.pinimg.com/originals/a1/f8/be/a1f8be54a08a324c83e747a8fa5ed660.gif)

> [!NOTE]
> ***ESTOS APUNTES CUBREN TODO LO RELACIONADO CON BOOTSTRAP 5.3.3*** tal y como se usa en el proyecto del curso de Udemy "CodeIgniter 4 desde cero + integración con Bootstrap 4 o 5". **Incluye explicación detallada de cada componente,** *clase de utilidad y concepto de Bootstrap* con ejemplos reales del proyecto (navbar, tablas, formularios, cards, alertas, grid, spacing, colores, botones, badges, paginación, responsive y mucho más). ***CADA SECCIÓN INDICA EN QUÉ ARCHIVO DEL PROYECTO SE USA***

---

## `¿QUÉ ES BOOTSTRAP? 📦`

> [!NOTE]
> **Bootstrap es un framework CSS de código abierto creado originalmente por Twitter en 2011.** *PROPORCIONA UNA COLECCIÓN DE ESTILOS CSS Y COMPONENTES JAVASCRIPT PREDISEÑADOS* que permiten crear interfaces web bonitas, modernas y responsivas **sin tener que escribir CSS desde cero.** ***ES EL FRAMEWORK CSS MÁS POPULAR DEL MUNDO***

### `CONCEPTOS CLAVE`

| CONCEPTO | SIGNIFICADO |
|---|---|
| ***FRAMEWORK CSS*** | *Una librería de estilos ya hechos que tú aplicas con clases CSS* |
| **Responsivo** | ***LA PÁGINA SE ADAPTA AUTOMÁTICAMENTE AL TAMAÑO DE PANTALLA (MÓVIL, TABLET, ESCRITORIO)*** |
| ***MOBILE FIRST*** | **Bootstrap diseña primero para móviles y luego escala hacia arriba** |
| *Componentes* | ***PIEZAS DE INTERFAZ REUTILIZABLES: BOTONES, TARJETAS, NAVBAR, ALERTAS, ETC.*** |
| ***UTILIDADES*** | *Clases CSS pequeñas que hacen una sola cosa: `mt-3`, `text-center`, `d-flex`, etc.* |
| **CDN** | ***CONTENT DELIVERY NETWORK - SERVIDOR EXTERNO QUE ALOJA LOS ARCHIVOS DE BOOTSTRAP*** |

### `BOOTSTRAP NO TIENE NADA QUE VER CON CODEIGNITER`

> [!IMPORTANT]
> ***ESTO ES FUNDAMENTAL ENTENDERLO:*** **CodeIgniter 4 es un framework PHP para el BACKEND (servidor)** *y Bootstrap es un framework CSS para el FRONTEND (navegador).* ***SON COMPLETAMENTE INDEPENDIENTES.*** **Podrías usar CI4 sin Bootstrap (y escribir tu propio CSS),** *o podrías usar Bootstrap sin CI4 (con Laravel, Symfony, o incluso sin framework PHP).* ***SE USAN JUNTOS POR CONVENIENCIA: CI4 GENERA EL HTML Y BOOTSTRAP LO HACE BONITO***

### `¿CÓMO FUNCIONA?`

**Bootstrap funciona con CLASES CSS.** *TÚ AÑADES CLASES A TUS ELEMENTOS HTML Y BOOTSTRAP LES APLICA ESTILOS AUTOMÁTICAMENTE.* **No necesitas escribir CSS.** ***SOLO NECESITAS SABER QUÉ CLASE USAR:***

```html
<!-- SIN Bootstrap (HTML pelado, feo) -->
<button>Guardar</button>

<!-- CON Bootstrap (bonito, con estilos) -->
<button class="btn btn-primary">Guardar</button>
```

*La clase `btn` le da aspecto de botón y `btn-primary` lo pinta de azul.* ***ASÍ DE SIMPLE***

---

## `INSTALACIÓN: CÓMO SE CARGA EN EL PROYECTO 🔌`

> [!NOTE]
> **En el proyecto de Udemy, Bootstrap se carga desde CDN (servidor externo).** ***ESTO SIGNIFICA QUE NO HAY QUE DESCARGAR NADA NI INSTALAR NADA CON NPM O COMPOSER.*** *Solo se añaden dos líneas en el HTML*

### `ARCHIVO: `app/Views/layout/main.php``

***EN EL `<head>` DEL LAYOUT SE CARGAN LOS CSS:***

```html
<!-- BOOTSTRAP 5.3.3 - ESTILOS CSS -->
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css"
      rel="stylesheet">

<!-- FONT AWESOME 6.5.1 - ÍCONOS (NO ES PARTE DE BOOTSTRAP) -->
<link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css"
      rel="stylesheet">
```

**Antes de cerrar el `</body>` se carga el JavaScript:**

```html
<!-- BOOTSTRAP 5.3.3 - JAVASCRIPT (PARA NAVBAR RESPONSIVE, ALERTAS CERRABLES, ETC.) -->
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js">
</script>
```

### `¿QUÉ ES UN CDN?`

| ASPECTO | DESCRIPCIÓN |
|---|---|
| ***SIGNIFICADO*** | *Content Delivery Network (red de distribución de contenido)* |
| **Qué es** | ***UN SERVIDOR EXTERNO QUE ALOJA ARCHIVOS PÚBLICOS (CSS, JS, FUENTES, ETC.)*** |
| ***VENTAJA*** | **Más rápido (servidores optimizados en todo el mundo), no ocupa espacio en tu proyecto** |
| *Desventaja* | ***SI NO HAY INTERNET, BOOTSTRAP NO SE CARGA Y LA PÁGINA SE VE FEA*** |
| ***ALTERNATIVA*** | *Descargar Bootstrap en tu proyecto con NPM (`npm install bootstrap`) o descarga directa* |

### `¿POR QUÉ SE NECESITA TANTO CSS COMO JS?`

*El CSS de Bootstrap da los estilos visuales (colores, bordes, tamaños, grid, etc.).* ***EL JAVASCRIPT DE BOOTSTRAP AÑADE INTERACTIVIDAD A CIERTOS COMPONENTES:***

| COMPONENTE | ¿NECESITA JS? | POR QUÉ |
|---|---|---|
| ***NAVBAR RESPONSIVE*** | **Sí** | *El menú hamburguesa se abre/cierra con JS* |
| **Alertas descartables** | ***SÍ*** | ***EL BOTÓN X QUE CIERRA LA ALERTA USA JS*** |
| *Tooltips* | **Sí** | ***LOS POPUPS INFORMATIVOS NECESITAN JS PARA APARECER*** |
| ***MODALES*** | *Sí* | **Las ventanas emergentes se abren/cierran con JS** |
| *Dropdown* | ***SÍ*** | ***LOS MENÚS DESPLEGABLES NECESITAN JS*** |
| **Botones** | ***NO*** | *Solo necesitan CSS para los estilos* |
| ***TABLAS*** | **No** | *Solo necesitan CSS* |
| *Cards* | ***NO*** | **Solo necesitan CSS** |
| ***GRID*** | *No* | ***SOLO NECESITAN CSS*** |
| **Formularios** | ***NO*** | *Solo necesitan CSS* |

> [!TIP]
> **El archivo `bootstrap.bundle.min.js` ya incluye Popper.js** *(necesario para tooltips y dropdowns).* ***SI USAS `bootstrap.min.js` (SIN "BUNDLE"), TENDRÍAS QUE CARGAR POPPER.JS POR SEPARADO***

---

## `SISTEMA DE GRID (REJILLA) - LA BASE DE BOOTSTRAP 📐`

> [!NOTE]
> ***EL GRID ES EL SISTEMA MÁS IMPORTANTE DE BOOTSTRAP.*** **Divide la pantalla en 12 columnas invisibles** *y tú decides cuántas columnas ocupa cada elemento.* ***ES LO QUE HACE QUE LA PÁGINA SEA RESPONSIVA***

### `CONCEPTO: 12 COLUMNAS`

```
LA PANTALLA COMPLETA = 12 COLUMNAS

|  1  |  2  |  3  |  4  |  5  |  6  |  7  |  8  |  9  | 10  | 11  | 12  |
|─────────────────────────────────────────────────────────────────────────|

col-6 = OCUPA 6 DE 12 COLUMNAS = 50% DEL ANCHO
|████████████████████████████████████|                                    |

col-4 = OCUPA 4 DE 12 COLUMNAS = 33.3% DEL ANCHO
|████████████████████████|                                                |

col-3 = OCUPA 3 DE 12 COLUMNAS = 25% DEL ANCHO
|██████████████████|                                                      |

col-12 = OCUPA 12 DE 12 COLUMNAS = 100% DEL ANCHO (FILA COMPLETA)
|████████████████████████████████████████████████████████████████████████|
```

### `ESTRUCTURA BÁSICA: container → row → col`

***SIEMPRE SE SIGUE ESTA JERARQUÍA.*** **No puedes poner un `col` sin un `row`:**

```html
<div class="container">        <!-- CONTENEDOR QUE CENTRA TODO -->
    <div class="row">          <!-- FILA QUE CONTIENE COLUMNAS -->
        <div class="col-6">   <!-- COLUMNA QUE OCUPA 6/12 = 50% -->
            Contenido izquierda
        </div>
        <div class="col-6">   <!-- COLUMNA QUE OCUPA 6/12 = 50% -->
            Contenido derecha
        </div>
    </div>
</div>
```

### `BREAKPOINTS: TAMAÑOS DE PANTALLA`

*Bootstrap define 6 breakpoints (puntos de quiebre).* ***PUEDES ASIGNAR DIFERENTES ANCHOS DE COLUMNA PARA CADA TAMAÑO DE PANTALLA:***

| BREAKPOINT | PREFIJO | ANCHO MÍNIMO | DISPOSITIVO TÍPICO |
|---|---|---|---|
| ***EXTRA SMALL*** | *`col-`* | **< 576px** | *Móviles en vertical* |
| **Small** | ***`col-sm-`*** | *≥ 576px* | ***MÓVILES EN HORIZONTAL*** |
| ***MEDIUM*** | **`col-md-`** | *≥ 768px* | **Tablets** |
| *Large* | ***`col-lg-`*** | **≥ 992px** | ***ESCRITORIOS*** |
| ***EXTRA LARGE*** | *`col-xl-`* | **≥ 1200px** | *Escritorios grandes* |
| **XXL** | ***`col-xxl-`*** | *≥ 1400px* | ***PANTALLAS MUY GRANDES*** |

### `EJEMPLO DEL PROYECTO: FORMULARIO DE LOGIN CENTRADO`

***ARCHIVO: `app/Views/auth/login.php`***

```html
<div class="row justify-content-center">
    <div class="col-md-6">
        <!-- FORMULARIO DE LOGIN AQUÍ -->
    </div>
</div>
```

| CLASE | QUÉ HACE |
|---|---|
| ***`row`*** | *Crea una fila que contiene columnas* |
| **`justify-content-center`** | ***CENTRA LA COLUMNA HORIZONTALMENTE DENTRO DE LA FILA*** |
| *`col-md-6`* | **En pantallas medianas (≥768px) o mayores: ocupa 6/12 = 50% del ancho** |
| ***EN MÓVILES*** | *Automáticamente ocupa 12/12 = 100% del ancho (porque no hay `col-` sin sufijo)* |

**Resultado: el formulario de login ocupa la mitad de la pantalla en escritorio** ***Y TODO EL ANCHO EN MÓVILES***

### `EJEMPLO DEL PROYECTO: CHECKBOXES DE ETIQUETAS`

*Archivo: `app/Views/peliculas/create.php`*

```html
<?php foreach ($etiquetas as $etiqueta): ?>
    <div class="col-md-3 col-6">
        <div class="form-check">
            <input type="checkbox" name="etiquetas[]" value="<?= $etiqueta['id'] ?>">
            <label><?= esc($etiqueta['nombre']) ?></label>
        </div>
    </div>
<?php endforeach; ?>
```

| CLASE | QUÉ HACE |
|---|---|
| ***`col-md-3`*** | **En escritorio: 3/12 = 25% del ancho → 4 checkboxes por fila** |
| *`col-6`* | ***EN MÓVILES: 6/12 = 50% DEL ANCHO → 2 CHECKBOXES POR FILA*** |

### `EJEMPLO DEL PROYECTO: BARRA DE FILTROS`

***ARCHIVO: `app/Views/peliculas/index.php`***

```html
<div class="row g-3 align-items-end">
    <div class="col-md-3">
        <!-- INPUT BÚSQUEDA -->
    </div>
    <div class="col-md-3">
        <!-- SELECT CATEGORÍA -->
    </div>
    <div class="col-md-3">
        <!-- SELECT ETIQUETA -->
    </div>
    <div class="col-md-3">
        <!-- BOTONES FILTRAR Y LIMPIAR -->
    </div>
</div>
```

| CLASE | QUÉ HACE |
|---|---|
| **`row`** | ***FILA CONTENEDORA*** |
| *`g-3`* | **Gap/gutter de nivel 3 (espacio entre columnas = 1rem)** |
| ***`align-items-end`*** | *Alinea los elementos al fondo de la fila (los botones quedan alineados con los inputs)* |
| **`col-md-3`** | ***CADA CAMPO OCUPA 3/12 = 25% → 4 CAMPOS EN UNA FILA EN ESCRITORIO*** |

### `COMBINACIONES COMUNES DE GRID`

| CLASES | ESCRITORIO | MÓVIL | USO TÍPICO |
|---|---|---|---|
| ***`col-12`*** | *100%* | **100%** | *Ancho completo siempre* |
| **`col-md-6`** | ***50%*** | *100%* | ***DOS COLUMNAS EN ESCRITORIO, UNA EN MÓVIL*** |
| *`col-md-4`* | **33%** | ***100%*** | **Tres columnas en escritorio** |
| ***`col-md-3`*** | *25%* | **100%** | ***CUATRO COLUMNAS EN ESCRITORIO*** |
| **`col-md-3 col-6`** | *25%* | ***50%*** | **Cuatro en escritorio, dos en móvil** |
| *`col-md-6 col-lg-4`* | ***33% (LG) / 50% (MD)*** | **100%** | *Tres escalas diferentes* |
| ***`col-md-8` + `col-md-4`*** | *66% + 33%* | **100% + 100%** | ***CONTENIDO PRINCIPAL + SIDEBAR*** |

### `GUTTERS (ESPACIADO ENTRE COLUMNAS)`

**Los gutters son el espacio entre columnas.** *Se controlan con clases `g-*`, `gx-*` (horizontal), `gy-*` (vertical):*

| CLASE | QUÉ HACE |
|---|---|
| ***`g-0`*** | **Sin espacio entre columnas** |
| *`g-1`* | ***ESPACIO MÍNIMO (0.25rem)*** |
| **`g-2`** | *Espacio pequeño (0.5rem)* |
| ***`g-3`*** | **Espacio medio (1rem) ← usado en los filtros del proyecto** |
| *`g-4`* | ***ESPACIO GRANDE (1.5rem)*** |
| **`g-5`** | *Espacio máximo (3rem)* |
| ***`gx-3`*** | **Espacio horizontal de 1rem (solo izquierda-derecha)** |
| *`gy-3`* | ***ESPACIO VERTICAL DE 1rem (SOLO ARRIBA-ABAJO)*** |

---

## `CONTAINER (CONTENEDOR) 📦`

> [!NOTE]
> **El container es el contenedor principal que centra el contenido y le da márgenes laterales.** ***SIN CONTAINER, TODO EL CONTENIDO IRÍA PEGADO A LOS BORDES DE LA PANTALLA***

### `TIPOS DE CONTAINER`

| CLASE | COMPORTAMIENTO |
|---|---|
| ***`container`*** | **Ancho fijo que cambia por breakpoint (más usado) ← usado en el proyecto** |
| *`container-fluid`* | ***ANCHO 100% SIEMPRE (OCUPA TODA LA PANTALLA)*** |
| **`container-sm`** | *100% hasta SM, luego ancho fijo* |
| ***`container-md`*** | **100% hasta MD, luego ancho fijo** |
| *`container-lg`* | ***100% HASTA LG, LUEGO ANCHO FIJO*** |
| **`container-xl`** | *100% hasta XL, luego ancho fijo* |

### `ANCHOS DEL CONTAINER SEGÚN BREAKPOINT`

| BREAKPOINT | `container` | `container-fluid` |
|---|---|---|
| ***< 576px*** | **100%** | *100%* |
| **≥ 576px (sm)** | ***540px*** | *100%* |
| *≥ 768px (md)* | **720px** | ***100%*** |
| ***≥ 992px (lg)*** | *960px* | **100%** |
| **≥ 1200px (xl)** | ***1140px*** | *100%* |
| *≥ 1400px (xxl)* | **1320px** | ***100%*** |

### `USO EN EL PROYECTO`

***ARCHIVO: `app/Views/layout/main.php`***

```html
<!-- CONTAINER EN LA NAVBAR (CENTRA EL MENÚ) -->
<nav class="navbar navbar-expand-lg navbar-dark bg-dark">
    <div class="container">
        <!-- CONTENIDO DE LA NAVBAR -->
    </div>
</nav>

<!-- CONTAINER PRINCIPAL (CENTRA TODO EL CONTENIDO DE LA PÁGINA) -->
<div class="container mt-4">
    <!-- MENSAJES FLASH -->
    <!-- CONTENIDO DE CADA VISTA HIJA -->
    <?= $this->renderSection('contenido') ?>
</div>
```

---

## `SISTEMA DE ESPACIADO (MARGIN Y PADDING) 📏`

> [!NOTE]
> ***BOOTSTRAP TIENE UN SISTEMA DE CLASES PARA CONTROLAR MÁRGENES Y PADDING*** **sin escribir CSS.** *Se usan en prácticamente todos los elementos del proyecto*

### `SINTAXIS: {propiedad}{lado}-{tamaño}`

**Primera letra = propiedad:**

| LETRA | PROPIEDAD | SIGNIFICADO |
|---|---|---|
| ***`m`*** | *margin* | **ESPACIO EXTERIOR (FUERA DEL BORDE)** |
| **`p`** | ***padding*** | *Espacio interior (dentro del borde)* |

*Segunda letra = lado:*

| LETRA | LADO | CSS EQUIVALENTE |
|---|---|---|
| ***`t`*** | **top** | *margin-top / padding-top* |
| **`b`** | ***bottom*** | *margin-bottom / padding-bottom* |
| *`s`* | **start (izquierda)** | ***margin-left / padding-left*** |
| ***`e`*** | *end (derecha)* | **margin-right / padding-right** |
| **`x`** | ***horizontal*** | *left + right* |
| *`y`* | **vertical** | ***top + bottom*** |
| ***(nada)*** | *todos los lados* | **margin / padding (los 4 lados)** |

***NÚMERO = TAMAÑO:***

| NÚMERO | TAMAÑO | EQUIVALENTE CSS |
|---|---|---|
| **`0`** | *nada* | ***0*** |
| *`1`* | **muy pequeño** | ***0.25rem (4px)*** |
| ***`2`*** | *pequeño* | **0.5rem (8px)** |
| **`3`** | ***medio*** | *1rem (16px)* |
| ***`4`*** | **grande** | *1.5rem (24px)* |
| *`5`* | ***muy grande*** | **3rem (48px)** |
| ***`auto`*** | *automático* | **auto (centra elementos)** |

### `EJEMPLOS DEL PROYECTO`

| CLASE | DÓNDE SE USA | QUÉ HACE |
|---|---|---|
| ***`mt-4`*** | *`container mt-4` en layout/main.php* | **Margen superior de 1.5rem entre la navbar y el contenido** |
| **`mb-3`** | ***`<div class="mb-3">` EN TODOS LOS FORMULARIOS*** | *Margen inferior de 1rem entre campos del formulario* |
| *`mb-4`* | **`card card-body bg-light mb-4` en los filtros** | ***MARGEN INFERIOR DE 1.5rem ENTRE LA BARRA DE FILTROS Y LA TABLA*** |
| ***`mt-2`*** | *`<div class="mt-2">` en la preview de imagen* | **Margen superior de 0.5rem encima de la imagen actual** |
| **`mt-3`** | ***`<div class="d-flex ... mt-3">` EN LA PAGINACIÓN*** | *Margen superior de 1rem entre la tabla y la paginación* |
| *`mt-4`* | **`card shadow mt-4` en login/registro** | ***MARGEN SUPERIOR DE 1.5rem ENTRE LA NAVBAR Y LA CARD*** |
| ***`mb-0`*** | *`<ul class="mb-0">` en listas de errores* | **Elimina el margen inferior por defecto de la lista** |
| **`mb-1`** | ***`<p class="text-muted mb-1">` EN IMAGEN ACTUAL*** | *Margen inferior mínimo* |
| *`mb-2`* | **`btn btn-dark w-100 mb-2` en botón filtrar** | ***MARGEN INFERIOR DE 0.5rem ENTRE LOS DOS BOTONES*** |
| ***`me-2`*** | *`btn btn-dark me-2` en categorías/etiquetas* | **Margen derecho de 0.5rem entre los botones buscar y limpiar** |
| **`me-auto`** | ***`navbar-nav me-auto` EN LA NAVBAR*** | *Margen derecho automático → empuja la parte derecha del menú* |

### `DIAGRAMA VISUAL MARGIN VS PADDING`

```
                    ┌─── MARGIN (espacio exterior) ───┐
                    │                                   │
                    │  ┌─── PADDING (espacio interior) ──┐
                    │  │                                  │
                    │  │    ┌─── CONTENIDO ───┐           │
   mt-4 ──────►    │  │    │                  │           │
                    │  │    │   Texto aquí     │           │  ◄── me-2
                    │  │    │                  │           │
                    │  │    └──────────────────┘           │
                    │  │                                  │
   mb-3 ──────►    │  └──────────────────────────────────┘
                    │                                   │
                    └───────────────────────────────────┘
```

---

## `COLORES DE FONDO Y TEXTO 🎨`

> [!NOTE]
> **Bootstrap define un sistema de colores semánticos** ***QUE SE USAN EN TODA LA LIBRERÍA.*** *Cada color tiene un nombre y un significado*

### `COLORES SEMÁNTICOS DE BOOTSTRAP`

| NOMBRE | COLOR | USO TÍPICO | HEX APROXIMADO |
|---|---|---|---|
| ***`primary`*** | **Azul** | *Acción principal (guardar, crear, links)* | ***#0d6efd*** |
| *`secondary`* | ***GRIS*** | **Acción secundaria (volver, cancelar)** | *#6c757d* |
| ***`success`*** | *Verde* | **Éxito, confirmación, rol admin** | ***#198754*** |
| **`danger`** | ***ROJO*** | *Error, peligro, eliminar* | **#dc3545** |
| *`warning`* | **Amarillo** | ***ADVERTENCIA, EDITAR*** | *#ffc107* |
| ***`info`*** | *Celeste* | **Información, rol usuario** | ***#0dcaf0*** |
| **`light`** | ***GRIS CLARO*** | *Fondo suave, cards de filtros* | **#f8f9fa** |
| *`dark`* | **Casi negro** | ***NAVBAR, CABECERAS DE TABLAS*** | *#212529* |
| ***`white`*** | **Blanco** | *Texto sobre fondo oscuro* | ***#ffffff*** |

### `CLASES DE FONDO (bg-*)`

| CLASE | QUÉ HACE | DÓNDE SE USA EN EL PROYECTO |
|---|---|---|
| ***`bg-dark`*** | **Fondo oscuro** | *Navbar (`navbar-dark bg-dark`), card header del login* |
| **`bg-light`** | ***FONDO GRIS CLARO*** | **Card de filtros (`card card-body bg-light`)** |
| *`bg-primary`* | **Fondo azul** | ***BADGE DE CATEGORÍA EN LISTADO DE PELÍCULAS*** |
| ***`bg-success`*** | *Fondo verde* | **Badge de rol admin en la navbar** |
| **`bg-info`** | ***FONDO CELESTE*** | *Badge de rol usuario en la navbar* |
| *`bg-secondary`* | **Fondo gris** | ***BADGE DE NOMBRE DE ETIQUETA EN EL LISTADO*** |

### `CLASES DE TEXTO (text-*)`

| CLASE | QUÉ HACE | DÓNDE SE USA EN EL PROYECTO |
|---|---|---|
| ***`text-white`*** | *Texto blanco* | **Card header del login/registro (`bg-dark text-white`)** |
| **`text-danger`** | ***TEXTO ROJO*** | *Enlace "Salir" en la navbar* |
| *`text-muted`* | **Texto gris suave** | ***"SIN CATEGORÍA" EN EL LISTADO, TEXTO DE AYUDA EN FORMULARIOS*** |
| ***`text-center`*** | *Texto centrado* | **Cabecera de cards, pie de cards, mensaje "no se encontraron..."** |

### `EJEMPLO DEL PROYECTO: BADGE CON COLORES`

*Archivo: `app/Views/layout/main.php` (navbar)*

```html
<!-- BADGE CON COLOR DINÁMICO SEGÚN EL ROL DEL USUARIO -->
<span class="badge <?= session()->get('usuario_rol') === 'admin' ? 'bg-success' : 'bg-info' ?>">
    <?= esc(strtoupper(session()->get('usuario_rol'))) ?>
</span>
```

***SI ES ADMIN → `bg-success` → BADGE VERDE CON TEXTO "ADMIN"***
**Si es usuario → `bg-info` → badge celeste con texto "USUARIO"**

---

## `NAVBAR (BARRA DE NAVEGACIÓN) 🧭`

> [!NOTE]
> ***LA NAVBAR ES EL COMPONENTE MÁS COMPLEJO DE BOOTSTRAP USADO EN EL PROYECTO.*** **Es la barra superior que aparece en todas las páginas** *y contiene el logo, los enlaces de navegación y la información del usuario.* ***ES RESPONSIVA: EN ESCRITORIO MUESTRA TODOS LOS ENLACES, EN MÓVIL LOS COLAPSA EN UN MENÚ HAMBURGUESA***

### `ESTRUCTURA COMPLETA DE LA NAVBAR DEL PROYECTO`

*Archivo: `app/Views/layout/main.php`*

```html
<nav class="navbar navbar-expand-lg navbar-dark bg-dark">
    <div class="container">
        <a class="navbar-brand" href="<?= base_url('/') ?>">CI4 Udemy</a>
        <button class="navbar-toggler" type="button"
                data-bs-toggle="collapse" data-bs-target="#navbarNav">
            <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
            <!-- MENÚ IZQUIERDA -->
            <ul class="navbar-nav me-auto">
                <?php if (session()->get('logueado')): ?>
                    <li class="nav-item">
                        <a class="nav-link" href="<?= base_url('/peliculas') ?>">
                            <i class="fa fa-film"></i> Películas
                        </a>
                    </li>
                    <!-- ... más enlaces ... -->
                <?php endif; ?>
            </ul>
            <!-- MENÚ DERECHA -->
            <ul class="navbar-nav">
                <!-- USUARIO LOGUEADO O ENLACES LOGIN/REGISTRO -->
            </ul>
        </div>
    </div>
</nav>
```

### `DESGLOSE DE CADA CLASE DE LA NAVBAR`

| CLASE | QUÉ HACE |
|---|---|
| ***`navbar`*** | *Componente base de barra de navegación (obligatorio)* |
| **`navbar-expand-lg`** | ***EN PANTALLAS ≥992px SE EXPANDE MOSTRANDO TODOS LOS ENLACES. EN PANTALLAS MENORES SE COLAPSA EN MENÚ HAMBURGUESA*** |
| *`navbar-dark`* | **Estilo de texto claro (blanco/gris) para usar con fondos oscuros** |
| ***`bg-dark`*** | *Fondo de color oscuro (casi negro)* |
| **`container`** | ***CENTRA EL CONTENIDO DE LA NAVBAR CON MÁRGENES*** |
| *`navbar-brand`* | **El logo o nombre de la aplicación (más grande y destacado)** |
| ***`navbar-toggler`*** | *El botón hamburguesa (☰) que solo aparece en pantallas pequeñas* |
| **`navbar-toggler-icon`** | ***EL ÍCONO DE TRES LÍNEAS (☰) DENTRO DEL BOTÓN HAMBURGUESA*** |
| *`collapse navbar-collapse`* | **Contenedor de enlaces que se colapsa/expande en responsive** |
| ***`navbar-nav`*** | *Lista de elementos de navegación (reemplaza el estilo de `<ul>`)* |
| **`nav-item`** | ***UN ELEMENTO INDIVIDUAL DEL MENÚ (`<li>`)*** |
| *`nav-link`* | **Un enlace dentro del menú (`<a>`) con estilos de navegación** |
| ***`me-auto`*** | *Margin-End automático → empuja todo lo que viene después hacia la derecha* |

### `ATRIBUTOS data-bs-* (JAVASCRIPT DE BOOTSTRAP)`

| ATRIBUTO | VALOR | QUÉ HACE |
|---|---|---|
| ***`data-bs-toggle="collapse"`*** | **En el botón hamburguesa** | *Le dice a Bootstrap que este botón abre/cierra un elemento colapsable* |
| **`data-bs-target="#navbarNav"`** | ***EN EL BOTÓN HAMBURGUESA*** | **Indica qué elemento colapsar (el div con id="navbarNav")** |
| *`data-bs-dismiss="alert"`* | **En el botón X de alertas** | ***LE DICE A BOOTSTRAP QUE ESTE BOTÓN CIERRA LA ALERTA*** |

### `NAVBAR DINÁMICA SEGÚN ESTADO DE SESIÓN`

***LA NAVBAR DEL PROYECTO CAMBIA SU CONTENIDO SEGÚN SI EL USUARIO ESTÁ LOGUEADO O NO:***

| ESTADO | MENÚ IZQUIERDA | MENÚ DERECHA |
|---|---|---|
| **Sin loguearse** | *Vacío (no se muestran películas, categorías ni etiquetas)* | ***"ENTRAR" Y "REGISTRARSE"*** |
| *Logueado* | ***PELÍCULAS, CATEGORÍAS, ETIQUETAS*** | **Nombre + badge de rol + "Salir"** |

---

## `CARDS (TARJETAS) 🃏`

> [!NOTE]
> **Las cards son contenedores flexibles con bordes redondeados** ***QUE SE USAN PARA AGRUPAR CONTENIDO RELACIONADO.*** *En el proyecto se usan para los formularios de login/registro y para las barras de filtros*

### `ESTRUCTURA DE UNA CARD`

```html
<div class="card">
    <div class="card-header">
        Cabecera (opcional)
    </div>
    <div class="card-body">
        Contenido principal
    </div>
    <div class="card-footer">
        Pie (opcional)
    </div>
</div>
```

### `USO EN EL PROYECTO: FORMULARIO DE LOGIN`

***ARCHIVO: `app/Views/auth/login.php`***

```html
<div class="card shadow mt-4">
    <div class="card-header bg-dark text-white text-center">
        <h3><i class="fa fa-user-lock"></i> Iniciar Sesión</h3>
    </div>
    <div class="card-body">
        <form action="<?= base_url('/auth/loginPost') ?>" method="POST">
            <!-- CAMPOS DEL FORMULARIO -->
        </form>
    </div>
    <div class="card-footer text-center">
        ¿No tienes cuenta? <a href="<?= base_url('/auth/registro') ?>">Regístrate aquí</a>
    </div>
</div>
```

| CLASE | QUÉ HACE |
|---|---|
| ***`card`*** | *Componente tarjeta base (borde, bordes redondeados, fondo blanco)* |
| **`shadow`** | ***AÑADE UNA SOMBRA SUTIL DEBAJO DE LA TARJETA (EFECTO DE PROFUNDIDAD)*** |
| *`card-header`* | **Sección superior de la tarjeta (con borde inferior)** |
| ***`card-body`*** | *Sección central de la tarjeta (con padding)* |
| **`card-footer`** | ***SECCIÓN INFERIOR DE LA TARJETA (CON BORDE SUPERIOR)*** |

### `USO EN EL PROYECTO: BARRA DE FILTROS`

*Archivo: `app/Views/peliculas/index.php`*

```html
<form action="<?= base_url('/peliculas') ?>" method="GET"
      class="card card-body bg-light mb-4">
    <!-- CAMPOS DE FILTRO -->
</form>
```

| CLASE | QUÉ HACE |
|---|---|
| ***`card card-body`*** | **Tarjeta que directamente es su propio cuerpo (sin header ni footer)** |
| *`bg-light`* | ***FONDO GRIS CLARO PARA DISTINGUIRLO DEL FONDO BLANCO*** |
| **`mb-4`** | *Margen inferior de 1.5rem (espacio entre filtros y tabla)* |

---

## `TABLAS 📊`

> [!NOTE]
> ***LAS TABLAS DE BOOTSTRAP SON TABLAS HTML ESTÁNDAR*** **(`<table>`) a las que se les añaden clases** *para darles un aspecto profesional.* ***EN EL PROYECTO SE USAN EN LOS TRES LISTADOS: PELÍCULAS, CATEGORÍAS Y ETIQUETAS***

### `CLASES DE TABLA DISPONIBLES`

| CLASE | QUÉ HACE |
|---|---|
| ***`table`*** | *Clase base que aplica los estilos de Bootstrap a la tabla (obligatoria)* |
| **`table-bordered`** | ***AÑADE BORDES EN TODAS LAS CELDAS (HORIZONTAL Y VERTICAL)*** |
| *`table-striped`* | **Filas alternas con fondo gris claro (efecto cebra para mejor legibilidad)** |
| ***`table-hover`*** | *Al pasar el ratón sobre una fila, se resalta con un fondo gris* |
| **`table-dark`** | ***FONDO OSCURO (SE USA EN `<thead>` PARA LA CABECERA)*** |
| *`table-sm`* | **Tabla compacta (menos padding en las celdas)** |
| ***`table-responsive`*** | *Contenedor que añade scroll horizontal en pantallas pequeñas* |
| **`table-borderless`** | ***TABLA SIN BORDES*** |
| *`table-primary`* | **Fila o celda con fondo azul** |
| ***`table-success`*** | *Fila o celda con fondo verde* |
| **`table-danger`** | ***FILA O CELDA CON FONDO ROJO*** |

### `USO EN EL PROYECTO: LISTADO DE PELÍCULAS`

*Archivo: `app/Views/peliculas/index.php`*

```html
<div class="table-responsive">
    <table class="table table-bordered table-striped table-hover">
        <thead class="table-dark">
            <tr>
                <th>ID</th>
                <th>Imagen</th>
                <th>Título</th>
                <th>Categoría</th>
                <th>Descripción</th>
                <th>Creado</th>
                <th>Acciones</th>
            </tr>
        </thead>
        <tbody>
            <?php foreach ($peliculas as $pelicula): ?>
                <tr>
                    <td><?= $pelicula['id'] ?></td>
                    <td><img src="..." class="img-thumbnail" style="max-height: 60px;"></td>
                    <td><?= esc($pelicula['titulo']) ?></td>
                    <td><span class="badge bg-primary"><?= esc($pelicula['categoria_nombre']) ?></span></td>
                    <td><?= character_limiter(esc($pelicula['descripcion'] ?? ''), 60) ?></td>
                    <td><?= $pelicula['created_at'] ?></td>
                    <td>
                        <!-- BOTONES EDITAR Y ELIMINAR -->
                    </td>
                </tr>
            <?php endforeach; ?>
        </tbody>
    </table>
</div>
```

---

## `FORMULARIOS 📝`

> [!NOTE]
> **Bootstrap proporciona estilos para todos los elementos de formulario:** *inputs, textareas, selects, checkboxes, radio buttons y botones.* ***EN EL PROYECTO SE USAN EN LOS FORMULARIOS DE CRUD (CREAR/EDITAR) Y EN LOGIN/REGISTRO***

### `CLASES DE FORMULARIO`

| CLASE | ELEMENTO | QUÉ HACE |
|---|---|---|
| ***`form-label`*** | *`<label>`* | **Estilo para la etiqueta del campo (negrita ligera, margen inferior)** |
| **`form-control`** | ***`<input>`, `<textarea>`*** | *Estilo principal: borde, padding, ancho 100%, bordes redondeados, foco azul* |
| *`form-select`* | **`<select>`** | ***ESTILO PARA DESPLEGABLES (SIMILAR A form-control PERO CON FLECHA)*** |
| ***`form-check`*** | *`<div>` contenedor* | **Contenedor para checkbox o radio button** |
| **`form-check-input`** | ***`<input type="checkbox/radio">`*** | *Estilo para el checkbox o radio en sí* |
| *`form-check-label`* | **`<label>`** | ***ESTILO PARA LA ETIQUETA DEL CHECKBOX/RADIO*** |
| ***`form-text`*** | *`<div>` o `<small>`* | **Texto de ayuda debajo de un campo (gris, pequeño)** |
| **`form-floating`** | ***`<div>` CONTENEDOR*** | *Label flotante que se mueve al escribir (no usado en el proyecto)* |

### `EJEMPLO COMPLETO DEL PROYECTO: FORMULARIO DE CREAR PELÍCULA`

***ARCHIVO: `app/Views/peliculas/create.php`***

```html
<form action="<?= base_url('/peliculas/store') ?>" method="POST"
      enctype="multipart/form-data">
    <?= csrf_field() ?>

    <!-- INPUT TEXT CON form-control -->
    <div class="mb-3">
        <label for="titulo" class="form-label">Título</label>
        <input type="text" class="form-control" id="titulo" name="titulo"
               value="<?= old('titulo') ?>" required>
    </div>

    <!-- TEXTAREA CON form-control -->
    <div class="mb-3">
        <label for="descripcion" class="form-label">Descripción</label>
        <textarea class="form-control" id="descripcion" name="descripcion"
                  rows="4"><?= old('descripcion') ?></textarea>
    </div>

    <!-- SELECT CON form-select -->
    <div class="mb-3">
        <label for="categoria_id" class="form-label">Categoría</label>
        <select class="form-select" id="categoria_id" name="categoria_id">
            <option value="">-- Seleccionar categoría --</option>
            <?php foreach ($categorias as $categoria): ?>
                <option value="<?= $categoria['id'] ?>"><?= esc($categoria['titulo']) ?></option>
            <?php endforeach; ?>
        </select>
    </div>

    <!-- CHECKBOXES CON form-check -->
    <div class="mb-3">
        <label class="form-label">Etiquetas</label>
        <div class="row">
            <?php foreach ($etiquetas as $etiqueta): ?>
                <div class="col-md-3 col-6">
                    <div class="form-check">
                        <input class="form-check-input" type="checkbox"
                               name="etiquetas[]" value="<?= $etiqueta['id'] ?>">
                        <label class="form-check-label">
                            <?= esc($etiqueta['nombre']) ?>
                        </label>
                    </div>
                </div>
            <?php endforeach; ?>
        </div>
    </div>

    <!-- INPUT FILE CON form-control + form-text -->
    <div class="mb-3">
        <label for="imagen" class="form-label">Imagen (opcional, máx. 2MB)</label>
        <input type="file" class="form-control" id="imagen" name="imagen" accept="image/*">
        <div class="form-text">FORMATOS PERMITIDOS: JPG, JPEG, PNG, GIF. TAMAÑO MÁXIMO: 2MB</div>
    </div>

    <a href="<?= base_url('/peliculas') ?>" class="btn btn-secondary">Volver</a>
    <button type="submit" class="btn btn-primary">Guardar</button>
</form>
```

### `PATRÓN PARA CADA CAMPO: div.mb-3 > label.form-label + input.form-control`

**Todos los campos del proyecto siguen el mismo patrón:**

```html
<div class="mb-3">                              <!-- CONTENEDOR CON MARGEN INFERIOR -->
    <label for="campo" class="form-label">       <!-- ETIQUETA CON ESTILO -->
        Nombre del campo
    </label>
    <input type="text" class="form-control"      <!-- INPUT CON ESTILO -->
           id="campo" name="campo">
</div>
```

---

## `BOTONES 🔘`

> [!NOTE]
> ***LOS BOTONES DE BOOTSTRAP SE CREAN CON LA CLASE BASE `btn`*** **combinada con una clase de color.** *Se pueden aplicar a `<button>`, `<a>` o `<input>`.* ***EN EL PROYECTO SE USAN BOTONES DE TODOS LOS COLORES Y TAMAÑOS***

### `TODOS LOS TIPOS DE BOTÓN`

| CLASE | COLOR | USO EN EL PROYECTO |
|---|---|---|
| ***`btn btn-primary`*** | **Azul (relleno)** | *Guardar, crear nuevo, entrar (login)* |
| **`btn btn-secondary`** | ***GRIS (RELLENO)*** | **Volver al listado** |
| *`btn btn-success`* | **Verde (relleno)** | ***BOTÓN DE REGISTRARSE*** |
| ***`btn btn-danger`*** | *Rojo (relleno)* | **Eliminar** |
| **`btn btn-warning`** | ***AMARILLO (RELLENO)*** | *Editar* |
| *`btn btn-info`* | **Celeste (relleno)** | ***INFORMACIÓN (NO USADO EN EL PROYECTO)*** |
| ***`btn btn-dark`*** | *Oscuro (relleno)* | **Botón filtrar en la barra de filtros** |
| **`btn btn-light`** | ***GRIS CLARO (RELLENO)*** | *(No usado en el proyecto)* |
| *`btn btn-outline-primary`* | **Azul (solo borde)** | ***(NO USADO EN EL PROYECTO)*** |
| ***`btn btn-outline-secondary`*** | *Gris (solo borde)* | **Botón limpiar filtros** |

### `TAMAÑOS DE BOTÓN`

| CLASE | TAMAÑO | USO EN EL PROYECTO |
|---|---|---|
| **`btn btn-lg`** | ***GRANDE*** | *(No usado)* |
| ***`btn`*** | **Normal** | *Guardar, volver, filtrar* |
| *`btn btn-sm`* | ***PEQUEÑO*** | **Editar y eliminar en las tablas** |

### `BOTONES ANCHOS`

| CLASE | QUÉ HACE | USO EN EL PROYECTO |
|---|---|---|
| ***`w-100`*** | *Width 100% (ocupa todo el ancho)* | **Botón filtrar y limpiar en filtros de películas** |
| **`d-grid`** | ***DISPLAY GRID (BOTÓN OCUPA TODO EL ANCHO DEL CONTENEDOR)*** | *Botón "Entrar" en login y "Registrarse"* |

### `TODOS LOS BOTONES DEL PROYECTO`

```html
<!-- GUARDAR (CREAR) - AZUL -->
<button type="submit" class="btn btn-primary">
    <i class="fa fa-save"></i> Guardar
</button>

<!-- ACTUALIZAR (EDITAR) - AZUL -->
<button type="submit" class="btn btn-primary">
    <i class="fa fa-save"></i> Actualizar
</button>

<!-- VOLVER AL LISTADO - GRIS -->
<a href="<?= base_url('/peliculas') ?>" class="btn btn-secondary">
    <i class="fa fa-arrow-left"></i> Volver
</a>

<!-- CREAR NUEVO - AZUL -->
<a href="<?= base_url('/peliculas/create') ?>" class="btn btn-primary">
    <i class="fa fa-plus"></i> Nueva Película
</a>

<!-- EDITAR - AMARILLO PEQUEÑO -->
<a href="..." class="btn btn-sm btn-warning">
    <i class="fa fa-edit"></i>
</a>

<!-- ELIMINAR - ROJO PEQUEÑO -->
<button type="submit" class="btn btn-sm btn-danger">
    <i class="fa fa-trash"></i>
</button>

<!-- FILTRAR - OSCURO ANCHO -->
<button type="submit" class="btn btn-dark w-100 mb-2">
    <i class="fa fa-filter"></i> Filtrar
</button>

<!-- LIMPIAR - BORDE GRIS ANCHO -->
<a href="..." class="btn btn-outline-secondary w-100">
    <i class="fa fa-times"></i> Limpiar
</a>

<!-- ENTRAR (LOGIN) - AZUL ANCHO -->
<div class="d-grid">
    <button type="submit" class="btn btn-primary">
        <i class="fa fa-sign-in-alt"></i> Entrar
    </button>
</div>

<!-- REGISTRARSE - VERDE ANCHO -->
<div class="d-grid">
    <button type="submit" class="btn btn-success">
        <i class="fa fa-user-plus"></i> Registrarse
    </button>
</div>
```

---

## `ALERTAS (MENSAJES) ⚠️`

> [!NOTE]
> **Las alertas son cajas de mensaje con colores semánticos.** ***EN EL PROYECTO SE USAN PARA MOSTRAR MENSAJES DE ÉXITO (VERDE) Y ERROR (ROJO)*** *después de cada acción CRUD o intento de login*

### `TIPOS DE ALERTA`

| CLASE | COLOR | USO EN EL PROYECTO |
|---|---|---|
| ***`alert alert-success`*** | **Verde** | *"Película creada correctamente", "Bienvenido, usuario!"* |
| **`alert alert-danger`** | ***ROJO*** | **"Credenciales incorrectas", "Debes iniciar sesión", errores de validación** |
| *`alert alert-warning`* | **Amarillo** | ***(DISPONIBLE PERO NO USADO EN EL PROYECTO)*** |
| ***`alert alert-info`*** | *Celeste* | **(Disponible pero no usado en el proyecto)** |
| *`alert alert-primary`* | ***AZUL*** | *(Disponible pero no usado en el proyecto)* |

### `ALERTAS DESCARTABLES (CON BOTÓN X)`

***ARCHIVO: `app/Views/layout/main.php`***

```html
<!-- ALERTA DE ÉXITO (VERDE) CON BOTÓN PARA CERRAR -->
<?php if (session()->getFlashdata('mensaje')): ?>
    <div class="alert alert-success alert-dismissible fade show">
        <?= session()->getFlashdata('mensaje') ?>
        <button type="button" class="btn-close" data-bs-dismiss="alert"></button>
    </div>
<?php endif; ?>

<!-- ALERTA DE ERROR (ROJA) CON BOTÓN PARA CERRAR -->
<?php if (session()->getFlashdata('error')): ?>
    <div class="alert alert-danger alert-dismissible fade show">
        <?= session()->getFlashdata('error') ?>
        <button type="button" class="btn-close" data-bs-dismiss="alert"></button>
    </div>
<?php endif; ?>
```

| CLASE | QUÉ HACE |
|---|---|
| ***`alert`*** | *Clase base de alerta (padding, bordes, margen)* |
| **`alert-success`** | ***COLOR VERDE (FONDO Y BORDE)*** |
| *`alert-danger`* | **Color rojo (fondo y borde)** |
| ***`alert-dismissible`*** | *Permite cerrar la alerta (añade espacio para el botón X)* |
| **`fade show`** | ***ANIMACIÓN DE APARICIÓN Y DESAPARICIÓN SUAVE*** |
| *`btn-close`* | **Botón X para cerrar (requiere `data-bs-dismiss="alert"`)** |

### `ALERTAS CON LISTA DE ERRORES DE VALIDACIÓN`

*Archivo: `app/Views/peliculas/create.php` (y todos los formularios)*

```html
<?php if (session()->getFlashdata('errors')): ?>
    <div class="alert alert-danger">
        <ul class="mb-0">
            <?php foreach (session()->getFlashdata('errors') as $error): ?>
                <li><?= esc($error) ?></li>
            <?php endforeach; ?>
        </ul>
    </div>
<?php endif; ?>
```

**`mb-0` en la `<ul>` elimina el margen inferior por defecto de la lista,** ***PARA QUE NO QUEDE ESPACIO EXTRA DENTRO DE LA ALERTA***

---

## `BADGES (INSIGNIAS/ETIQUETAS) 🏅`

> [!NOTE]
> ***LOS BADGES SON PEQUEÑAS ETIQUETAS REDONDEADAS CON FONDO DE COLOR.*** **Se usan para mostrar información breve y categorizada** *como roles, estados o categorías*

### `USO EN EL PROYECTO`

| DÓNDE | CLASE | QUÉ MUESTRA |
|---|---|---|
| ***NAVBAR (ROL ADMIN)*** | **`badge bg-success`** | *Badge verde con texto "ADMIN"* |
| **Navbar (rol usuario)** | ***`badge bg-info`*** | **Badge celeste con texto "USUARIO"** |
| *Listado películas (categoría)* | **`badge bg-primary`** | ***BADGE AZUL CON EL NOMBRE DE LA CATEGORÍA*** |
| ***LISTADO ETIQUETAS (NOMBRE)*** | *`badge bg-secondary`* | **Badge gris con el nombre de la etiqueta** |

### `EJEMPLOS DEL PROYECTO`

```html
<!-- BADGE DE ROL EN LA NAVBAR -->
<span class="badge bg-success">ADMIN</span>
<span class="badge bg-info">USUARIO</span>

<!-- BADGE DE CATEGORÍA EN EL LISTADO DE PELÍCULAS -->
<span class="badge bg-primary"><?= esc($pelicula['categoria_nombre']) ?></span>

<!-- BADGE DE ETIQUETA EN EL LISTADO DE ETIQUETAS -->
<span class="badge bg-secondary"><?= esc($etiqueta['nombre']) ?></span>
```

### `TODOS LOS COLORES DE BADGE`

| CLASE | COLOR |
|---|---|
| ***`badge bg-primary`*** | **Azul** |
| *`badge bg-secondary`* | ***GRIS*** |
| **`badge bg-success`** | *Verde* |
| ***`badge bg-danger`*** | **Rojo** |
| *`badge bg-warning text-dark`* | ***AMARILLO (CON TEXTO OSCURO PARA QUE SE LEA)*** |
| **`badge bg-info`** | *Celeste* |
| ***`badge bg-light text-dark`*** | **Gris claro (con texto oscuro)** |
| *`badge bg-dark`* | ***OSCURO*** |

---

## `UTILIDADES DE DISPLAY Y FLEXBOX 📐`

> [!NOTE]
> **Bootstrap proporciona clases de utilidad para controlar el display CSS y flexbox** ***SIN ESCRIBIR CSS.*** *Estas clases se usan mucho en el proyecto para alinear elementos, centrar contenido y distribuir espacio*

### `CLASES DE DISPLAY`

| CLASE | CSS EQUIVALENTE | USO EN EL PROYECTO |
|---|---|---|
| ***`d-none`*** | *`display: none`* | **Ocultar un elemento** |
| **`d-block`** | ***`display: block`*** | *Mostrar como bloque* |
| *`d-inline`* | **`display: inline`** | ***FORMULARIO DE ELIMINAR EN LÍNEA CON BOTÓN DE EDITAR*** |
| ***`d-flex`*** | *`display: flex`* | **Contenedor flex para alinear elementos** |
| **`d-grid`** | ***`display: grid`*** | *Botón ancho en login/registro* |
| *`d-none d-md-block`* | **Oculto en móvil, visible en tablet+** | ***RESPONSIVE: OCULTAR/MOSTRAR*** |

### `CLASES DE FLEXBOX`

| CLASE | QUÉ HACE | USO EN EL PROYECTO |
|---|---|---|
| ***`d-flex`*** | **Activa flexbox en el contenedor** | *Cabecera de listados* |
| **`justify-content-between`** | ***HIJOS SEPARADOS A LOS EXTREMOS (IZQUIERDA Y DERECHA)*** | **Título + botón "Nueva Película"** |
| *`justify-content-center`* | **Hijos centrados horizontalmente** | ***PAGINACIÓN, FORMULARIO LOGIN*** |
| ***`align-items-center`*** | *Hijos centrados verticalmente* | **Cabecera de listados (título + botón alineados)** |
| **`align-items-end`** | ***HIJOS ALINEADOS AL FONDO*** | *Barra de filtros (labels con diferente altura)* |

### `EJEMPLO DEL PROYECTO: CABECERA DE LISTADOS`

*Archivo: `app/Views/peliculas/index.php`*

```html
<div class="d-flex justify-content-between align-items-center mb-3">
    <h1>Películas</h1>
    <a href="<?= base_url('/peliculas/create') ?>" class="btn btn-primary">
        <i class="fa fa-plus"></i> Nueva Película
    </a>
</div>
```

***RESULTADO VISUAL:***

```
┌──────────────────────────────────────────────────────────────┐
│ Películas                                  [+ Nueva Película]│
│ ← justify-content-between los separa a los extremos          │
│ ← align-items-center los alinea verticalmente                │
└──────────────────────────────────────────────────────────────┘
```

### `EJEMPLO DEL PROYECTO: BOTONES EDITAR Y ELIMINAR EN LÍNEA`

**Archivo: `app/Views/peliculas/index.php`**

```html
<td>
    <a href="..." class="btn btn-sm btn-warning">
        <i class="fa fa-edit"></i>
    </a>
    <form action="..." method="POST" class="d-inline">
        <button class="btn btn-sm btn-danger">
            <i class="fa fa-trash"></i>
        </button>
    </form>
</td>
```

*Sin `d-inline`, el `<form>` ocuparía toda la fila y el botón rojo iría debajo del amarillo.* ***CON `d-inline`, QUEDAN UNO AL LADO DEL OTRO***

---

## `IMÁGENES 🖼️`

> [!NOTE]
> ***BOOTSTRAP PROPORCIONA CLASES PARA ESTILIZAR IMÁGENES.*** **En el proyecto se usa `img-thumbnail`** *para las imágenes de las películas*

### `CLASES DE IMAGEN`

| CLASE | QUÉ HACE | USO EN EL PROYECTO |
|---|---|---|
| **`img-fluid`** | *Hace la imagen responsiva (max-width: 100%, height: auto)* | ***(NO USADO)*** |
| ***`img-thumbnail`*** | **Añade borde, bordes redondeados y padding a la imagen** | *Imágenes de películas en listado y edición* |
| *`rounded`* | ***BORDES REDONDEADOS*** | **(No usado)** |
| ***`rounded-circle`*** | *Imagen circular* | **(No usado, pero útil para avatares)** |

### `EJEMPLO DEL PROYECTO`

```html
<!-- EN EL LISTADO DE PELÍCULAS (MINIATURA) -->
<img src="<?= base_url('uploads/peliculas/' . $pelicula['imagen']) ?>"
     alt="Imagen" class="img-thumbnail" style="max-height: 60px;">

<!-- EN EL FORMULARIO DE EDICIÓN (PREVIEW GRANDE) -->
<img src="<?= base_url('uploads/peliculas/' . $pelicula['imagen']) ?>"
     alt="Imagen actual" class="img-thumbnail" style="max-height: 200px;">
```

---

## `SOMBRAS Y BORDES 🔲`

### `SOMBRAS`

| CLASE | QUÉ HACE | USO EN EL PROYECTO |
|---|---|---|
| **`shadow-none`** | *Sin sombra* | ***(NO USADO)*** |
| *`shadow-sm`* | ***SOMBRA PEQUEÑA*** | **(No usado)** |
| ***`shadow`*** | **Sombra normal** | *Cards de login y registro* |
| **`shadow-lg`** | ***SOMBRA GRANDE*** | *(No usado)* |

### `BORDES`

| CLASE | QUÉ HACE |
|---|---|
| ***`border`*** | *Borde en los 4 lados* |
| **`border-0`** | ***SIN BORDES*** |
| *`border-top`* | **Solo borde superior** |
| ***`border-primary`*** | *Borde azul* |
| **`rounded`** | ***BORDES REDONDEADOS*** |
| *`rounded-0`* | **Sin redondear (esquinas cuadradas)** |
| ***`rounded-circle`*** | *Completamente circular* |
| **`rounded-pill`** | ***FORMA DE PÍLDORA (BORDES MUY REDONDEADOS)*** |

---

## `UTILIDADES DE TAMAÑO (WIDTH Y HEIGHT) 📐`

| CLASE | QUÉ HACE | USO EN EL PROYECTO |
|---|---|---|
| **`w-25`** | *width: 25%* | ***(NO USADO)*** |
| *`w-50`* | ***width: 50%*** | **(No usado)** |
| ***`w-75`*** | **width: 75%** | *(No usado)* |
| **`w-100`** | ***width: 100%*** | **Botones filtrar y limpiar (ancho completo)** |
| *`w-auto`* | **width: auto** | ***(NO USADO)*** |
| ***`h-100`*** | *height: 100%* | **(No usado)** |
| **`mw-100`** | ***max-width: 100%*** | *(No usado)* |
| *`vh-100`* | **height: 100vh (toda la ventana)** | ***(NO USADO)*** |

---

## `TIPOGRAFÍA ✏️`

> [!NOTE]
> ***BOOTSTRAP MODIFICA LA TIPOGRAFÍA BASE DE LA PÁGINA*** **y proporciona clases para controlar tamaño, peso y estilo del texto**

### `CLASES DE TIPOGRAFÍA`

| CLASE | QUÉ HACE | USO EN EL PROYECTO |
|---|---|---|
| ***`fw-bold`*** | *Font-weight bold (negrita)* | **Labels de los filtros** |
| **`fw-light`** | ***FONT-WEIGHT LIGHT*** | *(No usado)* |
| *`fst-italic`* | **Font-style italic (cursiva)** | ***(NO USADO)*** |
| ***`text-decoration-none`*** | *Quita el subrayado de los enlaces* | **(No usado)** |
| **`text-uppercase`** | ***TEXTO EN MAYÚSCULAS*** | *(No usado, se hace con PHP strtoupper())* |
| *`text-lowercase`* | **Texto en minúsculas** | ***(NO USADO)*** |
| ***`text-capitalize`*** | *Primera letra mayúscula* | **(No usado)** |
| **`fs-1` a `fs-6`** | ***TAMAÑO DE FUENTE (1=MÁS GRANDE, 6=MÁS PEQUEÑO)*** | *(No usado, se usan `<h1>` a `<h6>`)* |
| *`lead`* | **Párrafo más grande y destacado** | ***(NO USADO)*** |

### `EJEMPLO DEL PROYECTO: LABELS EN NEGRITA`

***ARCHIVO: `app/Views/peliculas/index.php`***

```html
<label for="busqueda" class="form-label fw-bold">
    <i class="fa fa-search"></i> Buscar
</label>
```

**`fw-bold` hace que el texto "Buscar" aparezca en negrita**

---

## `PAGINACIÓN 📄`

> [!NOTE]
> **CodeIgniter 4 genera automáticamente los enlaces de paginación** ***CON ESTILOS DE BOOTSTRAP*** *usando la plantilla `default_full`.* **Los enlaces aparecen como botones numerados** *(1, 2, 3, Anterior, Siguiente)*

### `CÓDIGO EN LA VISTA`

*Archivo: `app/Views/peliculas/index.php`* ***(y categorias/index.php, etiquetas/index.php)***

```html
<?php if (isset($pager)): ?>
    <div class="d-flex justify-content-center mt-3">
        <?= $pager->links('default', 'default_full') ?>
    </div>
<?php endif; ?>
```

| PARTE | QUÉ HACE |
|---|---|
| ***`$pager->links()`*** | *Genera el HTML de los enlaces de paginación* |
| **`'default'`** | ***GRUPO POR DEFECTO (EL MODELO GENERA UNO AUTOMÁTICAMENTE)*** |
| *`'default_full'`* | **Plantilla de Bootstrap con anterior, siguiente y números** |
| ***`d-flex justify-content-center`*** | *Centra los enlaces horizontalmente* |
| **`mt-3`** | ***MARGEN SUPERIOR DE 1rem ENTRE LA TABLA Y LA PAGINACIÓN*** |

**Bootstrap genera algo como esto:**

```html
<nav>
    <ul class="pagination">
        <li class="page-item disabled"><a class="page-link">« Anterior</a></li>
        <li class="page-item active"><a class="page-link">1</a></li>
        <li class="page-item"><a class="page-link" href="?page=2">2</a></li>
        <li class="page-item"><a class="page-link" href="?page=3">3</a></li>
        <li class="page-item"><a class="page-link" href="?page=2">Siguiente »</a></li>
    </ul>
</nav>
```

| CLASE | QUÉ HACE |
|---|---|
| ***`pagination`*** | **Estilo base de la lista de paginación** |
| *`page-item`* | ***UN ELEMENTO DE LA PAGINACIÓN*** |
| **`page-link`** | *Un enlace de la paginación* |
| ***`active`*** | **Página actual (resaltada en azul)** |
| *`disabled`* | ***ENLACE DESHABILITADO (GRIS, NO CLICKEABLE)*** |

---

## `FONT AWESOME (ÍCONOS) - NO ES BOOTSTRAP ⭐`

> [!IMPORTANT]
> ***FONT AWESOME NO ES PARTE DE BOOTSTRAP.*** **Son dos librerías completamente independientes que se complementan.** *Bootstrap da los estilos y Font Awesome da los íconos*

### `CÓMO SE CARGA`

```html
<link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css"
      rel="stylesheet">
```

### `CÓMO SE USA`

**Se usa un tag `<i>` (italic) con clases de Font Awesome:**

```html
<i class="fa fa-film"></i>        <!-- ÍCONO DE PELÍCULA -->
```

### `TODOS LOS ÍCONOS USADOS EN EL PROYECTO`

| CLASE | ÍCONO | DÓNDE SE USA |
|---|---|---|
| ***`fa fa-film`*** | *Película* | **Enlace "Películas" en la navbar** |
| **`fa fa-tags`** | ***ETIQUETAS*** | *Enlace "Categorías" en la navbar* |
| *`fa fa-bookmark`* | **Marcador** | ***ENLACE "ETIQUETAS" EN LA NAVBAR*** |
| ***`fa fa-user`*** | *Usuario* | **Nombre del usuario en la navbar** |
| **`fa fa-user-lock`** | ***CANDADO*** | *Título del formulario de login* |
| *`fa fa-user-plus`* | **Usuario+** | ***TÍTULO DEL FORMULARIO DE REGISTRO*** |
| ***`fa fa-sign-in-alt`*** | *Entrar* | **Botón "Entrar" en navbar y login** |
| **`fa fa-sign-out-alt`** | ***SALIR*** | *Botón "Salir" en la navbar* |
| *`fa fa-plus`* | **Más** | ***BOTONES "NUEVA PELÍCULA/CATEGORÍA/ETIQUETA"*** |
| ***`fa fa-edit`*** | *Lápiz* | **Botones de editar en las tablas** |
| **`fa fa-trash`** | ***PAPELERA*** | *Botones de eliminar en las tablas* |
| *`fa fa-save`* | **Disquete** | ***BOTONES "GUARDAR" Y "ACTUALIZAR"*** |
| ***`fa fa-arrow-left`*** | *Flecha* | **Botones "Volver"** |
| **`fa fa-search`** | ***LUPA*** | *Label "Buscar" en los filtros* |
| *`fa fa-filter`* | **Embudo** | ***BOTÓN "FILTRAR"*** |
| ***`fa fa-times`*** | *X* | **Botón "Limpiar" filtros** |
| **`fa fa-folder`** | ***CARPETA*** | *Label "Categoría" en los filtros* |
| *`fa fa-tag`* | **Etiqueta** | ***LABEL "ETIQUETA" EN LOS FILTROS*** |
| ***`fa fa-image`*** | *Imagen* | **Placeholder cuando no hay imagen** |

---

## `COMPONENTES BOOTSTRAP ADICIONALES (NO USADOS EN EL PROYECTO PERO ÚTILES) 📚`

> [!TIP]
> **Estos componentes no se usan en el proyecto de Udemy** ***PERO SON MUY COMUNES EN DESARROLLO WEB CON BOOTSTRAP.*** *Es bueno conocerlos para futuros proyectos*

### `MODALES (VENTANAS EMERGENTES)`

```html
<!-- BOTÓN QUE ABRE EL MODAL -->
<button class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#miModal">
    Abrir Modal
</button>

<!-- EL MODAL -->
<div class="modal fade" id="miModal">
    <div class="modal-dialog">
        <div class="modal-content">
            <div class="modal-header">
                <h5 class="modal-title">Título del Modal</h5>
                <button class="btn-close" data-bs-dismiss="modal"></button>
            </div>
            <div class="modal-body">
                <p>Contenido del modal.</p>
            </div>
            <div class="modal-footer">
                <button class="btn btn-secondary" data-bs-dismiss="modal">Cerrar</button>
                <button class="btn btn-primary">Guardar</button>
            </div>
        </div>
    </div>
</div>
```

*Ejemplo de uso: podrías usar un modal para confirmar la eliminación* ***EN VEZ DE `confirm()` DE JAVASCRIPT***

### `BREADCRUMBS (MIGAS DE PAN)`

```html
<nav aria-label="breadcrumb">
    <ol class="breadcrumb">
        <li class="breadcrumb-item"><a href="/">Inicio</a></li>
        <li class="breadcrumb-item"><a href="/peliculas">Películas</a></li>
        <li class="breadcrumb-item active">Crear</li>
    </ol>
</nav>
```

**Muestra la ruta de navegación:** ***`Inicio > Películas > Crear`***

### `ACCORDION (DESPLEGABLE)`

```html
<div class="accordion" id="miAccordion">
    <div class="accordion-item">
        <h2 class="accordion-header">
            <button class="accordion-button" data-bs-toggle="collapse"
                    data-bs-target="#seccion1">
                Sección 1
            </button>
        </h2>
        <div id="seccion1" class="accordion-collapse collapse show"
             data-bs-parent="#miAccordion">
            <div class="accordion-body">
                Contenido de la sección 1.
            </div>
        </div>
    </div>
</div>
```

### `TOOLTIPS (INFORMACIÓN AL PASAR EL RATÓN)`

```html
<!-- REQUIERE INICIALIZACIÓN CON JAVASCRIPT -->
<button class="btn btn-primary" data-bs-toggle="tooltip" title="Información extra">
    Botón con tooltip
</button>

<script>
var tooltips = document.querySelectorAll('[data-bs-toggle="tooltip"]');
tooltips.forEach(t => new bootstrap.Tooltip(t));
</script>
```

### `SPINNER (CARGANDO)`

```html
<!-- SPINNER CIRCULAR -->
<div class="spinner-border text-primary" role="status">
    <span class="visually-hidden">Cargando...</span>
</div>

<!-- SPINNER DE PUNTOS -->
<div class="spinner-grow text-primary" role="status">
    <span class="visually-hidden">Cargando...</span>
</div>
```

### `PROGRESS BAR (BARRA DE PROGRESO)`

```html
<div class="progress">
    <div class="progress-bar bg-success" style="width: 75%">75%</div>
</div>
```

### `LIST GROUP (LISTA ESTILIZADA)`

```html
<ul class="list-group">
    <li class="list-group-item active">Elemento activo</li>
    <li class="list-group-item">Segundo elemento</li>
    <li class="list-group-item list-group-item-danger">Elemento rojo</li>
</ul>
```

### `TOAST (NOTIFICACIÓN FLOTANTE)`

```html
<div class="toast" role="alert">
    <div class="toast-header">
        <strong class="me-auto">Notificación</strong>
        <button class="btn-close" data-bs-dismiss="toast"></button>
    </div>
    <div class="toast-body">
        Película creada correctamente.
    </div>
</div>
```

### `OFFCANVAS (PANEL LATERAL)`

```html
<button class="btn btn-primary" data-bs-toggle="offcanvas" data-bs-target="#miPanel">
    Abrir Panel
</button>

<div class="offcanvas offcanvas-start" id="miPanel">
    <div class="offcanvas-header">
        <h5>Menú lateral</h5>
        <button class="btn-close" data-bs-dismiss="offcanvas"></button>
    </div>
    <div class="offcanvas-body">
        Contenido del panel lateral.
    </div>
</div>
```

---

## `CHEAT SHEET: TODAS LAS CLASES USADAS EN EL PROYECTO 📋`

> [!NOTE]
> ***REFERENCIA RÁPIDA DE ABSOLUTAMENTE TODAS LAS CLASES DE BOOTSTRAP*** **que aparecen en el proyecto de Udemy,** *organizadas por categoría*

### `LAYOUT`

| CLASE | SIGNIFICADO |
|---|---|
| ***`container`*** | *Contenedor centrado con márgenes* |
| **`row`** | ***FILA DE COLUMNAS*** |
| *`col-6`* | **Columna de 50% en todos los tamaños** |
| ***`col-md-3`*** | *Columna de 25% en pantallas medianas+* |
| **`col-md-6`** | ***COLUMNA DE 50% EN PANTALLAS MEDIANAS+*** |
| *`col-md-8`* | **Columna de 66% en pantallas medianas+** |
| ***`col-md-4`*** | *Columna de 33% en pantallas medianas+* |

### `SPACING`

| CLASE | SIGNIFICADO |
|---|---|
| **`mt-2`** | ***MARGIN TOP 0.5rem*** |
| *`mt-3`* | **Margin top 1rem** |
| ***`mt-4`*** | *Margin top 1.5rem* |
| **`mb-0`** | ***MARGIN BOTTOM 0*** |
| *`mb-1`* | **Margin bottom 0.25rem** |
| ***`mb-2`*** | *Margin bottom 0.5rem* |
| **`mb-3`** | ***MARGIN BOTTOM 1rem*** |
| *`mb-4`* | **Margin bottom 1.5rem** |
| ***`me-2`*** | *Margin end 0.5rem* |
| **`me-auto`** | ***MARGIN END AUTO*** |

### `TEXTO`

| CLASE | SIGNIFICADO |
|---|---|
| ***`text-white`*** | **Color blanco** |
| *`text-danger`* | ***COLOR ROJO*** |
| **`text-muted`** | *Color gris suave* |
| ***`text-center`*** | **Centrado** |
| *`fw-bold`* | ***NEGRITA*** |

### `FONDO`

| CLASE | SIGNIFICADO |
|---|---|
| **`bg-dark`** | ***FONDO OSCURO*** |
| *`bg-light`* | **Fondo gris claro** |
| ***`bg-primary`*** | *Fondo azul* |
| **`bg-success`** | ***FONDO VERDE*** |
| *`bg-info`* | **Fondo celeste** |
| ***`bg-secondary`*** | *Fondo gris* |

### `DISPLAY Y FLEXBOX`

| CLASE | SIGNIFICADO |
|---|---|
| **`d-flex`** | ***DISPLAY FLEX*** |
| *`d-inline`* | **Display inline** |
| ***`d-grid`*** | *Display grid* |
| **`justify-content-between`** | ***SEPARAR A LOS EXTREMOS*** |
| *`justify-content-center`* | **Centrar horizontalmente** |
| ***`align-items-center`*** | *Centrar verticalmente* |
| **`align-items-end`** | ***ALINEAR AL FONDO*** |

### `COMPONENTES`

| CLASE | SIGNIFICADO |
|---|---|
| ***`navbar`*** | *Barra de navegación* |
| **`navbar-expand-lg`** | ***EXPANDE EN ≥992px*** |
| *`navbar-dark`* | **Texto claro** |
| ***`navbar-brand`*** | *Logo/nombre* |
| **`navbar-toggler`** | ***BOTÓN HAMBURGUESA*** |
| *`navbar-toggler-icon`* | **Ícono ☰** |
| ***`collapse navbar-collapse`*** | *Contenido colapsable* |
| **`navbar-nav`** | ***LISTA DE NAVEGACIÓN*** |
| *`nav-item`* | **Elemento de navegación** |
| ***`nav-link`*** | *Enlace de navegación* |
| **`card`** | ***TARJETA*** |
| *`card-header`* | **Cabecera de tarjeta** |
| ***`card-body`*** | *Cuerpo de tarjeta* |
| **`card-footer`** | ***PIE DE TARJETA*** |
| *`shadow`* | **Sombra** |
| ***`table`*** | *Tabla Bootstrap* |
| **`table-bordered`** | ***BORDES EN CELDAS*** |
| *`table-striped`* | **Filas alternas** |
| ***`table-hover`*** | *Resaltado al pasar ratón* |
| **`table-dark`** | ***FONDO OSCURO*** |
| *`table-responsive`* | **Scroll horizontal en móvil** |
| ***`alert`*** | *Mensaje/alerta* |
| **`alert-success`** | ***ALERTA VERDE*** |
| *`alert-danger`* | **Alerta roja** |
| ***`alert-dismissible`*** | *Alerta cerrable* |
| **`fade show`** | ***ANIMACIÓN*** |
| *`btn-close`* | **Botón X** |
| ***`badge`*** | *Insignia/etiqueta* |
| **`img-thumbnail`** | ***IMAGEN CON BORDE*** |

### `FORMULARIOS`

| CLASE | SIGNIFICADO |
|---|---|
| ***`form-label`*** | *Etiqueta de campo* |
| **`form-control`** | ***INPUT/TEXTAREA CON ESTILO*** |
| *`form-select`* | **Select con estilo** |
| ***`form-check`*** | *Contenedor checkbox/radio* |
| **`form-check-input`** | ***CHECKBOX/RADIO CON ESTILO*** |
| *`form-check-label`* | **Label de checkbox/radio** |
| ***`form-text`*** | *Texto de ayuda* |

### `BOTONES`

| CLASE | SIGNIFICADO |
|---|---|
| **`btn`** | ***BOTÓN BASE*** |
| *`btn-primary`* | **Azul** |
| ***`btn-secondary`*** | *Gris* |
| **`btn-success`** | ***VERDE*** |
| *`btn-danger`* | **Rojo** |
| ***`btn-warning`*** | *Amarillo* |
| **`btn-dark`** | ***OSCURO*** |
| *`btn-outline-secondary`* | **Gris solo borde** |
| ***`btn-sm`*** | *Pequeño* |
| **`w-100`** | ***ANCHO 100%*** |

### `GRID`

| CLASE | SIGNIFICADO |
|---|---|
| ***`g-3`*** | *Gap/gutter de 1rem* |
| **`pagination`** | ***CONTENEDOR DE PAGINACIÓN*** |
| *`page-item`* | **Elemento de paginación** |
| ***`page-link`*** | *Enlace de paginación* |
| **`active`** | ***PÁGINA ACTUAL*** |
| *`disabled`* | **Enlace deshabilitado** |

---

## `RECURSOS Y DOCUMENTACIÓN 📚`

| RECURSO | URL |
|---|---|
| ***DOCUMENTACIÓN OFICIAL BOOTSTRAP 5*** | *https://getbootstrap.com/docs/5.3* |
| **Ejemplos oficiales** | ***https://getbootstrap.com/docs/5.3/examples*** |
| *Íconos Bootstrap (alternativa a Font Awesome)* | **https://icons.getbootstrap.com** |
| ***FONT AWESOME (BÚSQUEDA DE ÍCONOS)*** | *https://fontawesome.com/icons* |
| **CDN de Bootstrap** | ***https://www.jsdelivr.com/package/npm/bootstrap*** |
| *Repositorio GitHub de Bootstrap* | **https://github.com/twbs/bootstrap** |
| ***PROYECTO UDEMY CI4 (REPOSITORIO DEL CURSO)*** | *https://github.com/saulteconsite/pasos_udemy_ci4* |

---

> [!TIP]
> **Este documento cubre todas las clases de Bootstrap utilizadas en el proyecto de Udemy.** ***PARA CADA CLASE SE INDICA QUÉ HACE Y EN QUÉ ARCHIVO DEL PROYECTO SE ENCUENTRA.*** *Usa este README como referencia rápida mientras trabajas con el código*
