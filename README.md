# Cravia — Sistema Operativo Digital

Propuesta visual completa del ecosistema digital de **Cravia — The Cookie State**, desarrollada por [STRYV](https://stryvstudio.com).

## Qué contiene

Cuatro sistemas integrados que componen el sistema operativo digital de Cravia:

| # | Sistema | Descripción |
|---|---------|-------------|
| 01 | **Plataforma del cliente** | Web + app para compras online, Cookie Club y loyalty |
| 02 | **Punto de venta (POS)** | Sistema para el mostrador — cobros, tickets, inventario |
| 03 | **Kiosco self-service** | Pantalla touch en tienda para auto-servicio |
| 04 | **Panel admin** | Dashboard centralizado multi-sucursal |

## Estructura

```
cravia-sistemas/
├── index.html                   Landing con acceso a los 4 sistemas
├── netlify.toml                 Config de deployment + redirects
├── README.md                    Este archivo
├── .gitignore
└── sistemas/
    ├── plataforma-cliente.html  Sistema 01
    ├── venta-cajera.html        Sistema 02
    ├── venta-kiosco.html        Sistema 03
    └── panel-admin.html         Sistema 04
```

## Features

### Responsive Design
- Desktop (1100px+), tablet (900px), mobile (640px), small mobile (380px)
- Nav sticky entre sistemas con hamburguesa en mobile
- Breakpoints específicos para cada componente (hero, packaging, locations, etc.)

### Navegación
- Nav sticky en la parte superior de los 4 sistemas
- Logo Cravia regresa al index principal
- Cambio rápido entre sistemas sin recargar contexto

### Animaciones CSS Premium
- Ken Burns effect (zoom lento infinito) en imágenes clave
- Fade-in on scroll con IntersectionObserver
- Hover scale en product cards y location cards
- Drift on hover en imágenes de packaging
- Smooth scroll global
- Hover state en botones y tabs

### Assets
- 13 imágenes png (packaging, productos, lifestyle, tiendas)
- 6 videos mp4 (hero, philosophy, unboxing, cliente, storefront, pattern)
- Logo oficial Cravia
- Todos alojados en Supabase Storage (bucket cravia)

## Deployment

### Opción A — Netlify manual (más rápido)
1. Entra a [app.netlify.com](https://app.netlify.com)
2. "Add new site" → "Deploy manually"
3. Arrastra la carpeta cravia-sistemas al área de drop
4. URL automática en ~15 segundos

### Opción B — GitHub + Netlify
1. Crea repo nuevo en GitHub: cravia-sistemas
2. Sube los archivos vía terminal:
   ```bash
   cd cravia-sistemas
   git init
   git add .
   git commit -m "Initial commit"
   gh repo create cravia-sistemas --public --source=. --push
   ```
3. En Netlify: "Import from Git" → conecta con GitHub → selecciona repo
4. Deploy automático en cada push a main

## URLs cortas configuradas en netlify.toml

Después del deploy, estas URLs redirigen a los sistemas:
- /cliente → Plataforma del cliente
- /pos → Punto de venta
- /kiosco → Kiosco self-service
- /admin → Panel admin

## Stack

- HTML + CSS vanilla (single-file por sistema)
- Fonts: Google Fonts (DM Serif Display, Caveat, Inter)
- Animaciones: CSS puro + IntersectionObserver
- Storage: Supabase Storage para imágenes y videos
- Deploy: Netlify

## Notas

- Los assets se cargan desde Supabase Storage — no es necesario copiarlos al repo
- Si un video no carga, verifica que el nombre en Supabase coincida con el referenciado
- El archivo Counter:mostrador.png tiene un ":" en el nombre — se recomienda renombrarlo a Counter-mostrador.png en Supabase para evitar problemas en algunos navegadores

---

**Construido por [STRYV](https://stryvstudio.com)** · Sistemas operativos digitales para negocios que crecen.
