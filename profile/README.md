<div align="center">


<br/>
<br/>

<img src="../assets/logo.png" alt="Nexus Logo" width="200"/>

# Nexus App — GitHub Oficial

**Portal de presentación, documentación técnica y marketing de Nexus**, la plataforma unificada de marketplace de segunda mano, chollometro comunitario y publicidad B2B para empresas.

[![Astro](https://img.shields.io/badge/Astro-5.x-FF5D01?style=flat-square&logo=astro&logoColor=white)](https://astro.build/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.x-3178C6?style=flat-square&logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![Vercel](https://img.shields.io/badge/Deployed%20on-Vercel-black?style=flat-square&logo=vercel)](https://vercel.com/)
[![License](https://img.shields.io/badge/Propiedad-Ecentia-9d5ae5?style=flat-square)](mailto:somosnexusapp@gmail.com)

*Proyecto Final de Grado Superior — DAM | IES Francisco Rodríguez Marín, Osuna (Sevilla)*

---

[🚀 Demo en vivo](#) · [📖 Documentación](#-documentación-técnica) · [🐛 Reportar un bug](mailto:somosnexusapp@gmail.com) · [💬 Contacto](mailto:somosnexusapp@gmail.com)

</div>

---

## 📋 Tabla de contenidos

- [Sobre el proyecto](#-sobre-el-proyecto)
- [Ecosistema Nexus](#-ecosistema-nexus)
- [Stack tecnológico](#-stack-tecnológico)
- [Estructura del repositorio](#-estructura-del-repositorio)
- [Instalación y desarrollo local](#-instalación-y-desarrollo-local)
- [Páginas y rutas](#-páginas-y-rutas)
- [Capturas de pantalla](#-capturas-de-pantalla)
- [Equipo](#-equipo)
- [Licencia](#-licencia)

---

## 🌐 Sobre el proyecto

Este repositorio contiene la **web informativa y de marketing de Nexus** (`nexus-web-about`), construida con **Astro**. Se trata de uno de los cuatro submódulos que componen el ecosistema completo de la plataforma.

Su función principal es:

- Presentar la propuesta de valor de Nexus al público general.
- Alojar la **documentación técnica oficial** del proyecto de fin de grado (memoria, requisitos, diseño, pruebas, etc.).
- Publicar el **blog de desarrollo** con artículos sobre arquitectura, IA, diseño y DevOps.
- Servir las páginas legales (Política de Privacidad, Aviso Legal, Cookies, Términos).
- Ofrecer el **Centro de Ayuda** con FAQ interactivo.
- Exponer el **stack tecnológico** y el prototipo en Figma.

Al generarse como sitio estático (HTML puro), logra tiempos de carga casi nulos y un SEO óptimo, sin JavaScript en el cliente salvo donde es estrictamente necesario.

---

## 🏗 Ecosistema Nexus

Nexus está compuesto por cuatro submódulos independientes que comparten un único backend:

| Repositorio | Descripción | Deploy |
|---|---|---|
| `nexus-backend` | API REST (48 endpoints) + WebSocket STOMP — Spring Boot 3 (Java 17) | Render (Docker) |
| `nexus-angular-app` | App de usuario — Angular 21 + Ionic 8 + Capacitor 8 | Vercel |
| `nexus-admin-web-app` | Panel de administración — Angular 21 | Vercel (subdominio) |
| **`nexus-web-about`** ← **(este repo)** | Web informativa y docs — Astro | Vercel |

```
                    ┌──────────────────────────────────┐
                    │        nexus-backend              │
                    │   Spring Boot 3.5 · Java 17       │
                    │   48 REST + 1 WebSocket · Docker  │
                    └──────────┬────────────────────────┘
                               │  HTTP REST + JWT Bearer
          ┌────────────────────┼─────────────────────────────┐
          │                    │                             │
 ┌────────▼───────┐  ┌─────────▼──────────┐  ┌─────────────▼──────┐
 │ nexus-angular  │  │  nexus-admin-web   │  │  nexus-web-about   │
 │ Angular 21     │  │  Angular 21        │  │  Astro (este repo) │
 │ Ionic 8        │  │  Panel Admin       │  │  Web informativa   │
 │ Capacitor → APK│  │  Subdominio        │  │  Docs + Blog       │
 └────────────────┘  └────────────────────┘  └────────────────────┘
```

---

## 🛠 Stack tecnológico

### Web informativa (este repo)

| Tecnología | Versión | Uso |
|---|---|---|
| [Astro](https://astro.build/) | 5.x | Framework SSG principal |
| TypeScript | 5.x | Tipado estático |
| GSAP | 3.12.5 | Animaciones en landing |
| Mermaid / Diagramas | — | Diagramas UML en docs |

### Plataforma completa

<table>
<tr>
<td align="center"><img src="../assets/herramientas/java.png" height="40"/><br/><b>Java 17</b></td>
<td align="center"><img src="../assets/herramientas/srping.png" height="40"/><br/><b>Spring Boot 3</b></td>
<td align="center"><img src="../assets/herramientas/angular.png" height="40"/><br/><b>Angular 21</b></td>
<td align="center"><img src="../assets/herramientas/typescript.png" height="40"/><br/><b>TypeScript 5</b></td>
<td align="center"><img src="../assets/herramientas/postgresql.png" height="40"/><br/><b>PostgreSQL</b></td>
<td align="center"><img src="../assets/herramientas/capacitor.png" height="40"/><br/><b>Capacitor 8</b></td>
</tr>
<tr>
<td align="center"><img src="../assets/herramientas/gemini.png" height="40"/><br/><b>Gemini AI</b></td>
<td align="center"><img src="../assets/herramientas/groq.png" height="40"/><br/><b>Groq</b></td>
<td align="center"><img src="../assets/herramientas/recaptcha.png" height="40"/><br/><b>reCAPTCHA</b></td>
<td align="center"><img src="../assets/herramientas/correos.png" height="40"/><br/><b>Correos</b></td>
<td align="center"><img src="../assets/herramientas/vscode.png" height="40"/><br/><b>VS Code</b></td>
<td align="center"><img src="../assets/herramientas/cursor.png" height="40"/><br/><b>Cursor IDE</b></td>
</tr>
</table>

**Servicios externos:** Stripe (pagos), Cloudinary (medios), Google OAuth 2.0, Gmail SMTP, OpenStreetMap, ZXing (QR).

---

## 📁 Estructura del repositorio

```
nexus-web-about/
├── public/
│   ├── assets/
│   │   ├── herramientas/        # Logos de tecnologías
│   │   ├── CEOs/                # Fotos del equipo
│   │   ├── img-pruebas/         # Capturas web (app usuario)
│   │   ├── img-pruebas-admin/   # Capturas panel de administración
│   │   ├── img-pruebas-mobile/  # Capturas app Android
│   │   ├── img-pruebas-compra/  # Capturas flujo de compra
│   │   └── img-pruebas-msg-*/   # Capturas mensajería y reservas
│   ├── logo.webp
│   └── favicon.ico
├── src/
│   ├── layouts/
│   │   ├── Layout.astro         # Layout principal (header + footer + nav)
│   │   └── DocLayout.astro      # Layout para documentación técnica
│   └── pages/
│       ├── index.astro          # Landing page principal
│       ├── documentacion.astro  # Memoria técnica completa del TFG
│       ├── tecnologias.astro    # Stack tecnológico
│       ├── ayuda.astro          # Centro de ayuda con FAQ
│       ├── 404.astro            # Página de error
│       ├── blog/
│       │   ├── index.astro      # Listado del blog
│       │   ├── [id].astro       # Post por ID
│       │   └── [slug].astro     # Post por slug
│       └── legal/
│           ├── privacidad.astro
│           ├── terminos.astro
│           ├── cookies.astro
│           ├── aviso-legal.astro
│           ├── accesibilidad.astro
│           └── condiciones-compra.astro
├── astro.config.mjs
├── tsconfig.json
└── package.json
```

---

## 🚀 Instalación y desarrollo local

### Requisitos previos

- Node.js ≥ 18.x
- npm o pnpm

### Pasos

```bash
# 1. Clonar el repositorio
git clone https://github.com/ecentia/nexus-web-about.git
cd nexus-web-about

# 2. Instalar dependencias
npm install

# 3. Arrancar el servidor de desarrollo
npm run dev
# → http://localhost:4321

# 4. Construir para producción
npm run build

# 5. Previsualizar el build
npm run preview
```

### Scripts disponibles

| Comando | Descripción |
|---|---|
| `npm run dev` | Servidor de desarrollo con HMR en `localhost:4321` |
| `npm run build` | Build estático optimizado en `dist/` |
| `npm run preview` | Preview del build de producción |
| `npm run astro check` | Validación de tipos TypeScript |

---

## 📄 Páginas y rutas

| Ruta | Descripción |
|---|---|
| `/` | Landing page con hero, tech strip, servicios y team |
| `/documentacion` | Memoria técnica completa (Plan de Proyecto, Análisis, Diseño, Pruebas…) |
| `/tecnologias` | Stack tecnológico por categorías |
| `/ayuda` | Centro de ayuda con FAQ interactivo y buscador |
| `/blog` | Listado de artículos de desarrollo |
| `/blog/[id]` | Artículo individual |
| `/legal/privacidad` | Política de Privacidad (RGPD) |
| `/legal/terminos` | Términos y Condiciones |
| `/legal/cookies` | Política de Cookies |
| `/legal/aviso-legal` | Aviso Legal |
| `/legal/accesibilidad` | Declaración de Accesibilidad (WCAG 2.1 AA) |
| `/legal/condiciones-compra` | Condiciones de Compra |
| `/404` | Página de error personalizada |

---

## 📸 Capturas de pantalla

### Aplicación web — Usuario

| Inicio (visitante) | Pantalla principal — Secciones | Detalle de producto |
|---|---|---|
| ![Inicio invitado](../assets/img-pruebas/pantalla-inicio-invitado.png) | ![Chollos del día](../assets/img-pruebas/pantalla-principal-Chollos-del-dia.png) | ![Detalle producto](../assets/img-pruebas/producto-detail.png) |

| Detalle de vehículo | Detalle de oferta | Categoría de coches |
|---|---|---|
| ![Coche detail](../assets/img-pruebas/coche-detail.png) | ![Oferta detail](../assets/img-pruebas/oferta-producto-detail.png) | ![Categoría coches](../assets/img-pruebas/pantalla-categoria-coches.png) |

---

### Registro e inicio de sesión

| Registro | Verificación OTP | Inicio de sesión | Login con 2FA |
|---|---|---|---|
| ![Registro](../assets/img-pruebas/registro-normal.png) | ![Verificación](../assets/img-pruebas/verificacion-registro.png) | ![Login](../assets/img-pruebas/inicio-sesion-normal.png) | ![2FA](../assets/img-pruebas/inicio-sesion-normal-2.png) |

---

### Publicación de anuncios

| Selección de tipo | Detalles básicos | Fotos y descripción | Precio y ubicación |
|---|---|---|---|
| ![Publicar](../assets/img-pruebas/publicar.png) | ![Detalles](../assets/img-pruebas/publicar-producto-detalles-basicos.png) | ![Fotos](../assets/img-pruebas/publicar-subir-producto-Fotos-y-descripcion.png) | ![Precio](../assets/img-pruebas/publicar-subir-producto-Precio-y-ubicacion.png) |

---

### Perfil y configuración

| Resumen del perfil | Estadísticas | Mi cuenta — Seguridad | Mi cuenta — Notificaciones |
|---|---|---|---|
| ![Perfil resumen](../assets/img-pruebas/perfil-resumen.png) | ![Estadísticas](../assets/img-pruebas/perfil-estadisticas.png) | ![Seguridad](../assets/img-pruebas/micuenta-seguridad.png) | ![Notificaciones](../assets/img-pruebas/micuenta-notificaciones.png) |

---

### Funcionalidades destacadas

| Cerca de ti (50km) | Cerca de ti (10km) | Soporte con IA | Soporte con humano |
|---|---|---|---|
| ![50km](../assets/img-pruebas/pantalla-cerca-de-ti-50km-2coches.png) | ![10km](../assets/img-pruebas/pantalla-prueba-cerca-de-ti-radar-10km-1coche.png) | ![IA soporte](../assets/img-pruebas/soporte-chat-con-ia-normal.png) | ![Humano soporte](../assets/img-pruebas/soporte-chat-con-humano.png) |

---

### Panel de Administración

| Login Admin | Dashboard | Estadísticas en tiempo real |
|---|---|---|
| ![Login admin](../assets/img-pruebas-admin/login.png) | ![Dashboard](../assets/img-pruebas-admin/dashboard.png) | ![Estadísticas](../assets/img-pruebas-admin/estadisticas-live-1.png) |

| Gestión de usuarios | Moderación de productos | Gestión de ofertas |
|---|---|---|
| ![Usuarios](../assets/img-pruebas-admin/usuarios-lista.png) | ![Productos](../assets/img-pruebas-admin/productos.png) | ![Ofertas](../assets/img-pruebas-admin/ofertas.png) |

| Cupones | Newsletter | Soporte — Panel |
|---|---|---|
| ![Cupones](../assets/img-pruebas-admin/cupones.png) | ![Newsletter](../assets/img-pruebas-admin/newsletter-automatizacion-semanal.png) | ![Soporte](../assets/img-pruebas-admin/soporte-chat-panel.png) |

| 2FA Admin — QR | Sanciones | Configuración global |
|---|---|---|
| ![2FA QR](../assets/img-pruebas-admin/2fa-qr.png) | ![Sanciones](../assets/img-pruebas-admin/sanciones.png) | ![Config](../assets/img-pruebas-admin/configuracion-1.png) |

---

### Aplicación móvil Android (Ionic + Capacitor 8)

| Inicio | Menú categorías | Detalle coche | Perfil |
|---|---|---|---|
| ![Inicio móvil](../assets/img-pruebas-mobile/pantalla-inicio-invitado.png) | ![Categorías móvil](../assets/img-pruebas-mobile/desplegable-izquierda-categorias.png) | ![Coche móvil](../assets/img-pruebas-mobile/coche-detail.png) | ![Perfil móvil](../assets/img-pruebas-mobile/perfil.png) |

| Publicar anuncio | Mis cosas | Ajustes seguridad | Verificación registro |
|---|---|---|---|
| ![Publicar móvil](../assets/img-pruebas-mobile/publicar.png) | ![Mis cosas](../assets/img-pruebas-mobile/perfil-mis-cosas.png) | ![Seguridad móvil](../assets/img-pruebas-mobile/perfil-ajustes-seguridad.png) | ![Verificación móvil](../assets/img-pruebas-mobile/verificacion-registro.png) |

---

## 📖 Documentación técnica

La documentación completa del proyecto está disponible en la ruta `/documentacion` y cubre:

- **Plan de Proyecto** — Cronograma, gestión de riesgos y plan de comunicación
- **Estudio de Viabilidad** — Análisis económico, técnico, operativo y legal
- **Requisitos del Sistema** — 63 RF + 26 RNF + 17 RI + actores + casos de uso
- **Diseño** — Arquitectura del sistema, modelo de BD (29 entidades), diseño API REST, diseño UI
- **Implementación** — Estructura de carpetas, decisiones técnicas (8 DTs), flujos principales
- **Pruebas** — Pruebas funcionales con capturas reales + 7 pruebas unitarias especificadas
- **Despliegue** — Render (Docker), Vercel, Capacitor (APK Android)
- **Conclusiones** — Objetivos cumplidos, dificultades y 10 líneas de mejora futuras
- **Bibliografía** — +30 referencias técnicas
- **Anexos** — Glosario, tabla de endpoints y resumen del modelo de BD
- **Diagrama de Dominio UML**
- **Mockup Interactivo** en Figma (prototipo de alta fidelidad)

---

## 👥 Equipo

<table>
<tr>
<td align="center">
<img src="../assets/CEOs/kirri_traje.png" width="120" style="border-radius:50%"/><br/>
<b>José Manuel Jiménez</b><br/>
CEO & Desarrollador<br/>
<a href="https://www.linkedin.com/in/josemajr6/">LinkedIn</a> · <a href="https://www.instagram.com/josemajr_6/">Instagram</a>
</td>
<td align="center">
<img src="../assets/CEOs/rafa_traje.png" width="120" style="border-radius:50%"/><br/>
<b>Rafael Lázaro</b><br/>
CEO & Desarrollador<br/>
<a href="https://www.linkedin.com/in/rafalazarodam/">LinkedIn</a> · <a href="https://www.instagram.com/rafald_10/">Instagram</a>
</td>
<td align="center">
<img src="../assets/CEOs/juanjo_traje.png" width="120" style="border-radius:50%"/><br/>
<b>Juan José Gamero</b><br/>
CEO & Desarrollador<br/>
<a href="https://www.linkedin.com/in/juan-jos%C3%A9-gamero-l%C3%B3pez-76326b27a/">LinkedIn</a> · <a href="https://www.instagram.com/juuaanjoo_21/">Instagram</a>
</td>
</tr>
</table>

---

## 🏫 Contexto académico

| Campo | Detalle |
|---|---|
| **Proyecto** | Trabajo de Fin de Grado (TFG) |
| **Ciclo** | Grado Superior en Desarrollo de Aplicaciones Multiplataforma (DAM) |
| **Centro** | IES Francisco Rodríguez Marín — Osuna, Sevilla |
| **Empresa ficticia** | Ecentia |
| **Período** | Noviembre 2025 – Mayo 2026 |

---

## 📜 Licencia

© 2026 **Ecentia**. Todos los derechos reservados.

Este proyecto es propiedad exclusiva de Ecentia y ha sido desarrollado con fines académicos para el IES Francisco Rodríguez Marín. Queda prohibida la reproducción, distribución o explotación comercial sin autorización expresa por escrito.

Para consultas: [somosnexusapp@gmail.com](mailto:somosnexusapp@gmail.com)

---

<div align="center">

Hecho con ❤️ en Osuna, Sevilla · Ecentia © 2026

</div>
