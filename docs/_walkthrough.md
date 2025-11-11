# 🎥 MASTERCLASS TAILWIND CSS — GUION TÉCNICO

> "Crea una Landing Profesional desde Cero (y personalízala con tu propio tema)"

## 🕐 0:00 — Introducción

**LEE:**  
Hola, soy Oriol Cortés, y hoy vamos a construir juntos una landing page profesional con Tailwind CSS.
Solo con HTML y Tailwind, sin frameworks.
En menos de una hora tendrás una web moderna, responsive, con modo oscuro y colores personalizados.
Y además aprenderás cómo encontrar por ti mismo cualquier clase o utilidad de Tailwind.

**👁️ MUESTRA:**  
Pantalla inicial con la carpeta vacía del proyecto: `landing-tailwind/`.

---

## 🕐 1:30 — Setup inicial y filosofía Tailwind

**LEE:**  
Tailwind se basa en clases utilitarias: en lugar de escribir CSS, describes el diseño con pequeñas clases ya preparadas.
Vamos a usar el CDN para no tener que instalar nada y hacerlo todo inmediato.
El CDN es básicamente un servidor externo que nos sirve Tailwind ya listo para usar, sin instalaciones.
Así podrás probar Tailwind sin preocuparte por configuraciones.

**🎹 ESCRIBE:**  
Crea `index.html` y escribe:

```html
<!DOCTYPE html>
<html lang="es">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Landing Tailwind</title>
    <script src="https://cdn.tailwindcss.com"></script>
  </head>
  <body class="bg-gray-50 text-gray-800 font-sans flex flex-col min-h-screen">
    <header></header>
    <main class="flex-grow"></main>
    <footer></footer>
  </body>
</html>
```

**LEE:**  
Con solo esta línea, `<script src="https://cdn.tailwindcss.com">`, ya tienes todo el poder de Tailwind disponible.

**🎹 ESCRIBE:**  
Añade una línea de prueba:

```html
<p class="text-pink-500 text-2xl">Hola Tailwind</p>
```

**👁️ MUESTRA:**  
Navegador mostrando el texto "Hola Tailwind" en rosa.

**LEE:**  
Perfecto, Tailwind está funcionando.
`text-pink-500` define el color, y `text-2xl` el tamaño de fuente.

### 🔌 Extensión recomendada

**LEE:**  
Antes de continuar, te recomiendo instalar una extensión que te hará la vida mucho más fácil.
Se llama Tailwind CSS IntelliSense y te dará autocompletado, documentación en línea y vista previa de colores mientras escribes.

**👁️ MUESTRA:**  
Abre el panel de extensiones en VS Code (Ctrl/Cmd + Shift + X) y busca "Tailwind CSS IntelliSense".
O simplemente abre este enlace: `vscode:extension/bradlc.vscode-tailwindcss`

**LEE:**  
Con esta extensión, al escribir una clase verás sugerencias automáticas y la documentación sin salir del editor.

**🎹 ESCRIBE:**  
Para que la extensión funcione correctamente con el CDN, necesitamos crear un archivo de configuración mínimo.
Crea `tailwind.config.js` en la raíz del proyecto:

```js
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ["./*.html"],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

**LEE:**  
Este archivo le indica a la extensión dónde buscar las clases de Tailwind.
Ahora sí tendrás autocompletado completo mientras escribes.

### 🧭 Mostrar documentación oficial

**👁️ MUESTRA:**  
Abre <https://tailwindcss.com/docs>.

**LEE:**  
Si no recuerdas cómo se llama una clase, entra aquí, en la documentación oficial.
Por ejemplo, en Typography → Font Size verás todas las clases de tamaño, y en Colors las tonalidades disponibles.
No hace falta memorizar nada, solo saber buscar.

---

## 🕐 10:30 — Header y Hero

**LEE:**  
Vamos a empezar con la cabecera y la Hero section.
Primero, una barra de navegación fija arriba con sombra sutil.

**📋 PEGA:**

```html
<header class="sticky top-0 bg-white shadow-sm">
  <nav class="max-w-6xl mx-auto flex justify-between items-center p-4">
    <h1 class="text-2xl font-bold text-pink-500">TailPro</h1>
    <div class="flex items-center gap-6">
      <ul class="flex gap-6 text-gray-700 font-medium">
        <li><a href="#features" class="hover:text-pink-500">Features</a></li>
        <li><a href="#about" class="hover:text-pink-500">About</a></li>
        <li><a href="#contact" class="hover:text-pink-500">Contact</a></li>
      </ul>
    </div>
  </nav>
</header>
```

**LEE:**  
Cada clase hace algo concreto: `flex` alinea, `justify-between` separa, `p-4` añade espacio, `shadow-sm` añade sombra que da profundidad.

**👁️ MUESTRA:**  
Navegador con la barra visible.

### 🧭 Mostrar docs — Flexbox

**👁️ MUESTRA:**
Abre "Layout → Flexbox" en las docs.

**LEE:**  
Aquí puedes ver todas las variantes como `justify-between`, `items-center`, etc.
La documentación de Tailwind está llena de ejemplos prácticos.

### 🟣 Hero Section

**LEE:**  
La Hero section es la parte superior de la web, la primera impresión.
Aquí normalmente mostramos el mensaje principal, un título grande, un subtítulo y un botón de acción.
Su función es captar la atención y motivar al usuario a seguir explorando.

**📋 PEGA:**

```html
<section class="bg-gradient-to-r from-pink-500 to-purple-600 text-white text-center py-24 px-4">
  <h2 class="text-4xl md:text-6xl font-extrabold mb-4">Crea Interfaces Modernas</h2>
  <p class="text-lg md:text-xl mb-8 opacity-90">Aprende a diseñar con velocidad y precisión.</p>
  <a href="#features" class="bg-white text-pink-600 px-6 py-3 rounded-xl font-semibold hover:scale-105 transition">
    Empezar ahora
  </a>
</section>
```

**LEE:**  
Aquí usamos un gradiente con `bg-gradient-to-r` y clases responsive como `md:`.
Los prefijos como `md:` sirven para aplicar un estilo a partir de cierto tamaño de pantalla.
Por ejemplo, `md:text-6xl` significa que el texto será grande solo en pantallas medianas o superiores.
Recuerda que la buena práctica es trabajar siempre con un enfoque mobile first,
y luego ir añadiendo estilos para pantallas más grandes.

**👁️ MUESTRA:**  
Hero completo con gradiente y botón visible.

### 🧭 Mostrar docs — Gradientes

**👁️ MUESTRA:**  
Abre "Background Image → Gradient Color Stops".

**LEE:**  
Por ejemplo, `from-pink-500 to-purple-600` crea un degradado suave entre esos dos tonos.
Todo lo puedes combinar visualmente aquí.

---

## 🕐 20:30 — Sección de Features

**LEE:**  
Ahora practicaremos grid y sombras creando tres tarjetas de features.

**📋 PEGA:**

```html
<section id="features" class="max-w-6xl mx-auto py-16 px-4 grid md:grid-cols-3 gap-8">
  <div class="bg-white dark:bg-gray-800 p-6 rounded-2xl shadow-md hover:shadow-xl transition hover:-translate-y-1">
    <h3 class="text-xl font-bold text-pink-500 dark:text-pink-400 mb-2">Diseño rápido</h3>
    <p class="text-gray-600 dark:text-gray-300">Aplica estilos directamente en tus clases sin escribir CSS adicional.</p>
  </div>
  <div class="bg-white dark:bg-gray-800 p-6 rounded-2xl shadow-md hover:shadow-xl transition hover:-translate-y-1">
    <h3 class="text-xl font-bold text-pink-500 dark:text-pink-400 mb-2">Responsive total</h3>
    <p class="text-gray-600 dark:text-gray-300">Adapta tu diseño a cualquier dispositivo con utilidades prefijadas.</p>
  </div>
  <div class="bg-white dark:bg-gray-800 p-6 rounded-2xl shadow-md hover:shadow-xl transition hover:-translate-y-1">
    <h3 class="text-xl font-bold text-pink-500 dark:text-pink-400 mb-2">Modo oscuro</h3>
    <p class="text-gray-600 dark:text-gray-300">Activa fácilmente temas claros y oscuros según el sistema del usuario.</p>
  </div>
</section>
```

**LEE:**  
El grid organiza automáticamente las tarjetas, y con `hover:-translate-y-1` añadimos un pequeño movimiento al pasar el cursor.

**👁️ MUESTRA:**  
Navegador con las 3 cards visibles.

### 🧭 Mostrar docs — Grid & Shadow

**👁️ MUESTRA:**  
Abre "Grid Template Columns" y "Box Shadow".

**LEE:**  
Aquí puedes ver todas las combinaciones de columnas y sombras disponibles.
Si tienes dudas, la documentación te lo muestra visualmente.

**👁️ MUESTRA:**  
Abre <https://play.tailwindcss.com>.

**LEE:**  
Y si quieres experimentar rápido, usa Tailwind Play, un editor online que compila Tailwind al instante.

---

## 🕐 33:00 — CTA + Footer + Dark Mode

**LEE:**  
Vamos a cerrar la landing con una sección llamada CTA, o Call To Action.
Es el bloque final que busca convencer o motivar al usuario a hacer algo: suscribirse, contactar o probar un producto.
Visualmente debe destacar para atraer la atención.

**📋 PEGA:**

```html
<section class="text-center py-20 bg-gray-100 dark:bg-gray-800 transition">
  <h3 class="text-3xl font-bold mb-4 dark:text-gray-200">¿Listo para empezar?</h3>
  <button class="bg-pink-500 text-white px-8 py-3 rounded-full hover:bg-pink-600 transition">
    Únete hoy
  </button>
</section>

<footer class="bg-gray-900 text-gray-300 text-center py-6">
  <p>© 2025 TailPro. Todos los derechos reservados.</p>
</footer>
```

**🎹 ESCRIBE:**  
Antes de crear el botón, necesitamos configurar Tailwind para usar el modo oscuro manual.
En el `<head>`, después del CDN, añade:

```html
<script>
  tailwind.config = {
    darkMode: 'class'
  }
</script>
```

**LEE:**  
Esto le dice a Tailwind que active el modo oscuro cuando detecte la clase `dark` en el HTML.
Si estuvieras usando Vite, Next.js u otros frameworks, pondrías `darkMode: 'class'` directamente en el archivo `tailwind.config.js`.
Pero con el CDN necesitamos configurarlo así, inline.

**🎹 ESCRIBE:**  
Ahora sí, el botón del modo oscuro justo después de la `<ul>` del `<header>`:

```html
<button onclick="document.documentElement.classList.toggle('dark')"
  class="bg-gray-900 hover:bg-gray-700 text-white p-2 rounded-full transition">
  🌙
</button>
```

**👁️ MUESTRA:**  
Al hacer clic, el botón activa y desactiva el modo oscuro.

**LEE:**  
Perfecto. El botón añade o quita la clase `dark` al elemento HTML, y Tailwind aplica automáticamente todos los estilos `dark:` que hemos definido.

### 🧭 Mostrar docs — Dark Mode

**👁️ MUESTRA:**  
Abre "Dark Mode" en las docs.

**LEE:**  
Aquí puedes ver las estrategias disponibles: class y media.
Nosotros usamos class para controlarlo manualmente con un botón.

---

## 🕐 43:00 — Personalización con @theme

**LEE:**  
En Tailwind 4 podemos definir nuestro propio tema directamente en el HTML con `@theme`.
Así personalizamos colores fácilmente.

**📋 PEGA:**

```html
<script>
  tailwind.config = {
    darkMode: 'class',
    theme: {
      extend: {
        colors: {
          brand: '#3b82f6',
        }
      }
    }
  }
</script>
```

**🎹 ESCRIBE:**  
Aplica las nuevas variables en el hero:

```html
 <a href="#features" class="bg-brand text-white px-6 py-3 rounded-xl font-semibold hover:scale-105 transition hover:bg-white hover:text-brand hover:border-brand">
  Empezar ahora
</a>
```

**👁️ MUESTRA:**  
Hero actualizado con el color personalizado.

**LEE:**  
De esta forma creas tu identidad visual.

---

## 🕐 50:00 — Mostrar integración (no hacerla)

**LEE:**  
Si quieres usar Tailwind en un proyecto real, el proceso es casi igual.
Solo cambia la instalación según el entorno.

**👁️ MUESTRA:**  
Diapositiva o editor con:

### Vite

```bash
npm create vite@latest
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

### Next.js

```bash
npx create-next-app@latest
```

### Laravel

```bash
php artisan breeze:install
```

**LEE:**  
En todos los casos, solo hay que importar las directivas `@tailwind base;`, `@tailwind components;` y `@tailwind utilities;` en tu CSS.
Y si quieres personalizar colores o fuentes, lo haces en el archivo CSS, no con script inline como hemos hecho aquí con el CDN.

---

## 🕐 54:00 — Cierre y reto

**LEE:**  
Y así, en menos de una hora, hemos creado una web moderna, responsive, con modo oscuro y un tema personalizado.
Lo más importante: ahora sabes cómo buscar, combinar y entender las clases de Tailwind.

Te dejo un reto:
Duplica esta web, cambia la paleta y la tipografía para crear tu propia marca personal.

**👁️ MUESTRA:**  
Scroll completo de la landing terminada.

**👁️ MUESTRA:**  
Links en pantalla:

- <https://tailwindcss.com/docs>
- <https://play.tailwindcss.com>
- <https://tailwindcomponents.com>

**LEE:**
Perfecto. Hoy has aprendido lo más importante: cómo buscar, cómo combinar clases, y cómo personalizar tu diseño.
No necesitas memorizar nada, solo entender el sistema.

Soy Oriol Cortes, gracias por acompañarme.
Nos vemos en la próxima. ¡Recuerda el mantra de Tailwind: diseña más, escribe menos!
