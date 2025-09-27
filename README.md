# <img src="https://media3.giphy.com/media/v1.Y2lkPTc5MGI3NjExbHI3ZDBoaDM5OWk4ODRmNWo0c2ppeHh6eTR3d2QzczJ2MXMwNzRmNCZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9cw/jdPMeyv9rn0hZHh8n9/giphy.gif" width="40"/> KarenFlix — Frontend (HTML + CSS + JS)

> En este repo construimos el **frontend** de KarenFlix en **JavaScript “puro”** (sin frameworks). Priorizamos accesibilidad, modularidad y un consumo limpio de la API del backend. 

<br>

## 🏷️ Badges

### Tecnologías
![HTML5](https://img.shields.io/badge/HTML5-sem%C3%A1ntico-E34F26?logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-responsivo-1572B6?logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-ES2022-F7DF1E?logo=javascript&logoColor=000)
![Vite](https://img.shields.io/badge/Dev%20Server-Vite-646CFF?logo=vite&logoColor=fff)

<br>

### Calidad y estilo
![ESLint](https://img.shields.io/badge/ESLint-config-4B32C3?logo=eslint&logoColor=white)
![Prettier](https://img.shields.io/badge/Prettier-format-1A2C34?logo=prettier&logoColor=F7B93E)
![EditorConfig](https://img.shields.io/badge/EditorConfig-alineado-lightgrey)

<br>

### Accesibilidad y UX
![A11y](https://img.shields.io/badge/A11y-WAI--ARIA-blueviolet)
![Responsive](https://img.shields.io/badge/Responsive-Mobile--first-brightgreen)

<br>

### Deploy
![Vercel](https://img.shields.io/badge/Deploy-Vercel-000?logo=vercel)
![Netlify](https://img.shields.io/badge/Deploy-Netlify-00C7B7?logo=netlify&logoColor=fff)
![GitHub Pages](https://img.shields.io/badge/Deploy-GitHub%20Pages-181717?logo=github)

<br>

---

<br>

## <img src="https://media0.giphy.com/media/v1.Y2lkPTc5MGI3NjExbW40OGttN3RicThza3lucW1tZHhlMDVibHRlc2RiYmx0YnNwOWwyYyZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9cw/sUvXqhA9nukbIM0MyO/giphy.gif" width="30"/> Índice

- [Arquitectura](#arquitectura)
- [Stack y principios](#stack-y-principios)
- [Requisitos previos](#requisitos-previos)
- [Instalación](#instalación)
- [Variables de entorno](#variables-de-entorno)
- [Ejecución](#ejecución)
- [Build y estáticos](#build-y-estáticos)
- [Consumo de API](#consumo-de-api)
- [Estado y almacenamiento](#estado-y-almacenamiento)
- [Estilos y componentes](#estilos-y-componentes)
- [Accesibilidad (A11y)](#accesibilidad-a11y)
- [Manejo de errores y vacíos](#manejo-de-errores-y-vacíos)
- [Despliegue](#despliegue)
- [Contribución y Git Flow](#contribución-y-git-flow)
- [Planeación (SCRUM) y evidencias](#planeación-scrum-y-evidencias)
- [Licencia y créditos](#licencia-y-créditos)


<br><br>

## <img src="https://media3.giphy.com/media/v1.Y2lkPTc5MGI3NjExM2h2dmsxbWp4b3N4a3djN2duYmgwcTJtNmdrdG56dWozMm4wMnlzMyZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9cw/lSa5REAX23ECgpcDHj/giphy.gif" width="30"/> Arquitectura

Pensamos la app en módulos pequeños y testeables. Cada carpeta tiene un propósito claro:

``` js
index.html     # raíz del documento; punto de entrada del frontend
/css           # estilos globales del proyecto
  style.css
/js            # scripts con la lógica y funcionalidades
  main.js
README.md      # documentación del proyecto
```
---

- **index.html** archivo raíz que carga los estilos y scripts principales.  
- **/css/** contiene los estilos globales del proyecto (tipografías, colores, layout).  
- **/js/** agrupa la lógica y funcionalidades en JavaScript (manejo del DOM, eventos, interacciones).  
- **README.md** documentación básica del repositorio.  


<br><br>


##  <img src="https://media3.giphy.com/media/v1.Y2lkPTc5MGI3NjExZmdpNjNzd2I5NWZtZ2x3Y3dmZ25obGFwdmJ0YzA2ajFxdzA2OXNhYiZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9dHM/kAm4u0lhDCmXnugz6p/giphy.gif" width="30"/> Stack y principios

- **HTML semántico** + **CSS responsivo** (mobile-first).
- **JavaScript modular** (ESM) y **fetch API** nativa.
- **Hash routing** para evitar configuración de servidor SPA.
- **A11y** con roles/atributos ARIA y foco manejado.
- **DX**: Vite como dev server (opcional, sin framework).
- **Seguridad**: nunca exponemos secrets en el cliente; tokens en **memory** + `localStorage` opt-in.


<br><br>


##  <img src="https://media4.giphy.com/media/v1.Y2lkPTc5MGI3NjExN2liYTJtbmdwNmp6aHIwM214b3F5d2ttOG94azJlajI1cjNpNWttaiZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9cw/NPjKrInDbAHJelWm5X/giphy.gif" width="30"/> Requisitos previos

- Node.js **18+** (si usamos Vite para desarrollo/build).
- Navegador moderno (para ESM y fetch).

<br><br>

## <img src="https://media4.giphy.com/media/v1.Y2lkPTc5MGI3NjExN2liYTJtbmdwNmp6aHIwM214b3F5d2ttOG94azJlajI1cjNpNWttaiZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9cw/NPjKrInDbAHJelWm5X/giphy.gif" width="30"/> Instalación

Explicamos cómo levantarlo rápido y cómo trabajarlo en equipo:

```bash
# 1) Clonar el repo
git clone https://github.com/AuraCamilaPicoAraque/Proyecto_Express_S1_PicoAura_LizcanoNaya_frontend
```

Podemos abrir `public/index.html` con Live Server u otro servidor estático

<br><br>

## <img src="https://media0.giphy.com/media/v1.Y2lkPTc5MGI3NjExMW92dTE1ZDJ0c3g0cDRhbzdjdGExc3VqbXl4czFpanMyYTM3anNjcyZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9cw/dFv9SnGralwSQwfuBp/giphy.gif" width="30"/> Variables de entorno

Definimos el origen del backend y flags de build. Con Vite:

```ini
# .env (desarrollo)
VITE_API_BASE=http://localhost:3000/api/v1
VITE_APP_NAME=KarenFlix
```

En `src/config.js` centralizamos el acceso:

```js
export const API_BASE = import.meta?.env?.VITE_API_BASE || "http://localhost:3000/api/v1";
export const APP_NAME = import.meta?.env?.VITE_APP_NAME || "KarenFlix";
```

> Nota: el backend debe permitir CORS desde el origen del dev server (p. ej., `http://localhost:5173`).

<br><br>

## <img src="https://media1.giphy.com/media/v1.Y2lkPTc5MGI3NjExYmZxcHlwOTJtbzh2bm0xMWRwZWllc2E2bTU0d3NyaXV5ajBzMm5tZCZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9cw/JOrED1HkYfgjEZwJd3/giphy.gif" width="30"/> Ejecución

```bash
# Desarrollo (Vite)
npm run .
# abre: http://localhost:5173

# Lint opcional
npm run lint
npm run format
```

Sin Vite: servir `/public` con un servidor estático (ej. `npx serve public`).

<br><br>


## 🧭 Navegación y rutas

Usamos **hash routing** para evitar 404 del servidor:

- `#/` → Home (listado y ranking de películas)
- `#/login` → formulario de acceso
- `#/movie/:id` → detalle con reseñas
- `#/profile` → perfil y reseñas propias
- `#/categories` → catálogo por categoría

El enrutador escucha `hashchange` y renderiza la vista correspondiente. Si la ruta no existe, mostramos una página 404 accesible.

<br><br>

## <img src="https://media0.giphy.com/media/v1.Y2lkPTc5MGI3NjExYWJvZ3E0eDI0cGswOGs1dXdyZGtpNGFtazY3N3ZobGJicjNoaWNyZyZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9cw/DjuXSRQ9PYkqvL3DAK/giphy.gif" width="30"/>  Consumo de API

Centralizamos llamadas en `src/services/api.js` para desacoplar UI de red.

```js
poner aqui cuando se desarrolla
```

- **Errores**: propagamos el JSON del backend para mostrar mensajes útiles.
- **Paginación/orden**: `listMovies({ sort: "ranking", order: "desc", page: 1, limit: 20 })`.

<br><br>

##  <img src="https://media2.giphy.com/media/v1.Y2lkPTc5MGI3NjExZXZncTNjNWY3YWV6amdzdGF4Mm5ib3d6ZHB2dTYwcXUwMXhmaTF6diZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9cw/TbJtNftH7OzNFm1MNE/giphy.gif" width="30"/> Estado y almacenamiento

- Guardamos el **token** en **memory** y opcionalmente en `localStorage` (con opt-in explícito del usuario “Recordarme”).  
- Al cerrar sesión, limpiamos token y estado.
- Para caché de catálogos (categorías, top N), usamos `sessionStorage` con TTL simple.

<br><br>

## <img src="https://media2.giphy.com/media/v1.Y2lkPTc5MGI3NjExMnk3azFtNDU3Z3d1aTl6aTNtcDF5a29yNXlmejFrbm96Z2swMjMzdyZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9cw/8T2sUmuGlWU7ahH5Ev/giphy.gif" width="30"/> Estilos y componentes

- CSS modular en `/styles` con **variables CSS** y utilidades (espaciado, grid).  
- Convención **BEM** para bloques y elementos.  
- Componentes UI como funciones puras que devuelven `HTMLElement` o strings de plantilla; por ejemplo `MovieCard(movie)`.

```js
poner cuando ya lo tengamos
```
<br><br>

## <img src="https://media3.giphy.com/media/v1.Y2lkPTc5MGI3NjExM2ZkODB3ZXRhNG1mdjhiamZzbmw1NnloNDk5b21wejU5MHBkeXp1YyZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9cw/RlO1xYMj3eX3yXZQEp/giphy.gif" width="30"/> Accesibilidad (A11y)

- **Focus management** al cambiar de ruta (`main` recibe foco).
- **Labels** y descripciones en formularios.
- **Contraste** AA mínimo; chequeos rápidos con extensiones.
- **Semántica**: `header`, `main`, `nav`, `section`, `footer`.

<br><br>

## <img src="https://media3.giphy.com/media/v1.Y2lkPTc5MGI3NjExOWU0aHhrNHoxdHEyM3Vidmc3ZHI0aXZ4bWdxaDY3aWNpOXdhb3R0dCZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9cw/WRocW2SN1BFk49SFQR/giphy.gif" width="30"/> Manejo de errores y vacíos

- Estados de **carga**, **vacío** (“No hay reseñas todavía”) y **error** con mensajes claros.
- Reintentos limitados en llamadas críticas (login, crear reseña).
- Toasts o banners no intrusivos para feedback.

<br><br>

##  <img src="https://media2.giphy.com/media/v1.Y2lkPTc5MGI3NjExdWdreHIxeW1rczRud3RqcnJ6ejltanpsZDdrcm5vaG04aTE3Y3Y0ZCZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9cw/M4NykXxUE0HAcK7UJ6/giphy.gif" width="30"/> Despliegue

- **Vercel/Netlify**: apuntar al directorio `/dist` tras `npm run build`.
- **GitHub Pages**: publicar `/dist` (ojo con rutas hash).
- Configurar la variable `VITE_API_BASE` al dominio del backend en producción.
- CORS en backend debe permitir el dominio público del frontend.

<br><br>

## <img src="https://media3.giphy.com/media/v1.Y2lkPTc5MGI3NjExYTdxa3ZzcWhha2NqaXpqMm1leTIzNjk4YzU3YjczZTZ5amwxM2wzOCZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9cw/kH1DBkPNyZPOk0BxrM/giphy.gif" width="30"/> Contribución y Git Flow

- **Commits**: Conventional Commits.
- **Ramas**: `main` (estable), `dev` y features por issue.
- **PRs**: descripción, capturas y checklist de linters.
- **CI**: correr `lint` en cada PR.

<br><br>

##  <img src="https://media4.giphy.com/media/v1.Y2lkPTc5MGI3NjExODFzemswZmljOGY4aWo1cnJ5Y2VwcTlnM3FocjRlcWQzcG1nNGM4YiZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9cw/VtdEHkFxEA9nMPNExT/giphy.gif" width="30"/> Planeación (SCRUM) y evidencias

- Trabajamos con **SCRUM** en **≥ 2 sprints**.  
- Seguimiento en tablero (GitHub Projects / Trello / ClickUp).
- Evidencias:
  - `/planning/scrum.pdf` con la planeación del frontend.
  - Video (≤10 min) con explicación técnica y demo (consumiendo backend).

> Enlace al video (pendiente): `[Video](https://...)`

<br><br>

##  <img src="https://media3.giphy.com/media/v1.Y2lkPTc5MGI3NjExdDN1cXQwOXZxMm9obWJ5azI4dnY5NTg3c3JwNGZnYWxzZGZzbWlmMCZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9cw/1ji2Ht5MVO4wnQxQHL/giphy.gif" width="30"/> Licencia y créditos

- Licencia: MIT (o la que definamos como equipo).
- Créditos: Equipo KarenFlix.