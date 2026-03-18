# `BOOTSTRAP 5 - APUNTES COMPLETOS DEL CURSO UDEMY CODEIGNITER 4 🎨`

![img](https://i.pinimg.com/originals/a1/f8/be/a1f8be54a08a324c83e747a8fa5ed660.gif)

> [!NOTE]
> ***ESTOS APUNTES CUBREN TODO LO RELACIONADO CON BOOTSTRAP 5.3.3 TAL Y COMO SE USA EN EL PROYECTO DEL CURSO DE UDEMY "CODEIGNITER 4 DESDE CERO + INTEGRACIÓN CON BOOTSTRAP 4 O 5". INCLUYE EXPLICACIÓN DETALLADA DE CADA COMPONENTE, CLASE DE UTILIDAD Y CONCEPTO DE BOOTSTRAP CON EJEMPLOS REALES DEL PROYECTO (NAVBAR, TABLAS, FORMULARIOS, CARDS, ALERTAS, GRID, SPACING, COLORES, BOTONES, BADGES, PAGINACIÓN, RESPONSIVE Y MUCHO MÁS). CADA SECCIÓN INDICA EN QUÉ ARCHIVO DEL PROYECTO SE USA***

---

## `¿QUÉ ES BOOTSTRAP? 📦`

> [!NOTE]
> ***BOOTSTRAP ES UN FRAMEWORK CSS DE CÓDIGO ABIERTO CREADO ORIGINALMENTE POR TWITTER EN 2011. PROPORCIONA UNA COLECCIÓN DE ESTILOS CSS Y COMPONENTES JAVASCRIPT PREDISEÑADOS QUE PERMITEN CREAR INTERFACES WEB BONITAS, MODERNAS Y RESPONSIVAS SIN TENER QUE ESCRIBIR CSS DESDE CERO. ES EL FRAMEWORK CSS MÁS POPULAR DEL MUNDO***

### `CONCEPTOS CLAVE`

| CONCEPTO | SIGNIFICADO |
|---|---|
| ***FRAMEWORK CSS*** | ***UNA LIBRERÍA DE ESTILOS YA HECHOS QUE TÚ APLICAS CON CLASES CSS*** |
| ***RESPONSIVO*** | ***LA PÁGINA SE ADAPTA AUTOMÁTICAMENTE AL TAMAÑO DE PANTALLA (MÓVIL, TABLET, ESCRITORIO)*** |
| ***MOBILE FIRST*** | ***BOOTSTRAP DISEÑA PRIMERO PARA MÓVILES Y LUEGO ESCALA HACIA ARRIBA*** |
| ***COMPONENTES*** | ***PIEZAS DE INTERFAZ REUTILIZABLES: BOTONES, TARJETAS, NAVBAR, ALERTAS, ETC.*** |
| ***UTILIDADES*** | ***CLASES CSS PEQUEÑAS QUE HACEN UNA SOLA COSA: `mt-3`, `text-center`, `d-flex`, ETC.*** |
| ***CDN*** | ***CONTENT DELIVERY NETWORK - SERVIDOR EXTERNO QUE ALOJA LOS ARCHIVOS DE BOOTSTRAP*** |

### `BOOTSTRAP NO TIENE NADA QUE VER CON CODEIGNITER`

> [!IMPORTANT]
> ***ESTO ES FUNDAMENTAL ENTENDERLO: CODEIGNITER 4 ES UN FRAMEWORK PHP PARA EL BACKEND (SERVIDOR) Y BOOTSTRAP ES UN FRAMEWORK CSS PARA EL FRONTEND (NAVEGADOR). SON COMPLETAMENTE INDEPENDIENTES. PODRÍAS USAR CI4 SIN BOOTSTRAP (Y ESCRIBIR TU PROPIO CSS), O PODRÍAS USAR BOOTSTRAP SIN CI4 (CON LARAVEL, SYMFONY, O INCLUSO SIN FRAMEWORK PHP). SE USAN JUNTOS POR CONVENIENCIA: CI4 GENERA EL HTML Y BOOTSTRAP LO HACE BONITO***

### `¿CÓMO FUNCIONA?`

***BOOTSTRAP FUNCIONA CON CLASES CSS. TÚ AÑADES CLASES A TUS ELEMENTOS HTML Y BOOTSTRAP LES APLICA ESTILOS AUTOMÁTICAMENTE. NO NECESITAS ESCRIBIR CSS. SOLO NECESITAS SABER QUÉ CLASE USAR:***

```html
<!-- SIN Bootstrap (HTML pelado, feo) -->
<button>Guardar</button>

<!-- CON Bootstrap (bonito, con estilos) -->
<button class="btn btn-primary">Guardar</button>
```

***LA CLASE `btn` LE DA ASPECTO DE BOTÓN Y `btn-primary` LO PINTA DE AZUL. ASÍ DE SIMPLE***

---

## `INSTALACIÓN: CÓMO SE CARGA EN EL PROYECTO 🔌`

> [!NOTE]
> ***EN EL PROYECTO DE UDEMY, BOOTSTRAP SE CARGA DESDE CDN (SERVIDOR EXTERNO). ESTO SIGNIFICA QUE NO HAY QUE DESCARGAR NADA NI INSTALAR NADA CON NPM O COMPOSER. SOLO SE AÑADEN DOS LÍNEAS EN EL HTML***

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

***ANTES DE CERRAR EL `</body>` SE CARGA EL JAVASCRIPT:***

```html
<!-- BOOTSTRAP 5.3.3 - JAVASCRIPT (PARA NAVBAR RESPONSIVE, ALERTAS CERRABLES, ETC.) -->
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js">
</script>
```

### `¿QUÉ ES UN CDN?`

| ASPECTO | DESCRIPCIÓN |
|---|---|
| ***SIGNIFICADO*** | ***CONTENT DELIVERY NETWORK (RED DE DISTRIBUCIÓN DE CONTENIDO)*** |
| ***QUÉ ES*** | ***UN SERVIDOR EXTERNO QUE ALOJA ARCHIVOS PÚBLICOS (CSS, JS, FUENTES, ETC.)*** |
| ***VENTAJA*** | ***MÁS RÁPIDO (SERVIDORES OPTIMIZADOS EN TODO EL MUNDO), NO OCUPA ESPACIO EN TU PROYECTO*** |
| ***DESVENTAJA*** | ***SI NO HAY INTERNET, BOOTSTRAP NO SE CARGA Y LA PÁGINA SE VE FEA*** |
| ***ALTERNATIVA*** | ***DESCARGAR BOOTSTRAP EN TU PROYECTO CON NPM (`npm install bootstrap`) O DESCARGA DIRECTA*** |

### `¿POR QUÉ SE NECESITA TANTO CSS COMO JS?`

***EL CSS DE BOOTSTRAP DA LOS ESTILOS VISUALES (COLORES, BORDES, TAMAÑOS, GRID, ETC.). EL JAVASCRIPT DE BOOTSTRAP AÑADE INTERACTIVIDAD A CIERTOS COMPONENTES:***

| COMPONENTE | ¿NECESITA JS? | POR QUÉ |
|---|---|---|
| ***NAVBAR RESPONSIVE*** | ***SÍ*** | ***EL MENÚ HAMBURGUESA SE ABRE/CIERRA CON JS*** |
| ***ALERTAS DESCARTABLES*** | ***SÍ*** | ***EL BOTÓN X QUE CIERRA LA ALERTA USA JS*** |
| ***TOOLTIPS*** | ***SÍ*** | ***LOS POPUPS INFORMATIVOS NECESITAN JS PARA APARECER*** |
| ***MODALES*** | ***SÍ*** | ***LAS VENTANAS EMERGENTES SE ABREN/CIERRAN CON JS*** |
| ***DROPDOWN*** | ***SÍ*** | ***LOS MENÚS DESPLEGABLES NECESITAN JS*** |
| ***BOTONES*** | ***NO*** | ***SOLO NECESITAN CSS PARA LOS ESTILOS*** |
| ***TABLAS*** | ***NO*** | ***SOLO NECESITAN CSS*** |
| ***CARDS*** | ***NO*** | ***SOLO NECESITAN CSS*** |
| ***GRID*** | ***NO*** | ***SOLO NECESITAN CSS*** |
| ***FORMULARIOS*** | ***NO*** | ***SOLO NECESITAN CSS*** |

> [!TIP]
> ***EL ARCHIVO `bootstrap.bundle.min.js` YA INCLUYE POPPER.JS (NECESARIO PARA TOOLTIPS Y DROPDOWNS). SI USAS `bootstrap.min.js` (SIN "BUNDLE"), TENDRÍAS QUE CARGAR POPPER.JS POR SEPARADO***

---

## `SISTEMA DE GRID (REJILLA) - LA BASE DE BOOTSTRAP 📐`

> [!NOTE]
> ***EL GRID ES EL SISTEMA MÁS IMPORTANTE DE BOOTSTRAP. DIVIDE LA PANTALLA EN 12 COLUMNAS INVISIBLES Y TÚ DECIDES CUÁNTAS COLUMNAS OCUPA CADA ELEMENTO. ES LO QUE HACE QUE LA PÁGINA SEA RESPONSIVA (QUE SE ADAPTE A DISTINTOS TAMAÑOS DE PANTALLA)***

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

***SIEMPRE SE SIGUE ESTA JERARQUÍA. NO PUEDES PONER UN `col` SIN UN `row`:***

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

***BOOTSTRAP DEFINE 6 BREAKPOINTS (PUNTOS DE QUIEBRE). PUEDES ASIGNAR DIFERENTES ANCHOS DE COLUMNA PARA CADA TAMAÑO DE PANTALLA:***

| BREAKPOINT | PREFIJO | ANCHO MÍNIMO | DISPOSITIVO TÍPICO |
|---|---|---|---|
| ***Extra small*** | ***`col-`*** | ***< 576px*** | ***Móviles en vertical*** |
| ***Small*** | ***`col-sm-`*** | ***≥ 576px*** | ***Móviles en horizontal*** |
| ***Medium*** | ***`col-md-`*** | ***≥ 768px*** | ***Tablets*** |
| ***Large*** | ***`col-lg-`*** | ***≥ 992px*** | ***Escritorios*** |
| ***Extra large*** | ***`col-xl-`*** | ***≥ 1200px*** | ***Escritorios grandes*** |
| ***XXL*** | ***`col-xxl-`*** | ***≥ 1400px*** | ***Pantallas muy grandes*** |

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
| ***`row`*** | ***CREA UNA FILA QUE CONTIENE COLUMNAS*** |
| ***`justify-content-center`*** | ***CENTRA LA COLUMNA HORIZONTALMENTE DENTRO DE LA FILA*** |
| ***`col-md-6`*** | ***EN PANTALLAS MEDIANAS (≥768px) O MAYORES: OCUPA 6/12 = 50% DEL ANCHO*** |
| ***EN MÓVILES*** | ***AUTOMÁTICAMENTE OCUPA 12/12 = 100% DEL ANCHO (PORQUE NO HAY `col-` SIN SUFIJO)*** |

***RESULTADO: EL FORMULARIO DE LOGIN OCUPA LA MITAD DE LA PANTALLA EN ESCRITORIO Y TODO EL ANCHO EN MÓVILES***

### `EJEMPLO DEL PROYECTO: CHECKBOXES DE ETIQUETAS`

***ARCHIVO: `app/Views/peliculas/create.php`***

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
| ***`col-md-3`*** | ***EN ESCRITORIO: 3/12 = 25% DEL ANCHO → 4 CHECKBOXES POR FILA*** |
| ***`col-6`*** | ***EN MÓVILES: 6/12 = 50% DEL ANCHO → 2 CHECKBOXES POR FILA*** |

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
| ***`row`*** | ***FILA CONTENEDORA*** |
| ***`g-3`*** | ***GAP/GUTTER DE NIVEL 3 (ESPACIO ENTRE COLUMNAS = 1rem)*** |
| ***`align-items-end`*** | ***ALINEA LOS ELEMENTOS AL FONDO DE LA FILA (LOS BOTONES QUEDAN ALINEADOS CON LOS INPUTS)*** |
| ***`col-md-3`*** | ***CADA CAMPO OCUPA 3/12 = 25% → 4 CAMPOS EN UNA FILA EN ESCRITORIO*** |

### `COMBINACIONES COMUNES DE GRID`

| CLASES | ESCRITORIO | MÓVIL | USO TÍPICO |
|---|---|---|---|
| ***`col-12`*** | ***100%*** | ***100%*** | ***ANCHO COMPLETO SIEMPRE*** |
| ***`col-md-6`*** | ***50%*** | ***100%*** | ***DOS COLUMNAS EN ESCRITORIO, UNA EN MÓVIL*** |
| ***`col-md-4`*** | ***33%*** | ***100%*** | ***TRES COLUMNAS EN ESCRITORIO*** |
| ***`col-md-3`*** | ***25%*** | ***100%*** | ***CUATRO COLUMNAS EN ESCRITORIO*** |
| ***`col-md-3 col-6`*** | ***25%*** | ***50%*** | ***CUATRO EN ESCRITORIO, DOS EN MÓVIL*** |
| ***`col-md-6 col-lg-4`*** | ***33% (LG) / 50% (MD)*** | ***100%*** | ***TRES ESCALAS DIFERENTES*** |
| ***`col-md-8` + `col-md-4`*** | ***66% + 33%*** | ***100% + 100%*** | ***CONTENIDO PRINCIPAL + SIDEBAR*** |

### `GUTTERS (ESPACIADO ENTRE COLUMNAS)`

***LOS GUTTERS SON EL ESPACIO ENTRE COLUMNAS. SE CONTROLAN CON CLASES `g-*`, `gx-*` (HORIZONTAL), `gy-*` (VERTICAL):***

| CLASE | QUÉ HACE |
|---|---|
| ***`g-0`*** | ***SIN ESPACIO ENTRE COLUMNAS*** |
| ***`g-1`*** | ***ESPACIO MÍNIMO (0.25rem)*** |
| ***`g-2`*** | ***ESPACIO PEQUEÑO (0.5rem)*** |
| ***`g-3`*** | ***ESPACIO MEDIO (1rem) ← USADO EN LOS FILTROS DEL PROYECTO*** |
| ***`g-4`*** | ***ESPACIO GRANDE (1.5rem)*** |
| ***`g-5`*** | ***ESPACIO MÁXIMO (3rem)*** |
| ***`gx-3`*** | ***ESPACIO HORIZONTAL DE 1rem (SOLO IZQUIERDA-DERECHA)*** |
| ***`gy-3`*** | ***ESPACIO VERTICAL DE 1rem (SOLO ARRIBA-ABAJO)*** |

---

## `CONTAINER (CONTENEDOR) 📦`

> [!NOTE]
> ***EL CONTAINER ES EL CONTENEDOR PRINCIPAL QUE CENTRA EL CONTENIDO Y LE DA MÁRGENES LATERALES. SIN CONTAINER, TODO EL CONTENIDO IRÍA PEGADO A LOS BORDES DE LA PANTALLA***

### `TIPOS DE CONTAINER`

| CLASE | COMPORTAMIENTO |
|---|---|
| ***`container`*** | ***ANCHO FIJO QUE CAMBIA POR BREAKPOINT (MÁS USADO) ← USADO EN EL PROYECTO*** |
| ***`container-fluid`*** | ***ANCHO 100% SIEMPRE (OCUPA TODA LA PANTALLA)*** |
| ***`container-sm`*** | ***100% HASTA SM, LUEGO ANCHO FIJO*** |
| ***`container-md`*** | ***100% HASTA MD, LUEGO ANCHO FIJO*** |
| ***`container-lg`*** | ***100% HASTA LG, LUEGO ANCHO FIJO*** |
| ***`container-xl`*** | ***100% HASTA XL, LUEGO ANCHO FIJO*** |

### `ANCHOS DEL CONTAINER SEGÚN BREAKPOINT`

| BREAKPOINT | `container` | `container-fluid` |
|---|---|---|
| ***< 576px*** | ***100%*** | ***100%*** |
| ***≥ 576px (sm)*** | ***540px*** | ***100%*** |
| ***≥ 768px (md)*** | ***720px*** | ***100%*** |
| ***≥ 992px (lg)*** | ***960px*** | ***100%*** |
| ***≥ 1200px (xl)*** | ***1140px*** | ***100%*** |
| ***≥ 1400px (xxl)*** | ***1320px*** | ***100%*** |

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
> ***BOOTSTRAP TIENE UN SISTEMA DE CLASES PARA CONTROLAR MÁRGENES (ESPACIO EXTERIOR) Y PADDING (ESPACIO INTERIOR) SIN ESCRIBIR CSS. SE USAN EN PRÁCTICAMENTE TODOS LOS ELEMENTOS DEL PROYECTO***

### `SINTAXIS: {propiedad}{lado}-{tamaño}`

***PRIMERA LETRA = PROPIEDAD:***

| LETRA | PROPIEDAD | SIGNIFICADO |
|---|---|---|
| ***`m`*** | ***margin*** | ***ESPACIO EXTERIOR (FUERA DEL BORDE)*** |
| ***`p`*** | ***padding*** | ***ESPACIO INTERIOR (DENTRO DEL BORDE)*** |

***SEGUNDA LETRA = LADO:***

| LETRA | LADO | CSS EQUIVALENTE |
|---|---|---|
| ***`t`*** | ***top*** | ***margin-top / padding-top*** |
| ***`b`*** | ***bottom*** | ***margin-bottom / padding-bottom*** |
| ***`s`*** | ***start (izquierda)*** | ***margin-left / padding-left*** |
| ***`e`*** | ***end (derecha)*** | ***margin-right / padding-right*** |
| ***`x`*** | ***horizontal*** | ***left + right*** |
| ***`y`*** | ***vertical*** | ***top + bottom*** |
| ***(nada)*** | ***todos los lados*** | ***margin / padding (los 4 lados)*** |

***NÚMERO = TAMAÑO:***

| NÚMERO | TAMAÑO | EQUIVALENTE CSS |
|---|---|---|
| ***`0`*** | ***nada*** | ***0*** |
| ***`1`*** | ***muy pequeño*** | ***0.25rem (4px)*** |
| ***`2`*** | ***pequeño*** | ***0.5rem (8px)*** |
| ***`3`*** | ***medio*** | ***1rem (16px)*** |
| ***`4`*** | ***grande*** | ***1.5rem (24px)*** |
| ***`5`*** | ***muy grande*** | ***3rem (48px)*** |
| ***`auto`*** | ***automático*** | ***auto (centra elementos)*** |

### `EJEMPLOS DEL PROYECTO`

| CLASE | DÓNDE SE USA | QUÉ HACE |
|---|---|---|
| ***`mt-4`*** | ***`container mt-4` en layout/main.php*** | ***MARGEN SUPERIOR DE 1.5rem ENTRE LA NAVBAR Y EL CONTENIDO*** |
| ***`mb-3`*** | ***`<div class="mb-3">` EN TODOS LOS FORMULARIOS*** | ***MARGEN INFERIOR DE 1rem ENTRE CAMPOS DEL FORMULARIO*** |
| ***`mb-4`*** | ***`card card-body bg-light mb-4` EN LOS FILTROS*** | ***MARGEN INFERIOR DE 1.5rem ENTRE LA BARRA DE FILTROS Y LA TABLA*** |
| ***`mt-2`*** | ***`<div class="mt-2">` EN LA PREVIEW DE IMAGEN*** | ***MARGEN SUPERIOR DE 0.5rem ENCIMA DE LA IMAGEN ACTUAL*** |
| ***`mt-3`*** | ***`<div class="d-flex ... mt-3">` EN LA PAGINACIÓN*** | ***MARGEN SUPERIOR DE 1rem ENTRE LA TABLA Y LA PAGINACIÓN*** |
| ***`mt-4`*** | ***`card shadow mt-4` EN LOGIN/REGISTRO*** | ***MARGEN SUPERIOR DE 1.5rem ENTRE LA NAVBAR Y LA CARD*** |
| ***`mb-0`*** | ***`<ul class="mb-0">` EN LISTAS DE ERRORES*** | ***ELIMINA EL MARGEN INFERIOR POR DEFECTO DE LA LISTA*** |
| ***`mb-1`*** | ***`<p class="text-muted mb-1">` EN IMAGEN ACTUAL*** | ***MARGEN INFERIOR MÍNIMO*** |
| ***`mb-2`*** | ***`btn btn-dark w-100 mb-2` EN BOTÓN FILTRAR*** | ***MARGEN INFERIOR DE 0.5rem ENTRE LOS DOS BOTONES*** |
| ***`me-2`*** | ***`btn btn-dark me-2` EN CATEGORÍAS/ETIQUETAS*** | ***MARGEN DERECHO DE 0.5rem ENTRE LOS BOTONES BUSCAR Y LIMPIAR*** |
| ***`me-auto`*** | ***`navbar-nav me-auto` EN LA NAVBAR*** | ***MARGEN DERECHO AUTOMÁTICO → EMPUJA LA PARTE DERECHA DEL MENÚ*** |

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
> ***BOOTSTRAP DEFINE UN SISTEMA DE COLORES SEMÁNTICOS QUE SE USAN EN TODA LA LIBRERÍA. CADA COLOR TIENE UN NOMBRE Y UN SIGNIFICADO***

### `COLORES SEMÁNTICOS DE BOOTSTRAP`

| NOMBRE | COLOR | USO TÍPICO | HEX APROXIMADO |
|---|---|---|---|
| ***`primary`*** | ***AZUL*** | ***ACCIÓN PRINCIPAL (GUARDAR, CREAR, LINKS)*** | ***#0d6efd*** |
| ***`secondary`*** | ***GRIS*** | ***ACCIÓN SECUNDARIA (VOLVER, CANCELAR)*** | ***#6c757d*** |
| ***`success`*** | ***VERDE*** | ***ÉXITO, CONFIRMACIÓN, ROL ADMIN*** | ***#198754*** |
| ***`danger`*** | ***ROJO*** | ***ERROR, PELIGRO, ELIMINAR*** | ***#dc3545*** |
| ***`warning`*** | ***AMARILLO*** | ***ADVERTENCIA, EDITAR*** | ***#ffc107*** |
| ***`info`*** | ***CELESTE*** | ***INFORMACIÓN, ROL USUARIO*** | ***#0dcaf0*** |
| ***`light`*** | ***GRIS CLARO*** | ***FONDO SUAVE, CARDS DE FILTROS*** | ***#f8f9fa*** |
| ***`dark`*** | ***CASI NEGRO*** | ***NAVBAR, CABECERAS DE TABLAS*** | ***#212529*** |
| ***`white`*** | ***BLANCO*** | ***TEXTO SOBRE FONDO OSCURO*** | ***#ffffff*** |

### `CLASES DE FONDO (bg-*)`

| CLASE | QUÉ HACE | DÓNDE SE USA EN EL PROYECTO |
|---|---|---|
| ***`bg-dark`*** | ***FONDO OSCURO*** | ***NAVBAR (`navbar-dark bg-dark`), CARD HEADER DEL LOGIN*** |
| ***`bg-light`*** | ***FONDO GRIS CLARO*** | ***CARD DE FILTROS (`card card-body bg-light`)*** |
| ***`bg-primary`*** | ***FONDO AZUL*** | ***BADGE DE CATEGORÍA EN LISTADO DE PELÍCULAS*** |
| ***`bg-success`*** | ***FONDO VERDE*** | ***BADGE DE ROL ADMIN EN LA NAVBAR*** |
| ***`bg-info`*** | ***FONDO CELESTE*** | ***BADGE DE ROL USUARIO EN LA NAVBAR*** |
| ***`bg-secondary`*** | ***FONDO GRIS*** | ***BADGE DE NOMBRE DE ETIQUETA EN EL LISTADO*** |

### `CLASES DE TEXTO (text-*)`

| CLASE | QUÉ HACE | DÓNDE SE USA EN EL PROYECTO |
|---|---|---|
| ***`text-white`*** | ***TEXTO BLANCO*** | ***CARD HEADER DEL LOGIN/REGISTRO (`bg-dark text-white`)*** |
| ***`text-danger`*** | ***TEXTO ROJO*** | ***ENLACE "SALIR" EN LA NAVBAR*** |
| ***`text-muted`*** | ***TEXTO GRIS SUAVE*** | ***"SIN CATEGORÍA" EN EL LISTADO, TEXTO DE AYUDA EN FORMULARIOS*** |
| ***`text-center`*** | ***TEXTO CENTRADO*** | ***CABECERA DE CARDS, PIE DE CARDS, MENSAJE "NO SE ENCONTRARON..."*** |

### `EJEMPLO DEL PROYECTO: BADGE CON COLORES`

***ARCHIVO: `app/Views/layout/main.php` (NAVBAR)***

```html
<!-- BADGE CON COLOR DINÁMICO SEGÚN EL ROL DEL USUARIO -->
<span class="badge <?= session()->get('usuario_rol') === 'admin' ? 'bg-success' : 'bg-info' ?>">
    <?= esc(strtoupper(session()->get('usuario_rol'))) ?>
</span>
```

***SI ES ADMIN → `bg-success` → BADGE VERDE CON TEXTO "ADMIN"***
***SI ES USUARIO → `bg-info` → BADGE CELESTE CON TEXTO "USUARIO"***

---

## `NAVBAR (BARRA DE NAVEGACIÓN) 🧭`

> [!NOTE]
> ***LA NAVBAR ES EL COMPONENTE MÁS COMPLEJO DE BOOTSTRAP USADO EN EL PROYECTO. ES LA BARRA SUPERIOR QUE APARECE EN TODAS LAS PÁGINAS Y CONTIENE EL LOGO, LOS ENLACES DE NAVEGACIÓN Y LA INFORMACIÓN DEL USUARIO. ES RESPONSIVA: EN ESCRITORIO MUESTRA TODOS LOS ENLACES, EN MÓVIL LOS COLAPSA EN UN MENÚ HAMBURGUESA***

### `ESTRUCTURA COMPLETA DE LA NAVBAR DEL PROYECTO`

***ARCHIVO: `app/Views/layout/main.php`***

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
| ***`navbar`*** | ***COMPONENTE BASE DE BARRA DE NAVEGACIÓN (OBLIGATORIO)*** |
| ***`navbar-expand-lg`*** | ***EN PANTALLAS ≥992px SE EXPANDE MOSTRANDO TODOS LOS ENLACES. EN PANTALLAS MENORES SE COLAPSA EN MENÚ HAMBURGUESA*** |
| ***`navbar-dark`*** | ***ESTILO DE TEXTO CLARO (BLANCO/GRIS) PARA USAR CON FONDOS OSCUROS*** |
| ***`bg-dark`*** | ***FONDO DE COLOR OSCURO (CASI NEGRO)*** |
| ***`container`*** | ***CENTRA EL CONTENIDO DE LA NAVBAR CON MÁRGENES*** |
| ***`navbar-brand`*** | ***EL LOGO O NOMBRE DE LA APLICACIÓN (MÁS GRANDE Y DESTACADO)*** |
| ***`navbar-toggler`*** | ***EL BOTÓN HAMBURGUESA (☰) QUE SOLO APARECE EN PANTALLAS PEQUEÑAS*** |
| ***`navbar-toggler-icon`*** | ***EL ÍCONO DE TRES LÍNEAS (☰) DENTRO DEL BOTÓN HAMBURGUESA*** |
| ***`collapse navbar-collapse`*** | ***CONTENEDOR DE ENLACES QUE SE COLAPSA/EXPANDE EN RESPONSIVE*** |
| ***`navbar-nav`*** | ***LISTA DE ELEMENTOS DE NAVEGACIÓN (REEMPLAZA EL ESTILO DE `<ul>`)*** |
| ***`nav-item`*** | ***UN ELEMENTO INDIVIDUAL DEL MENÚ (`<li>`)*** |
| ***`nav-link`*** | ***UN ENLACE DENTRO DEL MENÚ (`<a>`) CON ESTILOS DE NAVEGACIÓN*** |
| ***`me-auto`*** | ***MARGIN-END AUTOMÁTICO → EMPUJA TODO LO QUE VIENE DESPUÉS HACIA LA DERECHA*** |

### `ATRIBUTOS data-bs-* (JAVASCRIPT DE BOOTSTRAP)`

| ATRIBUTO | VALOR | QUÉ HACE |
|---|---|---|
| ***`data-bs-toggle="collapse"`*** | ***EN EL BOTÓN HAMBURGUESA*** | ***LE DICE A BOOTSTRAP QUE ESTE BOTÓN ABRE/CIERRA UN ELEMENTO COLAPSABLE*** |
| ***`data-bs-target="#navbarNav"`*** | ***EN EL BOTÓN HAMBURGUESA*** | ***INDICA QUÉ ELEMENTO COLAPSAR (EL DIV CON id="navbarNav")*** |
| ***`data-bs-dismiss="alert"`*** | ***EN EL BOTÓN X DE ALERTAS*** | ***LE DICE A BOOTSTRAP QUE ESTE BOTÓN CIERRA LA ALERTA*** |

### `NAVBAR DINÁMICA SEGÚN ESTADO DE SESIÓN`

***LA NAVBAR DEL PROYECTO CAMBIA SU CONTENIDO SEGÚN SI EL USUARIO ESTÁ LOGUEADO O NO:***

| ESTADO | MENÚ IZQUIERDA | MENÚ DERECHA |
|---|---|---|
| ***SIN LOGUEARSE*** | ***VACÍO (NO SE MUESTRAN PELÍCULAS, CATEGORÍAS NI ETIQUETAS)*** | ***"ENTRAR" Y "REGISTRARSE"*** |
| ***LOGUEADO*** | ***PELÍCULAS, CATEGORÍAS, ETIQUETAS*** | ***NOMBRE + BADGE DE ROL + "SALIR"*** |

---

## `CARDS (TARJETAS) 🃏`

> [!NOTE]
> ***LAS CARDS SON CONTENEDORES FLEXIBLES CON BORDES REDONDEADOS QUE SE USAN PARA AGRUPAR CONTENIDO RELACIONADO. EN EL PROYECTO SE USAN PARA LOS FORMULARIOS DE LOGIN/REGISTRO Y PARA LAS BARRAS DE FILTROS***

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
| ***`card`*** | ***COMPONENTE TARJETA BASE (BORDE, BORDES REDONDEADOS, FONDO BLANCO)*** |
| ***`shadow`*** | ***AÑADE UNA SOMBRA SUTIL DEBAJO DE LA TARJETA (EFECTO DE PROFUNDIDAD)*** |
| ***`card-header`*** | ***SECCIÓN SUPERIOR DE LA TARJETA (CON BORDE INFERIOR)*** |
| ***`card-body`*** | ***SECCIÓN CENTRAL DE LA TARJETA (CON PADDING)*** |
| ***`card-footer`*** | ***SECCIÓN INFERIOR DE LA TARJETA (CON BORDE SUPERIOR)*** |

### `USO EN EL PROYECTO: BARRA DE FILTROS`

***ARCHIVO: `app/Views/peliculas/index.php`***

```html
<form action="<?= base_url('/peliculas') ?>" method="GET"
      class="card card-body bg-light mb-4">
    <!-- CAMPOS DE FILTRO -->
</form>
```

| CLASE | QUÉ HACE |
|---|---|
| ***`card card-body`*** | ***TARJETA QUE DIRECTAMENTE ES SU PROPIO CUERPO (SIN HEADER NI FOOTER)*** |
| ***`bg-light`*** | ***FONDO GRIS CLARO PARA DISTINGUIRLO DEL FONDO BLANCO*** |
| ***`mb-4`*** | ***MARGEN INFERIOR DE 1.5rem (ESPACIO ENTRE FILTROS Y TABLA)*** |

---

## `TABLAS 📊`

> [!NOTE]
> ***LAS TABLAS DE BOOTSTRAP SON TABLAS HTML ESTÁNDAR (`<table>`) A LAS QUE SE LES AÑADEN CLASES PARA DARLES UN ASPECTO PROFESIONAL. EN EL PROYECTO SE USAN EN LOS TRES LISTADOS: PELÍCULAS, CATEGORÍAS Y ETIQUETAS***

### `CLASES DE TABLA DISPONIBLES`

| CLASE | QUÉ HACE |
|---|---|
| ***`table`*** | ***CLASE BASE QUE APLICA LOS ESTILOS DE BOOTSTRAP A LA TABLA (OBLIGATORIA)*** |
| ***`table-bordered`*** | ***AÑADE BORDES EN TODAS LAS CELDAS (HORIZONTAL Y VERTICAL)*** |
| ***`table-striped`*** | ***FILAS ALTERNAS CON FONDO GRIS CLARO (EFECTO CEBRA PARA MEJOR LEGIBILIDAD)*** |
| ***`table-hover`*** | ***AL PASAR EL RATÓN SOBRE UNA FILA, SE RESALTA CON UN FONDO GRIS*** |
| ***`table-dark`*** | ***FONDO OSCURO (SE USA EN `<thead>` PARA LA CABECERA)*** |
| ***`table-sm`*** | ***TABLA COMPACTA (MENOS PADDING EN LAS CELDAS)*** |
| ***`table-responsive`*** | ***CONTENEDOR QUE AÑADE SCROLL HORIZONTAL EN PANTALLAS PEQUEÑAS*** |
| ***`table-borderless`*** | ***TABLA SIN BORDES*** |
| ***`table-primary`*** | ***FILA O CELDA CON FONDO AZUL*** |
| ***`table-success`*** | ***FILA O CELDA CON FONDO VERDE*** |
| ***`table-danger`*** | ***FILA O CELDA CON FONDO ROJO*** |

### `USO EN EL PROYECTO: LISTADO DE PELÍCULAS`

***ARCHIVO: `app/Views/peliculas/index.php`***

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
> ***BOOTSTRAP PROPORCIONA ESTILOS PARA TODOS LOS ELEMENTOS DE FORMULARIO: INPUTS, TEXTAREAS, SELECTS, CHECKBOXES, RADIO BUTTONS Y BOTONES. EN EL PROYECTO SE USAN EN LOS FORMULARIOS DE CRUD (CREAR/EDITAR) Y EN LOGIN/REGISTRO***

### `CLASES DE FORMULARIO`

| CLASE | ELEMENTO | QUÉ HACE |
|---|---|---|
| ***`form-label`*** | ***`<label>`*** | ***ESTILO PARA LA ETIQUETA DEL CAMPO (NEGRITA LIGERA, MARGEN INFERIOR)*** |
| ***`form-control`*** | ***`<input>`, `<textarea>`*** | ***ESTILO PRINCIPAL: BORDE, PADDING, ANCHO 100%, BORDES REDONDEADOS, FOCO AZUL*** |
| ***`form-select`*** | ***`<select>`*** | ***ESTILO PARA DESPLEGABLES (SIMILAR A form-control PERO CON FLECHA)*** |
| ***`form-check`*** | ***`<div>` CONTENEDOR*** | ***CONTENEDOR PARA CHECKBOX O RADIO BUTTON*** |
| ***`form-check-input`*** | ***`<input type="checkbox/radio">`*** | ***ESTILO PARA EL CHECKBOX O RADIO EN SÍ*** |
| ***`form-check-label`*** | ***`<label>`*** | ***ESTILO PARA LA ETIQUETA DEL CHECKBOX/RADIO*** |
| ***`form-text`*** | ***`<div>` O `<small>`*** | ***TEXTO DE AYUDA DEBAJO DE UN CAMPO (GRIS, PEQUEÑO)*** |
| ***`form-floating`*** | ***`<div>` CONTENEDOR*** | ***LABEL FLOTANTE QUE SE MUEVE AL ESCRIBIR (NO USADO EN EL PROYECTO)*** |

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

***TODOS LOS CAMPOS DEL PROYECTO SIGUEN EL MISMO PATRÓN:***

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
> ***LOS BOTONES DE BOOTSTRAP SE CREAN CON LA CLASE BASE `btn` COMBINADA CON UNA CLASE DE COLOR. SE PUEDEN APLICAR A `<button>`, `<a>` O `<input>`. EN EL PROYECTO SE USAN BOTONES DE TODOS LOS COLORES Y TAMAÑOS***

### `TODOS LOS TIPOS DE BOTÓN`

| CLASE | COLOR | USO EN EL PROYECTO |
|---|---|---|
| ***`btn btn-primary`*** | ***AZUL (RELLENO)*** | ***GUARDAR, CREAR NUEVO, ENTRAR (LOGIN)*** |
| ***`btn btn-secondary`*** | ***GRIS (RELLENO)*** | ***VOLVER AL LISTADO*** |
| ***`btn btn-success`*** | ***VERDE (RELLENO)*** | ***BOTÓN DE REGISTRARSE*** |
| ***`btn btn-danger`*** | ***ROJO (RELLENO)*** | ***ELIMINAR*** |
| ***`btn btn-warning`*** | ***AMARILLO (RELLENO)*** | ***EDITAR*** |
| ***`btn btn-info`*** | ***CELESTE (RELLENO)*** | ***INFORMACIÓN (NO USADO EN EL PROYECTO)*** |
| ***`btn btn-dark`*** | ***OSCURO (RELLENO)*** | ***BOTÓN FILTRAR EN LA BARRA DE FILTROS*** |
| ***`btn btn-light`*** | ***GRIS CLARO (RELLENO)*** | ***(NO USADO EN EL PROYECTO)*** |
| ***`btn btn-outline-primary`*** | ***AZUL (SOLO BORDE)*** | ***(NO USADO EN EL PROYECTO)*** |
| ***`btn btn-outline-secondary`*** | ***GRIS (SOLO BORDE)*** | ***BOTÓN LIMPIAR FILTROS*** |

### `TAMAÑOS DE BOTÓN`

| CLASE | TAMAÑO | USO EN EL PROYECTO |
|---|---|---|
| ***`btn btn-lg`*** | ***GRANDE*** | ***(NO USADO)*** |
| ***`btn`*** | ***NORMAL*** | ***GUARDAR, VOLVER, FILTRAR*** |
| ***`btn btn-sm`*** | ***PEQUEÑO*** | ***EDITAR Y ELIMINAR EN LAS TABLAS*** |

### `BOTONES ANCHOS`

| CLASE | QUÉ HACE | USO EN EL PROYECTO |
|---|---|---|
| ***`w-100`*** | ***WIDTH 100% (OCUPA TODO EL ANCHO)*** | ***BOTÓN FILTRAR Y LIMPIAR EN FILTROS DE PELÍCULAS*** |
| ***`d-grid`*** | ***DISPLAY GRID (BOTÓN OCUPA TODO EL ANCHO DEL CONTENEDOR)*** | ***BOTÓN "ENTRAR" EN LOGIN Y "REGISTRARSE"*** |

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
> ***LAS ALERTAS SON CAJAS DE MENSAJE CON COLORES SEMÁNTICOS. EN EL PROYECTO SE USAN PARA MOSTRAR MENSAJES DE ÉXITO (VERDE) Y ERROR (ROJO) DESPUÉS DE CADA ACCIÓN CRUD O INTENTO DE LOGIN***

### `TIPOS DE ALERTA`

| CLASE | COLOR | USO EN EL PROYECTO |
|---|---|---|
| ***`alert alert-success`*** | ***VERDE*** | ***"PELÍCULA CREADA CORRECTAMENTE", "BIENVENIDO, USUARIO!"*** |
| ***`alert alert-danger`*** | ***ROJO*** | ***"CREDENCIALES INCORRECTAS", "DEBES INICIAR SESIÓN", ERRORES DE VALIDACIÓN*** |
| ***`alert alert-warning`*** | ***AMARILLO*** | ***(DISPONIBLE PERO NO USADO EN EL PROYECTO)*** |
| ***`alert alert-info`*** | ***CELESTE*** | ***(DISPONIBLE PERO NO USADO EN EL PROYECTO)*** |
| ***`alert alert-primary`*** | ***AZUL*** | ***(DISPONIBLE PERO NO USADO EN EL PROYECTO)*** |

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
| ***`alert`*** | ***CLASE BASE DE ALERTA (PADDING, BORDES, MARGEN)*** |
| ***`alert-success`*** | ***COLOR VERDE (FONDO Y BORDE)*** |
| ***`alert-danger`*** | ***COLOR ROJO (FONDO Y BORDE)*** |
| ***`alert-dismissible`*** | ***PERMITE CERRAR LA ALERTA (AÑADE ESPACIO PARA EL BOTÓN X)*** |
| ***`fade show`*** | ***ANIMACIÓN DE APARICIÓN Y DESAPARICIÓN SUAVE*** |
| ***`btn-close`*** | ***BOTÓN X PARA CERRAR (REQUIERE `data-bs-dismiss="alert"`)*** |

### `ALERTAS CON LISTA DE ERRORES DE VALIDACIÓN`

***ARCHIVO: `app/Views/peliculas/create.php` (Y TODOS LOS FORMULARIOS)***

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

***`mb-0` EN LA `<ul>` ELIMINA EL MARGEN INFERIOR POR DEFECTO DE LA LISTA, PARA QUE NO QUEDE ESPACIO EXTRA DENTRO DE LA ALERTA***

---

## `BADGES (INSIGNIAS/ETIQUETAS) 🏅`

> [!NOTE]
> ***LOS BADGES SON PEQUEÑAS ETIQUETAS REDONDEADAS CON FONDO DE COLOR. SE USAN PARA MOSTRAR INFORMACIÓN BREVE Y CATEGORIZADA COMO ROLES, ESTADOS O CATEGORÍAS***

### `USO EN EL PROYECTO`

| DÓNDE | CLASE | QUÉ MUESTRA |
|---|---|---|
| ***NAVBAR (ROL ADMIN)*** | ***`badge bg-success`*** | ***BADGE VERDE CON TEXTO "ADMIN"*** |
| ***NAVBAR (ROL USUARIO)*** | ***`badge bg-info`*** | ***BADGE CELESTE CON TEXTO "USUARIO"*** |
| ***LISTADO PELÍCULAS (CATEGORÍA)*** | ***`badge bg-primary`*** | ***BADGE AZUL CON EL NOMBRE DE LA CATEGORÍA*** |
| ***LISTADO ETIQUETAS (NOMBRE)*** | ***`badge bg-secondary`*** | ***BADGE GRIS CON EL NOMBRE DE LA ETIQUETA*** |

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
| ***`badge bg-primary`*** | ***AZUL*** |
| ***`badge bg-secondary`*** | ***GRIS*** |
| ***`badge bg-success`*** | ***VERDE*** |
| ***`badge bg-danger`*** | ***ROJO*** |
| ***`badge bg-warning text-dark`*** | ***AMARILLO (CON TEXTO OSCURO PARA QUE SE LEA)*** |
| ***`badge bg-info`*** | ***CELESTE*** |
| ***`badge bg-light text-dark`*** | ***GRIS CLARO (CON TEXTO OSCURO)*** |
| ***`badge bg-dark`*** | ***OSCURO*** |

---

## `UTILIDADES DE DISPLAY Y FLEXBOX 📐`

> [!NOTE]
> ***BOOTSTRAP PROPORCIONA CLASES DE UTILIDAD PARA CONTROLAR EL DISPLAY CSS Y FLEXBOX SIN ESCRIBIR CSS. ESTAS CLASES SE USAN MUCHO EN EL PROYECTO PARA ALINEAR ELEMENTOS, CENTRAR CONTENIDO Y DISTRIBUIR ESPACIO***

### `CLASES DE DISPLAY`

| CLASE | CSS EQUIVALENTE | USO EN EL PROYECTO |
|---|---|---|
| ***`d-none`*** | ***`display: none`*** | ***OCULTAR UN ELEMENTO*** |
| ***`d-block`*** | ***`display: block`*** | ***MOSTRAR COMO BLOQUE*** |
| ***`d-inline`*** | ***`display: inline`*** | ***FORMULARIO DE ELIMINAR EN LÍNEA CON BOTÓN DE EDITAR*** |
| ***`d-flex`*** | ***`display: flex`*** | ***CONTENEDOR FLEX PARA ALINEAR ELEMENTOS*** |
| ***`d-grid`*** | ***`display: grid`*** | ***BOTÓN ANCHO EN LOGIN/REGISTRO*** |
| ***`d-none d-md-block`*** | ***OCULTO EN MÓVIL, VISIBLE EN TABLET+*** | ***RESPONSIVE: OCULTAR/MOSTRAR*** |

### `CLASES DE FLEXBOX`

| CLASE | QUÉ HACE | USO EN EL PROYECTO |
|---|---|---|
| ***`d-flex`*** | ***ACTIVA FLEXBOX EN EL CONTENEDOR*** | ***CABECERA DE LISTADOS*** |
| ***`justify-content-between`*** | ***HIJOS SEPARADOS A LOS EXTREMOS (IZQUIERDA Y DERECHA)*** | ***TÍTULO + BOTÓN "NUEVA PELÍCULA"*** |
| ***`justify-content-center`*** | ***HIJOS CENTRADOS HORIZONTALMENTE*** | ***PAGINACIÓN, FORMULARIO LOGIN*** |
| ***`align-items-center`*** | ***HIJOS CENTRADOS VERTICALMENTE*** | ***CABECERA DE LISTADOS (TÍTULO + BOTÓN ALINEADOS)*** |
| ***`align-items-end`*** | ***HIJOS ALINEADOS AL FONDO*** | ***BARRA DE FILTROS (LABELS CON DIFERENTE ALTURA)*** |

### `EJEMPLO DEL PROYECTO: CABECERA DE LISTADOS`

***ARCHIVO: `app/Views/peliculas/index.php`***

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

***ARCHIVO: `app/Views/peliculas/index.php`***

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

***SIN `d-inline`, EL `<form>` OCUPARÍA TODA LA FILA Y EL BOTÓN ROJO IRÍA DEBAJO DEL AMARILLO. CON `d-inline`, QUEDAN UNO AL LADO DEL OTRO***

---

## `IMÁGENES 🖼️`

> [!NOTE]
> ***BOOTSTRAP PROPORCIONA CLASES PARA ESTILIZAR IMÁGENES. EN EL PROYECTO SE USA `img-thumbnail` PARA LAS IMÁGENES DE LAS PELÍCULAS***

### `CLASES DE IMAGEN`

| CLASE | QUÉ HACE | USO EN EL PROYECTO |
|---|---|---|
| ***`img-fluid`*** | ***HACE LA IMAGEN RESPONSIVA (max-width: 100%, height: auto)*** | ***(NO USADO)*** |
| ***`img-thumbnail`*** | ***AÑADE BORDE, BORDES REDONDEADOS Y PADDING A LA IMAGEN*** | ***IMÁGENES DE PELÍCULAS EN LISTADO Y EDICIÓN*** |
| ***`rounded`*** | ***BORDES REDONDEADOS*** | ***(NO USADO)*** |
| ***`rounded-circle`*** | ***IMAGEN CIRCULAR*** | ***(NO USADO, PERO ÚTIL PARA AVATARES)*** |

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
| ***`shadow-none`*** | ***SIN SOMBRA*** | ***(NO USADO)*** |
| ***`shadow-sm`*** | ***SOMBRA PEQUEÑA*** | ***(NO USADO)*** |
| ***`shadow`*** | ***SOMBRA NORMAL*** | ***CARDS DE LOGIN Y REGISTRO*** |
| ***`shadow-lg`*** | ***SOMBRA GRANDE*** | ***(NO USADO)*** |

### `BORDES`

| CLASE | QUÉ HACE |
|---|---|
| ***`border`*** | ***BORDE EN LOS 4 LADOS*** |
| ***`border-0`*** | ***SIN BORDES*** |
| ***`border-top`*** | ***SOLO BORDE SUPERIOR*** |
| ***`border-primary`*** | ***BORDE AZUL*** |
| ***`rounded`*** | ***BORDES REDONDEADOS*** |
| ***`rounded-0`*** | ***SIN REDONDEAR (ESQUINAS CUADRADAS)*** |
| ***`rounded-circle`*** | ***COMPLETAMENTE CIRCULAR*** |
| ***`rounded-pill`*** | ***FORMA DE PÍLDORA (BORDES MUY REDONDEADOS)*** |

---

## `UTILIDADES DE TAMAÑO (WIDTH Y HEIGHT) 📐`

| CLASE | QUÉ HACE | USO EN EL PROYECTO |
|---|---|---|
| ***`w-25`*** | ***width: 25%*** | ***(NO USADO)*** |
| ***`w-50`*** | ***width: 50%*** | ***(NO USADO)*** |
| ***`w-75`*** | ***width: 75%*** | ***(NO USADO)*** |
| ***`w-100`*** | ***width: 100%*** | ***BOTONES FILTRAR Y LIMPIAR (ANCHO COMPLETO)*** |
| ***`w-auto`*** | ***width: auto*** | ***(NO USADO)*** |
| ***`h-100`*** | ***height: 100%*** | ***(NO USADO)*** |
| ***`mw-100`*** | ***max-width: 100%*** | ***(NO USADO)*** |
| ***`vh-100`*** | ***height: 100vh (TODA LA VENTANA)*** | ***(NO USADO)*** |

---

## `TIPOGRAFÍA ✏️`

> [!NOTE]
> ***BOOTSTRAP MODIFICA LA TIPOGRAFÍA BASE DE LA PÁGINA Y PROPORCIONA CLASES PARA CONTROLAR TAMAÑO, PESO Y ESTILO DEL TEXTO***

### `CLASES DE TIPOGRAFÍA`

| CLASE | QUÉ HACE | USO EN EL PROYECTO |
|---|---|---|
| ***`fw-bold`*** | ***FONT-WEIGHT BOLD (NEGRITA)*** | ***LABELS DE LOS FILTROS*** |
| ***`fw-light`*** | ***FONT-WEIGHT LIGHT*** | ***(NO USADO)*** |
| ***`fst-italic`*** | ***FONT-STYLE ITALIC (CURSIVA)*** | ***(NO USADO)*** |
| ***`text-decoration-none`*** | ***QUITA EL SUBRAYADO DE LOS ENLACES*** | ***(NO USADO)*** |
| ***`text-uppercase`*** | ***TEXTO EN MAYÚSCULAS*** | ***(NO USADO, SE HACE CON PHP strtoupper())*** |
| ***`text-lowercase`*** | ***TEXTO EN MINÚSCULAS*** | ***(NO USADO)*** |
| ***`text-capitalize`*** | ***PRIMERA LETRA MAYÚSCULA*** | ***(NO USADO)*** |
| ***`fs-1` a `fs-6`*** | ***TAMAÑO DE FUENTE (1=MÁS GRANDE, 6=MÁS PEQUEÑO)*** | ***(NO USADO, SE USAN `<h1>` A `<h6>`)*** |
| ***`lead`*** | ***PÁRRAFO MÁS GRANDE Y DESTACADO*** | ***(NO USADO)*** |

### `EJEMPLO DEL PROYECTO: LABELS EN NEGRITA`

***ARCHIVO: `app/Views/peliculas/index.php`***

```html
<label for="busqueda" class="form-label fw-bold">
    <i class="fa fa-search"></i> Buscar
</label>
```

***`fw-bold` HACE QUE EL TEXTO "BUSCAR" APAREZCA EN NEGRITA***

---

## `PAGINACIÓN 📄`

> [!NOTE]
> ***CODEIGNITER 4 GENERA AUTOMÁTICAMENTE LOS ENLACES DE PAGINACIÓN CON ESTILOS DE BOOTSTRAP USANDO LA PLANTILLA `default_full`. LOS ENLACES APARECEN COMO BOTONES NUMERADOS (1, 2, 3, ANTERIOR, SIGUIENTE)***

### `CÓDIGO EN LA VISTA`

***ARCHIVO: `app/Views/peliculas/index.php` (Y categorias/index.php, etiquetas/index.php)***

```html
<?php if (isset($pager)): ?>
    <div class="d-flex justify-content-center mt-3">
        <?= $pager->links('default', 'default_full') ?>
    </div>
<?php endif; ?>
```

| PARTE | QUÉ HACE |
|---|---|
| ***`$pager->links()`*** | ***GENERA EL HTML DE LOS ENLACES DE PAGINACIÓN*** |
| ***`'default'`*** | ***GRUPO POR DEFECTO (EL MODELO GENERA UNO AUTOMÁTICAMENTE)*** |
| ***`'default_full'`*** | ***PLANTILLA DE BOOTSTRAP CON ANTERIOR, SIGUIENTE Y NÚMEROS*** |
| ***`d-flex justify-content-center`*** | ***CENTRA LOS ENLACES HORIZONTALMENTE*** |
| ***`mt-3`*** | ***MARGEN SUPERIOR DE 1rem ENTRE LA TABLA Y LA PAGINACIÓN*** |

***BOOTSTRAP GENERA ALGO COMO ESTO:***

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
| ***`pagination`*** | ***ESTILO BASE DE LA LISTA DE PAGINACIÓN*** |
| ***`page-item`*** | ***UN ELEMENTO DE LA PAGINACIÓN*** |
| ***`page-link`*** | ***UN ENLACE DE LA PAGINACIÓN*** |
| ***`active`*** | ***PÁGINA ACTUAL (RESALTADA EN AZUL)*** |
| ***`disabled`*** | ***ENLACE DESHABILITADO (GRIS, NO CLICKEABLE)*** |

---

## `FONT AWESOME (ÍCONOS) - NO ES BOOTSTRAP ⭐`

> [!IMPORTANT]
> ***FONT AWESOME NO ES PARTE DE BOOTSTRAP. SON DOS LIBRERÍAS COMPLETAMENTE INDEPENDIENTES QUE SE COMPLEMENTAN. BOOTSTRAP DA LOS ESTILOS Y FONT AWESOME DA LOS ÍCONOS***

### `CÓMO SE CARGA`

```html
<link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css"
      rel="stylesheet">
```

### `CÓMO SE USA`

***SE USA UN TAG `<i>` (ITALIC) CON CLASES DE FONT AWESOME:***

```html
<i class="fa fa-film"></i>        <!-- ÍCONO DE PELÍCULA -->
```

### `TODOS LOS ÍCONOS USADOS EN EL PROYECTO`

| CLASE | ÍCONO | DÓNDE SE USA |
|---|---|---|
| ***`fa fa-film`*** | ***PELÍCULA*** | ***ENLACE "PELÍCULAS" EN LA NAVBAR*** |
| ***`fa fa-tags`*** | ***ETIQUETAS*** | ***ENLACE "CATEGORÍAS" EN LA NAVBAR*** |
| ***`fa fa-bookmark`*** | ***MARCADOR*** | ***ENLACE "ETIQUETAS" EN LA NAVBAR*** |
| ***`fa fa-user`*** | ***USUARIO*** | ***NOMBRE DEL USUARIO EN LA NAVBAR*** |
| ***`fa fa-user-lock`*** | ***CANDADO*** | ***TÍTULO DEL FORMULARIO DE LOGIN*** |
| ***`fa fa-user-plus`*** | ***USUARIO+*** | ***TÍTULO DEL FORMULARIO DE REGISTRO*** |
| ***`fa fa-sign-in-alt`*** | ***ENTRAR*** | ***BOTÓN "ENTRAR" EN NAVBAR Y LOGIN*** |
| ***`fa fa-sign-out-alt`*** | ***SALIR*** | ***BOTÓN "SALIR" EN LA NAVBAR*** |
| ***`fa fa-plus`*** | ***MÁS*** | ***BOTONES "NUEVA PELÍCULA/CATEGORÍA/ETIQUETA"*** |
| ***`fa fa-edit`*** | ***LÁPIZ*** | ***BOTONES DE EDITAR EN LAS TABLAS*** |
| ***`fa fa-trash`*** | ***PAPELERA*** | ***BOTONES DE ELIMINAR EN LAS TABLAS*** |
| ***`fa fa-save`*** | ***DISQUETE*** | ***BOTONES "GUARDAR" Y "ACTUALIZAR"*** |
| ***`fa fa-arrow-left`*** | ***FLECHA*** | ***BOTONES "VOLVER"*** |
| ***`fa fa-search`*** | ***LUPA*** | ***LABEL "BUSCAR" EN LOS FILTROS*** |
| ***`fa fa-filter`*** | ***EMBUDO*** | ***BOTÓN "FILTRAR"*** |
| ***`fa fa-times`*** | ***X*** | ***BOTÓN "LIMPIAR" FILTROS*** |
| ***`fa fa-folder`*** | ***CARPETA*** | ***LABEL "CATEGORÍA" EN LOS FILTROS*** |
| ***`fa fa-tag`*** | ***ETIQUETA*** | ***LABEL "ETIQUETA" EN LOS FILTROS*** |
| ***`fa fa-image`*** | ***IMAGEN*** | ***PLACEHOLDER CUANDO NO HAY IMAGEN*** |

---

## `COMPONENTES BOOTSTRAP ADICIONALES (NO USADOS EN EL PROYECTO PERO ÚTILES) 📚`

> [!TIP]
> ***ESTOS COMPONENTES NO SE USAN EN EL PROYECTO DE UDEMY PERO SON MUY COMUNES EN DESARROLLO WEB CON BOOTSTRAP. ES BUENO CONOCERLOS PARA FUTUROS PROYECTOS***

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

***EJEMPLO DE USO: PODRÍAS USAR UN MODAL PARA CONFIRMAR LA ELIMINACIÓN EN VEZ DE `confirm()` DE JAVASCRIPT***

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

***MUESTRA LA RUTA DE NAVEGACIÓN: `Inicio > Películas > Crear`***

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
> ***REFERENCIA RÁPIDA DE ABSOLUTAMENTE TODAS LAS CLASES DE BOOTSTRAP QUE APARECEN EN EL PROYECTO DE UDEMY, ORGANIZADAS POR CATEGORÍA***

### `LAYOUT`

| CLASE | SIGNIFICADO |
|---|---|
| ***`container`*** | ***CONTENEDOR CENTRADO CON MÁRGENES*** |
| ***`row`*** | ***FILA DE COLUMNAS*** |
| ***`col-6`*** | ***COLUMNA DE 50% EN TODOS LOS TAMAÑOS*** |
| ***`col-md-3`*** | ***COLUMNA DE 25% EN PANTALLAS MEDIANAS+*** |
| ***`col-md-6`*** | ***COLUMNA DE 50% EN PANTALLAS MEDIANAS+*** |
| ***`col-md-8`*** | ***COLUMNA DE 66% EN PANTALLAS MEDIANAS+*** |
| ***`col-md-4`*** | ***COLUMNA DE 33% EN PANTALLAS MEDIANAS+*** |

### `SPACING`

| CLASE | SIGNIFICADO |
|---|---|
| ***`mt-2`*** | ***MARGIN TOP 0.5rem*** |
| ***`mt-3`*** | ***MARGIN TOP 1rem*** |
| ***`mt-4`*** | ***MARGIN TOP 1.5rem*** |
| ***`mb-0`*** | ***MARGIN BOTTOM 0*** |
| ***`mb-1`*** | ***MARGIN BOTTOM 0.25rem*** |
| ***`mb-2`*** | ***MARGIN BOTTOM 0.5rem*** |
| ***`mb-3`*** | ***MARGIN BOTTOM 1rem*** |
| ***`mb-4`*** | ***MARGIN BOTTOM 1.5rem*** |
| ***`me-2`*** | ***MARGIN END 0.5rem*** |
| ***`me-auto`*** | ***MARGIN END AUTO*** |

### `TEXTO`

| CLASE | SIGNIFICADO |
|---|---|
| ***`text-white`*** | ***COLOR BLANCO*** |
| ***`text-danger`*** | ***COLOR ROJO*** |
| ***`text-muted`*** | ***COLOR GRIS SUAVE*** |
| ***`text-center`*** | ***CENTRADO*** |
| ***`fw-bold`*** | ***NEGRITA*** |

### `FONDO`

| CLASE | SIGNIFICADO |
|---|---|
| ***`bg-dark`*** | ***FONDO OSCURO*** |
| ***`bg-light`*** | ***FONDO GRIS CLARO*** |
| ***`bg-primary`*** | ***FONDO AZUL*** |
| ***`bg-success`*** | ***FONDO VERDE*** |
| ***`bg-info`*** | ***FONDO CELESTE*** |
| ***`bg-secondary`*** | ***FONDO GRIS*** |

### `DISPLAY Y FLEXBOX`

| CLASE | SIGNIFICADO |
|---|---|
| ***`d-flex`*** | ***DISPLAY FLEX*** |
| ***`d-inline`*** | ***DISPLAY INLINE*** |
| ***`d-grid`*** | ***DISPLAY GRID*** |
| ***`justify-content-between`*** | ***SEPARAR A LOS EXTREMOS*** |
| ***`justify-content-center`*** | ***CENTRAR HORIZONTALMENTE*** |
| ***`align-items-center`*** | ***CENTRAR VERTICALMENTE*** |
| ***`align-items-end`*** | ***ALINEAR AL FONDO*** |

### `COMPONENTES`

| CLASE | SIGNIFICADO |
|---|---|
| ***`navbar`*** | ***BARRA DE NAVEGACIÓN*** |
| ***`navbar-expand-lg`*** | ***EXPANDE EN ≥992px*** |
| ***`navbar-dark`*** | ***TEXTO CLARO*** |
| ***`navbar-brand`*** | ***LOGO/NOMBRE*** |
| ***`navbar-toggler`*** | ***BOTÓN HAMBURGUESA*** |
| ***`navbar-toggler-icon`*** | ***ÍCONO ☰*** |
| ***`collapse navbar-collapse`*** | ***CONTENIDO COLAPSABLE*** |
| ***`navbar-nav`*** | ***LISTA DE NAVEGACIÓN*** |
| ***`nav-item`*** | ***ELEMENTO DE NAVEGACIÓN*** |
| ***`nav-link`*** | ***ENLACE DE NAVEGACIÓN*** |
| ***`card`*** | ***TARJETA*** |
| ***`card-header`*** | ***CABECERA DE TARJETA*** |
| ***`card-body`*** | ***CUERPO DE TARJETA*** |
| ***`card-footer`*** | ***PIE DE TARJETA*** |
| ***`shadow`*** | ***SOMBRA*** |
| ***`table`*** | ***TABLA BOOTSTRAP*** |
| ***`table-bordered`*** | ***BORDES EN CELDAS*** |
| ***`table-striped`*** | ***FILAS ALTERNAS*** |
| ***`table-hover`*** | ***RESALTADO AL PASAR RATÓN*** |
| ***`table-dark`*** | ***FONDO OSCURO*** |
| ***`table-responsive`*** | ***SCROLL HORIZONTAL EN MÓVIL*** |
| ***`alert`*** | ***MENSAJE/ALERTA*** |
| ***`alert-success`*** | ***ALERTA VERDE*** |
| ***`alert-danger`*** | ***ALERTA ROJA*** |
| ***`alert-dismissible`*** | ***ALERTA CERRABLE*** |
| ***`fade show`*** | ***ANIMACIÓN*** |
| ***`btn-close`*** | ***BOTÓN X*** |
| ***`badge`*** | ***INSIGNIA/ETIQUETA*** |
| ***`img-thumbnail`*** | ***IMAGEN CON BORDE*** |

### `FORMULARIOS`

| CLASE | SIGNIFICADO |
|---|---|
| ***`form-label`*** | ***ETIQUETA DE CAMPO*** |
| ***`form-control`*** | ***INPUT/TEXTAREA CON ESTILO*** |
| ***`form-select`*** | ***SELECT CON ESTILO*** |
| ***`form-check`*** | ***CONTENEDOR CHECKBOX/RADIO*** |
| ***`form-check-input`*** | ***CHECKBOX/RADIO CON ESTILO*** |
| ***`form-check-label`*** | ***LABEL DE CHECKBOX/RADIO*** |
| ***`form-text`*** | ***TEXTO DE AYUDA*** |

### `BOTONES`

| CLASE | SIGNIFICADO |
|---|---|
| ***`btn`*** | ***BOTÓN BASE*** |
| ***`btn-primary`*** | ***AZUL*** |
| ***`btn-secondary`*** | ***GRIS*** |
| ***`btn-success`*** | ***VERDE*** |
| ***`btn-danger`*** | ***ROJO*** |
| ***`btn-warning`*** | ***AMARILLO*** |
| ***`btn-dark`*** | ***OSCURO*** |
| ***`btn-outline-secondary`*** | ***GRIS SOLO BORDE*** |
| ***`btn-sm`*** | ***PEQUEÑO*** |
| ***`w-100`*** | ***ANCHO 100%*** |

### `GRID`

| CLASE | SIGNIFICADO |
|---|---|
| ***`g-3`*** | ***GAP/GUTTER DE 1rem*** |
| ***`pagination`*** | ***CONTENEDOR DE PAGINACIÓN*** |
| ***`page-item`*** | ***ELEMENTO DE PAGINACIÓN*** |
| ***`page-link`*** | ***ENLACE DE PAGINACIÓN*** |
| ***`active`*** | ***PÁGINA ACTUAL*** |
| ***`disabled`*** | ***ENLACE DESHABILITADO*** |

---

## `RECURSOS Y DOCUMENTACIÓN 📚`

| RECURSO | URL |
|---|---|
| ***DOCUMENTACIÓN OFICIAL BOOTSTRAP 5*** | ***https://getbootstrap.com/docs/5.3*** |
| ***EJEMPLOS OFICIALES*** | ***https://getbootstrap.com/docs/5.3/examples*** |
| ***ÍCONOS BOOTSTRAP (ALTERNATIVA A FONT AWESOME)*** | ***https://icons.getbootstrap.com*** |
| ***FONT AWESOME (BÚSQUEDA DE ÍCONOS)*** | ***https://fontawesome.com/icons*** |
| ***CDN DE BOOTSTRAP*** | ***https://www.jsdelivr.com/package/npm/bootstrap*** |
| ***REPOSITORIO GITHUB DE BOOTSTRAP*** | ***https://github.com/twbs/bootstrap*** |
| ***PROYECTO UDEMY CI4 (REPOSITORIO DEL CURSO)*** | ***https://github.com/saulteconsite/pasos_udemy_ci4*** |

---

> [!TIP]
> ***ESTE DOCUMENTO CUBRE TODAS LAS CLASES DE BOOTSTRAP UTILIZADAS EN EL PROYECTO DE UDEMY. PARA CADA CLASE SE INDICA QUÉ HACE Y EN QUÉ ARCHIVO DEL PROYECTO SE ENCUENTRA. USA ESTE README COMO REFERENCIA RÁPIDA MIENTRAS TRABAJAS CON EL CÓDIGO***
