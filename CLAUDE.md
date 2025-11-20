# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**CO3 Website** - Sitio web corporativo para CO3, empresa especializada en inteligencia aplicada a arquitectura y construcción. El sitio presenta servicios de desarrollo BIM, automatización de procesos, integración de IA, y modernización tecnológica.

**GitHub Repository**: https://github.com/nolo-11/CO3-website

## Technology Stack

- **Static HTML/CSS/JavaScript**: No build system or frameworks
- **Language**: Spanish (es)
- **Theme**: Dark theme with black backgrounds and gold accents
- **Fonts**: Inter (Google Fonts), Font Awesome 6.4.0
- **Assets**:
  - `images/CO3_LOGO.png` - Logo completo
  - `images/CO3_LOGO_SIMPLIFICADO.png` - Logo simplificado

## Current Status

### ✅ Implemented Features
- Página completa con secciones: Inicio, Servicios, Beneficios, Promesa, Contacto
- Tema oscuro implementado con colores dorados
- Navegación responsive con menú móvil funcionando correctamente
- Animaciones de hover con glow dorado
- Smooth scrolling entre secciones
- Repository conectado a GitHub

### 🔄 Pending Changes
- [ ] Agregar sección "Tecnologías" después de Servicios
- [ ] Integrar logo en la navegación
- [ ] Mostrar tecnologías específicas de CO3

## Design System

### Color Scheme (Dark Theme)
- **Background**: `#000000` (Pure black)
- **Primary Gold**: `#e0ceb6` - Main brand color for accents and highlights
- **Secondary Gold**: `#c4b5a0` - Supporting brand color
- **Accent**: `#f0dcc4` - Lighter accent for gradients
- **Secondary Backgrounds**: `#1a1a1a`, `#2a2a2a`
- **Text Primary**: `#ffffff`
- **Text Secondary**: `#b0b0b0`
- **Borders**: `rgba(224, 206, 182, 0.3)` - Subtle golden borders
- **Glow Effect**: `0 0 20px rgba(224, 206, 182, 0.3)` - Golden glow on hover

### Design Patterns
- **Cards**: Dark background with golden border, hover effect with glow
- **Icons**: Font Awesome icons with golden gradient
- **Transitions**: Smooth (`all 0.3s cubic-bezier(0.4, 0, 0.2, 1)`)
- **Hover Effects**: `translateY(-5px)` with enhanced box-shadow and glow

### Layout
- **Container**: max-width 1200px
- **Responsive breakpoints**: 480px, 768px, 1024px, 1440px, 1920px
- **Spacing**: rem-based (0.5rem to 6rem)
- **Grid patterns**: `repeat(auto-fit, minmax(Xpx, 1fr))`

## Technologies to Showcase

When implementing the "Tecnologías" section, include the following categories:

### Lenguajes de Programación
- Python
- C#
- Dynamo (visual programming)
- Grasshopper (visual programming)

### Software BIM
- Revit
- AutoCAD
- Navisworks

### Desarrollo de Software
- Apps Móviles
- Apps Web
- Bases de Datos

### Inteligencia Artificial
- Machine Learning
- Dashboards Inteligentes
- Excel Avanzado con automatización

## File Structure

```
/
├── index.html              # Main HTML file
├── style.css              # Main styles (dark theme)
├── responsive.css         # Responsive breakpoints
├── main.js               # Vanilla JavaScript
├── images/
│   ├── CO3_LOGO.png
│   └── CO3_LOGO_SIMPLIFICADO.png
└── CLAUDE.md            # This file
```

## Development Commands

Static website - no build process required:

```bash
# Open in browser
xdg-open index.html

# Or serve locally with Python
python3 -m http.server 8000
# Then visit: http://localhost:8000
```

## JavaScript Features (main.js)

1. **Mobile Navigation**: Hamburger menu toggle
2. **Smooth Scrolling**: Native smooth scroll for anchor links
3. **Navbar Effects**: Background opacity/shadow changes on scroll
4. **Intersection Observer**: Fade-in animations for `.service-card`, `.benefit-item`
5. **Button Ripple Effects**: Dynamic golden ripple on click
6. **Keyboard Navigation**: Escape key closes mobile menu
7. **Focus Management**: Accessible focus indicators

## Key Sections in HTML

### Current Structure
1. **Hero** (`#inicio`): index.html:51-71
2. **Services** (`#servicios`): index.html:74-162
3. **Benefits** (`#beneficios`): index.html:165-238
4. **Promise**: index.html:241-248
5. **Contact** (`#contacto`): index.html:251-286
6. **Footer**: index.html:289-307

### Section to Add
- **Technologies** (`#tecnologias`): Should be inserted after Services section (after line 162)

## Styling Guidelines

When creating new sections (like "Tecnologías"):

### Card Structure
```css
.tech-card {
    background: var(--bg-secondary);        /* #1a1a1a */
    border: 1px solid var(--border-color);  /* #333333 */
    border-radius: var(--radius-lg);        /* 1rem */
    padding: 2.5rem;
    transition: var(--transition);
}

.tech-card:hover {
    transform: translateY(-5px);
    box-shadow: var(--shadow-xl), var(--shadow-glow);
    border-color: rgba(224, 206, 182, 0.5);
}
```

### Icon Styling
```css
.tech-icon {
    background: linear-gradient(135deg, rgba(224, 206, 182, 0.2), rgba(196, 181, 160, 0.1));
    border: 2px solid rgba(224, 206, 182, 0.3);
}

.tech-icon i {
    background: linear-gradient(135deg, var(--primary-color), var(--accent-color));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
}
```

## CSS Custom Properties

All CSS variables are defined in `style.css:4-24`:
- `--primary-color`: #e0ceb6
- `--secondary-color`: #c4b5a0
- `--accent-color`: #f0dcc4
- `--bg-primary`: #000000
- `--bg-secondary`: #1a1a1a
- `--shadow-glow`: 0 0 20px rgba(224, 206, 182, 0.3)
- `--transition`: all 0.3s cubic-bezier(0.4, 0, 0.2, 1)

## Contact Information

- **Email**: administrador@co3.com
- **Phone**: +57 (301) 786-4636
- **Availability**: Global

## Accessibility Features

- High contrast mode support
- Reduced motion support
- Keyboard navigation
- Focus indicators
- Print styles
- Semantic HTML structure

## Common Tasks

### Adding the Technologies Section
1. Insert new section in `index.html` after line 162
2. Use same structure as Services section with grid layout
3. Create 4 category cards (Lenguajes, Software BIM, Desarrollo, IA)
4. Add Font Awesome icons for each technology
5. Apply hover effects with golden glow
6. Update navigation to include `#tecnologias` link if needed
7. Ensure Intersection Observer picks up new `.tech-card` elements

### Updating Navigation Logo
1. Logo image is at `images/CO3_LOGO_SIMPLIFICADO.png`
2. Current nav logo structure is in `index.html:21-27`
3. Image already integrated, adjust sizing if needed in `style.css:135-139`

### Modifying Colors
- All color variables are in `:root` selector in `style.css`
- Golden color scheme: #e0ceb6 (primary), #c4b5a0 (secondary), #f0dcc4 (accent)
- Background must remain pure black (#000000) for brand consistency

## Git Workflow

```bash
# Current branch
git branch  # should show: main

# Standard workflow
git add .
git commit -m "mensaje descriptivo"
git push origin main
```

## Notes

- No package.json or dependencies - pure vanilla stack
- All resources via CDN (Google Fonts, Font Awesome)
- Spanish language throughout
- Mobile-first responsive design
- WSL development environment
