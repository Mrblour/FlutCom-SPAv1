# ⚡ Flutcom: Framework SPAV "Vanilla"

> **Arquitectura ligera sin dependencias.** Vanilla JS puro, enrutamiento Hash y renderizado directo. Ideal para entender cómo funcionan las SPAs por dentro o para proyectos que requieren máximo rendimiento con cero overhead.

![Flutcom Banner](resources/img/banner-placeholder.png)

## 🚀 ¿Por qué Flutcom?

En un mundo dominado por React, Vue y Angular, **Flutcom** es un experimento y una declaración de intenciones: **No siempre necesitas un Virtual DOM.**

*   **0 Dependencias de Runtime:** El núcleo es 100% JavaScript nativo.
*   **Rendimiento Absurdo:** Sin hidratación, sin diffing complejo. Solo DOM real.
*   **Tailwind CSS v4:** Integrado nativamente para el estilizado.
*   **Enrutamiento Hash:** Simple, robusto y compatible con cualquier hosting estático (GitHub Pages, Vercel, Netlify) sin configuración de servidor.

---

## 🛠️ Instalación y Uso

### Prerrequisitos
*   Node.js (solo para el entorno de desarrollo y compilación de Tailwind).

### 1. Clonar el repositorio
```bash
git clone https://github.com/tu-usuario/flutcom.git
cd flutcom
```

### 2. Instalar dependencias
```bash
npm install
```

### 3. Iniciar entorno de desarrollo
Esto iniciará el compilador de Tailwind en modo "watch" y un servidor local.
```bash
npm run dev
```
Abre tu navegador en `http://localhost:8080` (o el puerto que te indique).

---

## 📂 Estructura del Proyecto

La arquitectura está diseñada para ser intuitiva y escalable:

```text
/
├── assets/
│   ├── css/           # Estilos compilados y fuentes
│   └── img/           # Imágenes estáticas
├── config/
│   ├── core.js        # 🧠 El Cerebro: Router y Loader (No tocar)
│   ├── main.js        # 🎮 La App: Configuración y lógica de negocio
│   └── routes.js      # 🗺️ Mapa de rutas y parciales
├── resources/
│   ├── components/    # Fragmentos reutilizables (Cards, Botones)
│   ├── layouts/       # Estructura base (HTML shell)
│   ├── partials/      # Elementos fijos (Header, Footer)
│   └── views/         # Páginas completas (Home, Pricing, Docs)
└── index.html         # Punto de entrada único
```

---

## 🧑‍💻 Cómo crear una nueva página

### 1. Crear el archivo HTML
Crea un archivo en `resources/views/public/mi-pagina.html`:
```html
<section class="pt-32 px-6 max-w-4xl mx-auto">
    <h1 class="text-4xl font-bold text-white">Mi Nueva Página</h1>
    <p class="text-zinc-400 mt-4">Creada con Flutcom.</p>
</section>
```

### 2. Registrar la ruta
Abre `config/routes.js` y añade tu nueva ruta:
```javascript
export const navRoutes = {
  home: "resources/views/public/home.html",
  nueva: "resources/views/public/mi-pagina.html" // <--- Nueva ruta
};
```

### 3. ¡Listo!
Ahora puedes acceder navegando a `index.html#nueva`.

---

## 🎨 Personalización

### Estilos (Tailwind CSS)
Edita `src/input.css` para agregar fuentes o estilos globales. Tailwind detectará automáticamente tus clases en los archivos HTML dentro de `resources/`.

### Lógica Global
Si necesitas scripts que corran en toda la app (analytics, estado global), agrégalos en `config/main.js`.

---

## 📚 Documentación Avanzada

*   [**Core vs Main:**](./explicacion_core_vs_main.md) Entiende la diferencia entre el framework y tu aplicación.
*   [**Guía de Escalabilidad:**](./guia_escalabilidad_estatica.md) Cómo construir sitios gigantes sin backend.

---

## 🤝 Contribuir

Este es un proyecto de código abierto. ¡Las PRs son bienvenidas!
Si encuentras un bug o tienes una idea, abre un Issue.

## 📄 Licencia

MIT © 2025 Flutcom

