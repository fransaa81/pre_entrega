# Pre-Entrega Proyecto: Mediaciones Familiares

## 1. HTML: Estructura y Sem�ntica

1. **Declaraci�n DOCTYPE y `<html>`**
   - `<!DOCTYPE html>` define el est�ndar HTML5.
   - `<html lang="es">` indica que el contenido est� en espa�ol.

2. **Secci�n `<head>`**
   - `<meta charset="UTF-8">` establece la codificaci�n de caracteres.
   - `<meta name="viewport" content="width=device-width, initial-scale=1.0">` asegura responsividad en dispositivos m�viles.
   - `<title>` define el t�tulo de la pesta�a del navegador.
   - **Google Fonts**: `<link href="https://fonts.googleapis.com/css2?family=Roboto..." rel="stylesheet">` importa la fuente Roboto.
   - **Font Awesome**: `<link rel="stylesheet" href="https://cdnjs.cloudflare.com/.../css/all.min.css">` para �conos.
   - `<link rel="stylesheet" href="styles.css">` enlaza el CSS externo.

3. **Encabezado `<header>`**
   - **Navegaci�n**: `<nav><ul>...<li><a href="#inicio">Inicio</a></li>...</ul></nav>` crea enlaces internos a secciones.
   - **Hero**: `<div class="hero" id="inicio">` contiene t�tulo principal `<h1>`, descripci�n `<p>` y bot�n `<a>` que lleva al formulario.

4. **Contenido principal `<main>`**
   - **Secci�n Servicios**
     - `<section id="servicios">` agrupa contenido de servicios.
     - `<div class="servicios-container">` usa Flexbox para alinear tres `<div class="card servicio">`, cada una con �cono, subt�tulo `<h3>` y p�rrafo `<p>`.

   - **Secci�n Testimonios**
     - `<section id="rese�as">` agrupa los testimonios.
     - `<div class="rese�as-grid">` usa CSS Grid para distribuir las tarjetas de testimonio (`.card.testimonio`). Cada tarjeta incluye imagen `<img>`, cita `<blockquote>` y autor `<p>`.

   - **Secci�n Contacto**
     - `<section id="contacto">` contiene el `<form>` de contacto.
     - Campos obligatorios:
       - `<label for="name">Nombre</label>` + `<input type="text" id="name" name="name" required>`
       - `<label for="email">Correo electr�nico</label>` + `<input type="email" ... required>`
       - `<label for="message">Mensaje</label>` + `<textarea id="message" name="message" rows="5" required>`
     - `<button type="submit">Enviar</button>` env�a datos a Formspree v�a `action="https://formspree.io/f/YOUR_FORM_ID" method="POST"`.

5. **Pie de p�gina `<footer>`**
   - Contiene `<p>&copy; 2025 Mediaciones Familiares. Todos los derechos reservados.</p>`.

---
## 2. CSS: Organizaci�n y Estilos

1. **Variables CSS**
   - Definidas en `:root`: colores personalizados (`--rojo`, `--azul`, `--verde`) y fuente (`--font`).

2. **Reset b�sico**
   - `* { margin:0; padding:0; box-sizing:border-box; }` unifica m�rgenes y rellenos.

3. **Tipograf�a global**
   - `body { font-family: var(--font); color:#333; line-height:1.6; }` aplica Roboto y define espaciado de texto.

4. **Navegaci�n**
   - `nav ul { display:flex; justify-content:center; background:var(--azul); }`
   - `nav a { color:#fff; padding:1.5rem 2rem; font-size:1.2rem; }` asegura enlaces amplios y legibles.

5. **Hero**
   - `.hero { text-align:center; padding:4rem 2rem; background:linear-gradient(to right, var(--rojo),var(--azul),var(--verde)); color:#fff; }`
   - `.btn` estiliza el bot�n con padding amplio y fuente destacada.

6. **Secci�n Servicios (Flexbox)**
   - `.servicios-container { display:flex; flex-wrap:wrap; justify-content:center; gap:2.5rem; padding:4rem 3rem; }`
   - `.servicio { flex:1 1 350px; padding:2rem; border-radius:6px; text-align:center; }` cards fluidas y centradas.

7. **Secci�n Testimonios (Grid)**
   - `.rese�as-grid { display:grid; grid-template-columns:repeat(auto-fit,minmax(240px,1fr)); gap:2.5rem; padding:4rem 3rem; }`
   - `.testimonio` define fondo, padding y bordes redondeados para cada tarjeta.

8. **Formulario de Contacto (Extra ancho)**
   - `#contacto form { display:flex; flex-direction:column; gap:4rem; padding:4rem 10%; width:100%; }` ocupa casi todo el ancho.
   - `input, textarea { width:100%; padding:1.5rem; font-size:1.1rem; border-radius:6px; }`
   - `textarea { min-height:200px; }` y `button` con padding y tama�o adecuados.

9. **Media Queries**
   - Solo para la navegaci�n en m�viles: `@media (max-width:600px) { nav ul { flex-direction:column; } }`.