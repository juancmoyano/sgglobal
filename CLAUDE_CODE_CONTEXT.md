# SG GLOBAL — CONTEXTO DE PROYECTO PARA CLAUDE CODE
## Sesión de desarrollo web multi-página

---

## IDENTIDAD DEL PROYECTO

**Cliente:** SG Global — Intelligent Logistics Group  
**Managing Partner:** Juan Carlos Moyano  
**Web:** sgglobal.com.co  
**Repo:** https://github.com/juancmoyano/sgglobal  
**Correo contacto:** contactanos@sgglobal.com.co  
**Correo JCM:** jcmoyano@sgglobal.com.co  
**Tel:** +57 320 388 2637  

---

## SISTEMA DE MARCA — ARCTIC PRECISION

### Paleta de colores (OBLIGATORIA — no modificar)
```
--navy:            #1A2F4E   ← base corporativa
--navy2:           #0f1e33   ← fondo oscuro hero
--cyan:            #4DD9E0   ← acento primario / CTA
--sapphire:        #2563EB   ← SG Global Insurance
--aqua:            #06B6D4   ← SG Global Operations
--sky:             #38BDF8   ← SG Global Capital
--data-accent:     #4DD9E0   ← SG Global Data
```

### Tipografía (cargar siempre desde Google Fonts)
```
Cormorant Garamond → títulos H1/H2 (300, 400 italic)
Sora               → cuerpo, UI, labels (300, 400, 500)
```
```html
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;1,300;1,400&family=Sora:wght@300;400;500&display=swap" rel="stylesheet">
```

### Símbolo Pulse (usar en todas las páginas)
- Núcleo central circular
- 5 nodos satélite irradiando con líneas
- Siempre en color cyan `#4DD9E0` sobre fondos oscuros
- En fondos claros: usar `--aqua` (`#06B6D4`)
- Nunca es el elemento principal — siempre decorativo/marca de agua

### Reglas de diseño
- Fondo hero: siempre oscuro (`#0f1e33`) con animación canvas (red neuronal)
- Secciones alternas: oscuro (`#0f1e33`) / claro (`#f8fafc`)
- Imágenes de fondo: siempre con overlay de marca encima
- Botones primarios: fondo `--cyan`, texto `--navy2`, border-radius 100px
- Botones secundarios: borde `--cyan`, fondo transparente, border-radius 100px
- Todos los títulos: Cormorant Garamond, peso 300, itálica en el acento
- Navegación: siempre fija, blur backdrop, border-bottom sutil
- Formularios: border-radius 8px, fondo semi-transparente, focus en cyan

---

## ARQUITECTURA DE PÁGINAS

### Estructura del repositorio objetivo
```
sgglobal/
├── index.html              ← Página principal (HOME) ✅ EXISTE
├── seguros.html            ← Página SG Global Insurance 🔨 CREAR
├── data.html               ← Página SG Global Data (futuro)
├── operations.html         ← Página SG Global Operations (futuro)
├── capital.html            ← Página SG Global Capital (futuro)
├── assets/
│   └── (imágenes locales si aplica)
├── README.md               ← Documentación ✅ EXISTE
└── archive/
    └── sg-global-opciones.html  ← Referencia de diseño
```

---

## PÁGINA 1 — index.html (HOME) ✅ YA EXISTE

### Secciones actuales
1. **Nav** — Logo, links, toggle ES/EN, CTA "Conectar"
2. **Hero** — Red neuronal animada canvas + Pulse SVG watermark
3. **Nosotros** — Grid 2col: texto + 4 pilares
4. **Líneas de negocio** — Grid 2x2 con las 4 líneas
5. **Enfoque** — 3 columnas por qué SG Global
6. **Artículos** — 3 tarjetas editoriales ⚠️ links pendientes
7. **Newsletter** — Formulario suscripción ⚠️ Formspree pendiente
8. **Contacto** — Formulario completo ⚠️ Formspree pendiente
9. **Footer** — Logo, nav, copyright

### Pendientes en index.html
- [ ] Conectar Formspree al formulario de contacto
- [ ] Conectar Formspree al formulario de newsletter
- [ ] Activar links reales en las 3 tarjetas de artículos
- [ ] Verificar links a página `seguros.html` desde tarjeta Insurance

---

## PÁGINA 2 — seguros.html 🔨 CREAR DESDE CERO

### Propósito
Página dedicada a **SG Global Insurance** con profundidad de contenido,
explicación completa de la oferta, casos de uso y formulario de contacto
específico para seguros.

### Oferta de valor confirmada
- Seguros y Microseguros logísticos
- Coberturas para transportadores y operadores
- Cobertura de carga, flota y responsabilidad civil
- Seguros paramétricos vinculados a telemetría
- Gestión de siniestros especializada en logística
- Microseguros para todos los actores de la cadena

### Color de unidad
- Acento: `#2563EB` (Sapphire/Zafiro)
- Usar este color en lugar del cyan para todos los acentos de esta página

### Secciones sugeridas para seguros.html
1. Nav (mismo componente que index.html, con link activo en "Insurance")
2. Hero — imagen logística + Pulse + título de unidad
3. ¿Qué cubrimos? — grid de productos de seguro
4. ¿A quién va dirigido? — actores de la cadena
5. Cómo funciona — proceso de contratación y siniestros
6. Diferenciadores — paramétrico + telemetría
7. Formulario de cotización específico
8. Footer (mismo que index.html)

---

## FORMULARIOS — FORMSPREE

### Estado: ⏳ Pendiente configuración

Cuando el cliente comparta los endpoints, reemplazar en el código:

**Formulario de contacto** (index.html):
```html
<!-- Buscar: -->
<form class="cform" onsubmit="handleSubmit(event)">
<!-- Reemplazar con: -->
<form class="cform" action="https://formspree.io/f/ENDPOINT_CONTACTO" method="POST">
```

**Formulario newsletter** (index.html):
```html
<!-- Buscar: -->
<form class="nl-form" onsubmit="handleNL(event)">
<!-- Reemplazar con: -->
<form class="nl-form" action="https://formspree.io/f/ENDPOINT_NEWSLETTER" method="POST">
```

**Formulario cotización seguros** (seguros.html — por crear):
```html
<form action="https://formspree.io/f/ENDPOINT_SEGUROS" method="POST">
```

### Campos requeridos por Formspree
Cada `<input>` y `<textarea>` debe tener atributo `name`:
```html
<input type="text"  name="nombre"  ...>
<input type="email" name="email"   ...>
<input type="tel"   name="telefono"...>
<select             name="linea"   ...>
<textarea           name="mensaje" ...>
```

---

## ARTÍCULOS — LINKS EXTERNOS

### Estado: ⏳ URLs pendientes del cliente

Cuando el cliente comparta las URLs, reemplazar en index.html:

```html
<!-- Artículo 1 — Data & Telemetría -->
<a class="art-card" href="URL_ARTICULO_1">

<!-- Artículo 2 — Seguros & Riesgos -->
<a class="art-card" href="URL_ARTICULO_2">

<!-- Artículo 3 — Capital & M&A -->
<a class="art-card" href="URL_ARTICULO_3">
```

Agregar `target="_blank" rel="noopener"` para que abran en pestaña nueva.

---

## SISTEMA BILINGÜE ES/EN

### Cómo funciona (NO CAMBIAR la arquitectura)
Todas las páginas usan el mismo sistema de i18n con atributos data:

```html
<!-- Texto simple -->
<p data-i18n="clave.del.texto">Texto en español</p>

<!-- HTML con etiquetas (em, br) -->
<h1 data-i18n-html="hero.title">Título con <em>itálica</em></h1>

<!-- Placeholder de inputs -->
<input data-i18n-ph="form.placeholder" placeholder="texto">
```

### Función de cambio de idioma
```javascript
function setLang(l) {
  lang = l;
  document.documentElement.lang = l;
  // actualiza todos los elementos con data-i18n
}
```

### Regla para nuevas páginas
Cada página nueva debe incluir su propio diccionario `T = { es: {...}, en: {...} }`
con TODAS las cadenas de texto de esa página, en ambos idiomas.

---

## COMPONENTES REUTILIZABLES

### Nav (copiar en todas las páginas)
```html
<nav>
  <div class="logo">SG <em>Global</em></div>
  <ul class="nav-links">
    <li><a href="index.html"    data-i18n="nav.home">Inicio</a></li>
    <li><a href="index.html#nosotros" data-i18n="nav.about">Nosotros</a></li>
    <li><a href="index.html#lineas"   data-i18n="nav.lines">Líneas</a></li>
    <li><a href="seguros.html"        data-i18n="nav.insurance">Insurance</a></li>
    <li><a href="index.html#contacto" data-i18n="nav.contact">Contacto</a></li>
  </ul>
  <div class="nav-right">
    <div class="lang-toggle">
      <button class="lang-btn active" id="btn-es" onclick="setLang('es')">ES</button>
      <button class="lang-btn"        id="btn-en" onclick="setLang('en')">EN</button>
    </div>
    <a href="index.html#contacto" class="nav-cta" data-i18n="nav.cta">Conectar</a>
  </div>
</nav>
```

### Red neuronal canvas (copiar en páginas que lo necesiten)
El canvas de red neuronal del hero está en el `index.html` actual.
Buscar el bloque `/* ══ NEURAL NETWORK CANVAS ══ */` en el script
y copiar la función completa a cada nueva página.

### Pulse SVG (símbolo de marca)
```html
<svg class="pulse-mark" viewBox="0 0 48 48" fill="none">
  <circle cx="24" cy="24" r="5" fill="var(--cyan)"/>
  <line x1="24" y1="19" x2="24" y2="8"  stroke="var(--cyan)" stroke-width="1.2" opacity=".6"/>
  <line x1="24" y1="29" x2="24" y2="40" stroke="var(--cyan)" stroke-width="1.2" opacity=".6"/>
  <line x1="20" y1="22" x2="10" y2="16" stroke="var(--cyan)" stroke-width="1.2" opacity=".6"/>
  <line x1="28" y1="22" x2="38" y2="16" stroke="var(--cyan)" stroke-width="1.2" opacity=".6"/>
  <line x1="28" y1="26" x2="38" y2="32" stroke="var(--cyan)" stroke-width="1.2" opacity=".6"/>
  <circle cx="24" cy="6"  r="3" fill="var(--cyan)" opacity=".7"/>
  <circle cx="24" cy="42" r="3" fill="var(--cyan)" opacity=".7"/>
  <circle cx="8"  cy="14" r="3" fill="var(--cyan)" opacity=".7"/>
  <circle cx="40" cy="14" r="3" fill="var(--cyan)" opacity=".7"/>
  <circle cx="40" cy="34" r="3" fill="var(--cyan)" opacity=".7"/>
</svg>
```

---

## VALORES DE MARCA (tono de comunicación)

- Aprendizaje como ventaja competitiva
- Tecnología como reductor de fricción (no solo hardware/software)
- Integridad y conducta respetuosa ("caballeros y damas")
- Equipo primero
- Proactividad con sentido de pertenencia

**Posicionamiento aprobado:** "Socio Estratégico"  
**Tagline:** "La inteligencia que mueve la logística 360°"  
**Hero ES:** "Inteligencia / *para mover* / el mundo"  
**Hero EN:** "Intelligence / *to move* / the world"

---

## CHECKLIST — SESIÓN CLAUDE CODE

### Tareas inmediatas (en orden)
- [ ] 1. Abrir `index.html` desde el repo GitHub
- [ ] 2. Agregar atributo `name` a todos los campos de formularios
- [ ] 3. Conectar endpoints Formspree (cuando el cliente los comparta)
- [ ] 4. Activar links reales en las 3 tarjetas de artículos
- [ ] 5. Crear `seguros.html` siguiendo la arquitectura de marca
- [ ] 6. Actualizar nav en ambas páginas con links cruzados
- [ ] 7. Verificar bilingüe ES/EN en todas las páginas
- [ ] 8. Push a GitHub → verificar que Pages republique correctamente

### Criterios de calidad
- ✅ Cada página debe funcionar de forma independiente (sin frameworks externos)
- ✅ Todo el CSS inline en `<style>` dentro del mismo HTML
- ✅ Todo el JS inline en `<script>` al final del body
- ✅ Sin dependencias npm, sin build process — HTML puro
- ✅ Compatible con GitHub Pages (archivos estáticos solamente)
- ✅ Responsive mobile desde 320px hasta desktop 1920px
- ✅ Bilingüe completo en cada página nueva

---

## CÓMO USAR ESTE DOCUMENTO EN CLAUDE CODE

Al iniciar la sesión en Claude Code, comparta este archivo y diga:

> *"Este es el contexto del proyecto SG Global. Tenemos el index.html
> en el repositorio github.com/juancmoyano/sgglobal. Quiero empezar
> por [tarea específica]."*

Claude Code leerá el repositorio directamente y podrá editar,
crear y hacer commit de los archivos sin pasos intermedios.

---

*Documento generado desde Claude.ai · Proyecto SG Global · Abril 2025*
