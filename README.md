# SG Global — Sitio Web Corporativo

> **La inteligencia que mueve la logística 360°**

Sitio web corporativo de **SG Global**, grupo especializado en soluciones integrales para el sector logístico y de transporte en Latinoamérica.

---

## 🌐 Sitio en vivo

**URL GitHub Pages:** https://juancmoyano.github.io/sgglobal/

**Dominio corporativo:** https://sgglobal.com.co *(pendiente configuración DNS)*

---

## 📁 Estructura del repositorio

```
sgglobal/
├── index.html          ← Sitio web completo (bilingüe ES/EN)
├── README.md           ← Este archivo
└── archive/            ← Versiones y prototipos anteriores
    └── sg-global-opciones.html   ← 3 opciones de diseño (referencia)
```

---

## ✨ Características del sitio

- **Bilingüe** — Toggle ES / EN integrado, traducción completa sin recarga
- **Identidad Arctic Precision** — Paleta de marca, símbolo Pulse animado, tipografía Cormorant + Sora
- **Hero dinámico** — Red neuronal animada en canvas (paleta cyan/aqua/zafiro)
- **4 líneas de negocio** — Data, Insurance, Operations, Capital con colores diferenciados
- **Sección de artículos** — 3 tarjetas editoriales con imágenes y enlaces externos
- **Newsletter** — Formulario de suscripción con selector de cargo
- **Formulario de contacto** — Integrado con Formspree *(endpoint pendiente)*
- **Imágenes de fondo** — Fotografía logística real por sección vía Unsplash
- **Scroll reveal** — Animaciones de entrada al hacer scroll
- **Responsive** — Adaptado para móvil y desktop

---

## 🚀 Publicación — GitHub Pages

### Activar GitHub Pages
1. Ir a **Settings → Pages**
2. Source: **Deploy from a branch**
3. Branch: **main** / carpeta: **/ (root)**
4. Guardar → el sitio se publica en ~2 minutos

### Conectar dominio GoDaddy
Agregar estos registros DNS en GoDaddy:

| Tipo  | Nombre | Valor                |
|-------|--------|----------------------|
| A     | @      | 185.199.108.153      |
| A     | @      | 185.199.109.153      |
| A     | @      | 185.199.110.153      |
| A     | @      | 185.199.111.153      |
| CNAME | www    | juancmoyano.github.io |

Luego en GitHub Pages → **Custom domain** → escribir `sgglobal.com.co` → marcar ✓ **Enforce HTTPS**.

---

## 📧 Formulario de contacto — Formspree

**Estado:** ⏳ Pendiente configuración

### Pasos para activar:
1. Crear cuenta en [formspree.io](https://formspree.io)
2. Crear formulario "SG Global Contacto" → copiar endpoint
3. Crear formulario "SG Global Newsletter" → copiar endpoint
4. En `index.html`, reemplazar los dos `action` del formulario con los endpoints

```html
<!-- Formulario de contacto — buscar esta línea: -->
<form class="cform" onsubmit="handleSubmit(event)">
<!-- Cambiar a: -->
<form class="cform" action="https://formspree.io/f/XXXXXXXX" method="POST">

<!-- Formulario newsletter — buscar esta línea: -->
<form class="nl-form" onsubmit="handleNL(event)">
<!-- Cambiar a: -->
<form class="nl-form" action="https://formspree.io/f/YYYYYYYY" method="POST">
```

---

## 📰 Artículos — URLs pendientes

Los tres artículos están diseñados pero aún esperan los enlaces externos reales:

| # | Artículo | URL |
|---|----------|-----|
| 1 | Trazabilidad en tiempo real — Data & Telemetría | *(pendiente)* |
| 2 | Microseguros paramétricos — Seguros & Riesgos | *(pendiente)* |
| 3 | Consolidación logística LATAM — Capital & M&A | *(pendiente)* |

Para actualizar, reemplazar los `href="#articulos"` de cada tarjeta con la URL real.

---

## 🔄 Cómo actualizar el sitio

1. Descargar el `index.html` actualizado
2. En el repositorio → **Add file → Upload files** → reemplazar el archivo
3. Escribir en el commit: descripción del cambio (ej. *"Actualiza artículos"*)
4. **Commit changes** → el sitio se republica automáticamente en ~60 segundos

---

## 🏢 Líneas de negocio

| Unidad | Color | Descripción |
|--------|-------|-------------|
| **SG Global Data** | Cyan `#4DD9E0` | Telemetría, trazabilidad, RNDC, Torre de Control |
| **SG Global Insurance** | Zafiro `#2563EB` | Seguros y microseguros logísticos |
| **SG Global Operations** | Aqua `#06B6D4` | Montaje y estructuración de operaciones |
| **SG Global Capital** | Sky `#38BDF8` | M&A y financiamiento logístico |

---

## 📬 Contacto

- **Email:** contactanos@sgglobal.com.co
- **Web:** sgglobal.com.co
- **LinkedIn:** *(pendiente)*

---

*Desarrollado con identidad de marca Arctic Precision · Sistema bilingüe ES/EN · © 2025 SG Global*
