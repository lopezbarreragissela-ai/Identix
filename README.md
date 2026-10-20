# 📐 IdentiX

**Laboratorio interactivo de identidades trigonométricas para grado 10°.**

IdentiX es una aplicación web educativa (HTML + CSS + JavaScript, en un solo archivo) que enseña las identidades trigonométricas pitagóricas, recíprocas y de cociente mediante teoría, ejemplos resueltos, práctica interactiva, álgebra simbólica y juegos.

> Recurso educativo original. Toma como referencia únicamente la estructura de interacción de simuladores tipo *MathXR Fusion EDU*; el contenido, los datos y los ejercicios son propios.

---

## 🎯 Objetivo didáctico

Al finalizar, el estudiante de grado 10° podrá **identificar, comprobar y simplificar** identidades trigonométricas, relacionando el valor numérico de cada razón con su representación gráfica en el círculo trigonométrico y con el triángulo rectángulo.

## ✨ Características

| Sección | Qué incluye |
|---|---|
| 📘 **Explicar el tema** | Teoría de las 3 familias de identidades, círculo trigonométrico con triángulo rectángulo que se actualiza en vivo (panel lateral fijo) y panel desplegable de **Practicar**. |
| 🧪 **Practicar** (dentro de Explicar) | Controles de ángulo (0°–360°), identidad, dificultad, razón trigonométrica y tipo de ejercicio; cálculos en tiempo real; gráfica comparativa con Plotly; reto de predicción; retroalimentación; evidencia final exportable. |
| 📝 **Ejemplos paso a paso** | 6 ejemplos resueltos y explicados (2 por tipo de identidad). |
| 🧮 **Álgebra con identidades** | Despeje, factorización y simplificación con fracciones; cada caso inicia con un ejemplo que señala el **error común** y el procedimiento correcto, seguido de ejercicios largos con solución paso a paso. |
| 🧩 **Casos generales** | Ejercicios simbólicos sin datos numéricos (válidos para cualquier θ). |
| 💡 **Truquitos** | Mnemotecnias y errores frecuentes. |
| 🎮 **Juegos** | Quiz relámpago, Verdadero/Falso y Memorama, cada uno a **pantalla completa**, con botón *Salir* y cambio rápido entre juegos. |

Además: portada con logo y muñecos flotantes, compañero flotante con consejos por sección, transición de "ola" entre pantallas y fondo en degradado.

## 🧰 Tecnologías

- HTML5, CSS3 y JavaScript (vanilla), sin paso de compilación.
- [Plotly.js](https://plotly.com/javascript/) 2.32.0 (gráfica comparativa).
- [math.js](https://mathjs.org/) 12.4.2 (incluida para ampliaciones de cálculo).
- Fuentes del sistema (`Segoe UI`, `Arial`); sin dependencias de fuentes externas.

Plotly y math.js se cargan desde `cdnjs.cloudflare.com`, por lo que se necesita conexión a internet la primera vez.

## 🚀 Cómo usarlo

### Opción 1: abrirlo localmente
1. Descarga `identix.html`.
2. Ábrelo con cualquier navegador moderno (Chrome, Edge, Firefox, Safari).

### Opción 2: publicarlo con GitHub Pages
1. Sube `identix.html` al repositorio (puedes renombrarlo a `index.html`).
2. Ve a **Settings → Pages**.
3. En *Source* elige la rama `main` y la carpeta `/ (root)`.
4. Tu app quedará en `https://TU-USUARIO.github.io/NOMBRE-REPO/`.

## ♿ Accesibilidad y diseño

- Paleta de alto contraste: azul brillante, verde, naranja y blanco.
- Todos los controles tienen etiquetas, foco visible y navegación por teclado.
- La gráfica y el círculo incluyen descripciones (`aria-label`) y una tabla de valores como alternativa textual.
- Respeta `prefers-reduced-motion` (se desactivan animaciones y la ola de transición).
- Diseño responsive: en pantallas angostas el menú lateral pasa a barra superior y los paneles se apilan.
- No usa RA/RV ni cámara: el círculo 2D comunica las identidades con la misma claridad y funciona en cualquier dispositivo.

## 🗂️ Estructura del proyecto

```
identix.html   ← app completa (HTML + CSS + JS en un solo archivo)
README.md
```

Dentro de `identix.html` el código está organizado así: estilos (`<style>`), portada/sidebar/pestañas (HTML), y un único bloque `<script>` con secciones comentadas (cálculos, círculo, gráfica, predicción, banco de ejercicios, álgebra, juegos, navegación).

## 🔧 Adaptación rápida

- **Más ejercicios de Practicar:** edita el objeto `BANCO` en el script (por identidad y dificultad).
- **Más preguntas de juegos:** amplía `BANCO_QUIZ`, `BANCO_VF` o `PARES_MEMO`.
- **Más ejercicios de álgebra:** copia un bloque `.alg-ejercicio` en `tab-algebra` o `tab-general`; el botón *Comprobar* usa los atributos `data-tipo`, `data-resp` y `data-alt` (variantes de respuesta separadas por `|`).
- **Colores:** cambia las variables `--azul`, `--verde`, `--naranja` en `:root`.
- **Otro grado o tema:** ajusta los textos de las pestañas y los bancos de ejercicios.

## 📤 Exportación de evidencia

El botón **Exportar evidencia** genera un resumen (correctas, intentos, precisión y detalle por ejercicio) en JSON. El progreso se guarda además en `localStorage` del navegador.

> ⚠️ El botón de descarga está escrito para el entorno donde se publicó originalmente la app (usa `window.claude.use("downloads")`). Si lo alojas por tu cuenta (GitHub Pages, servidor propio), esa capacidad no existe y la app muestra el JSON en pantalla para copiarlo. Para tener descarga real, reemplaza el manejador de `exportBtn` por un `Blob` + enlace `download`:
>
> ```js
> const blob = new Blob([texto], {type: "application/json"});
> const a = document.createElement("a");
> a.href = URL.createObjectURL(blob);
> a.download = "identix_evidencia.json";
> a.click();
> ```

## 🗺️ Ideas para ampliar

- Más cuadrantes y signos de las razones en el círculo.
- Modo profesor con banco de ejercicios en JSON externo.
- Generación aleatoria de ejercicios algebraicos con verificación simbólica (math.js).
- Versión 3D/RA del círculo trigonométrico, siempre con alternativa sin cámara ni visor.

## 📄 Licencia

Elige la licencia que prefieras para tu repositorio (por ejemplo MIT o CC BY-NC-SA 4.0 para uso educativo) y agrega el archivo `LICENSE`.

---

Hecho con 💙 para aprender trigonometría jugando.
