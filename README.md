# Estructura Modular del Proyecto Apunti

Este proyecto ha sido reorganizado para usar componentes reutilizables y CSS separado.

## Estructura de Archivos

```
├── home.html                    # Página principal (ahora sin CSS inline ni header/footer hardcoded)
├── css/
│   └── styles.css              # Todos los estilos CSS (variables, componentes, responsive)
├── components/
│   ├── header.html             # Componente del header/navegación
│   └── footer.html             # Componente del footer
├── js/
│   └── components-loader.js    # Script para cargar componentes automáticamente
└── README.md                   # Este archivo
```

## Características

### CSS Modular (`css/styles.css`)
- **Variables CSS**: Colores principales, sombras, etc.
- **Estilos base**: Body, fuentes, gradientes de fondo
- **Componentes**: Header, hero, cards, footer, etc.
- **Responsive**: Media queries para diferentes tamaños de pantalla

### Componentes Reutilizables
- **Header** (`components/header.html`): Navegación principal con logo y menú
- **Footer** (`components/footer.html`): Pie de página con links y información

### Carga Automática
- Los componentes se cargan automáticamente via JavaScript
- No requiere servidor web especial, funciona con archivos estáticos
- Fácil de mantener y actualizar

## Cómo Usar en Otras Páginas

### 1. Incluir los archivos necesarios en el `<head>`:
```html
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet">
<link href="css/styles.css" rel="stylesheet">
```

### 2. Agregar placeholders para header y footer:
```html
<body>
  <!-- HEADER -->
  <div id="header-placeholder"></div>
  
  <!-- Tu contenido aquí -->
  
  <!-- FOOTER -->  
  <div id="footer-placeholder"></div>
</body>
```

### 3. Incluir los scripts antes del cierre de `</body>`:
```html
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"></script>
<script src="js/components-loader.js"></script>
```

## Beneficios

✅ **Reutilización**: Header y footer se pueden usar en múltiples páginas
✅ **Mantenimiento**: Cambios en header/footer se reflejan en todas las páginas
✅ **Organización**: CSS separado es más fácil de mantener
✅ **Performance**: CSS externo se cachea en el navegador
✅ **Escalabilidad**: Fácil agregar nuevos componentes

## Alternativas de Implementación

Si necesitas usar un framework específico, los componentes se pueden adaptar fácilmente:

- **PHP**: Usar `include()` o `require()`
- **Node.js/Express**: Usar template engines como EJS o Handlebars
- **React**: Convertir a componentes JSX
- **Vue.js**: Convertir a componentes .vue
- **Server Side Includes**: Usar `<!--#include virtual="..." -->`

## Desarrollo Local

Para desarrollo local, necesitas servir los archivos desde un servidor web (no abrir directamente en el navegador) para que funcione el fetch de componentes. Opciones:

- **Python**: `python -m http.server 8000`
- **Node.js**: `npx serve .`
- **PHP**: `php -S localhost:8000`
- **Live Server** (VS Code extension)