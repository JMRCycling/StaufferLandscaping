# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## Project Overview

This is a static website for Stauffer Landscaping, built with vanilla HTML, CSS, and JavaScript (no build tools or frameworks). The site is a single-page application with smooth scrolling navigation between sections.

## Development Commands

### Running the Development Server

```bash
# Using Python 3 (recommended)
python -m http.server 8000

# Using Node.js http-server
npx http-server
```

After starting the server, navigate to `http://localhost:8000` in your browser.

### Viewing the Site

You can also simply open `index.html` directly in a browser for quick viewing, though using a local server is recommended for testing.

## Architecture

### File Structure

- `index.html` - Single-page site with all sections (hero, services, about, gallery, contact)
- `css/styles.css` - All styling including responsive design
- `js/script.js` - All interactive functionality (mobile menu, form handling, scroll animations)
- `images/` - Directory for project images (currently uses placeholder divs)

### Key Architectural Patterns

**CSS Architecture:**
- Uses CSS custom properties (variables) defined in `:root` for theming
- Mobile-first responsive design with breakpoints at 768px and 480px
- Semantic class naming (e.g., `.service-card`, `.hero-content`, `.contact-form`)
- CSS Grid for layout (services grid, gallery grid, about/contact sections)
- Flexbox for navigation and smaller components

**JavaScript Architecture:**
- No external dependencies - all vanilla JavaScript
- Event-driven interactions (mobile menu toggle, form submission, scroll events)
- Intersection Observer API for scroll-based fade-in animations on `.service-card` and `.gallery-item` elements
- Modular approach with clear sections for each feature (mobile menu, smooth scroll, form handling, scroll animations)

**HTML Structure:**
- Semantic HTML5 elements (`<header>`, `<nav>`, `<main>`, `<section>`, `<footer>`)
- Each major section has an `id` attribute for anchor navigation (#home, #services, #about, #gallery, #contact)
- Sticky navigation header with `position: sticky`
- Form uses client-side validation with `required` attributes

### Color Theming

All colors are defined as CSS custom properties in `css/styles.css`:

```css
:root {
    --primary-color: #2d7a3e;      /* Main green */
    --primary-dark: #1f5c2e;       /* Darker green */
    --secondary-color: #7fb800;    /* Accent green */
    --text-dark: #333;             /* Main text */
    --text-light: #666;            /* Secondary text */
}
```

When changing colors, update these variables in the `:root` selector.

### Responsive Behavior

- **Desktop (>768px):** Horizontal navigation menu, multi-column grid layouts
- **Tablet/Mobile (≤768px):** Hamburger menu, single-column layouts for about/contact/services
- **Small Mobile (≤480px):** Reduced font sizes and padding

The mobile menu is hidden by default and toggled with the `.active` class (handled in `js/script.js`).

### Form Handling

The contact form (`#contactForm`) currently:
- Prevents default submission and logs data to console
- Shows a fixed-position success modal for 3 seconds
- Resets the form after submission

**To integrate with a backend:** Modify the submit event handler in `js/script.js` (lines 54-98) to send form data via `fetch()` or another method.

### Image Integration

The site currently uses `.placeholder-image` divs (colored boxes with gradient backgrounds) instead of real images. To add actual images:

1. Place images in the `images/` directory
2. Replace `.placeholder-image` divs with `<img>` tags:
   ```html
   <img src="images/your-image.jpg" alt="Description">
   ```

### Animation System

Scroll-based animations use Intersection Observer:
- Elements with `.service-card` or `.gallery-item` classes automatically get fade-in animations
- Initial state: `opacity: 0`, `transform: translateY(20px)`
- When in viewport: `opacity: 1`, `transform: translateY(0)`
- To add animations to new elements, include them in the `animatedElements` query selector (line 117 in `js/script.js`)

## Development Guidelines

### Adding New Sections

When adding new sections to the page:
1. Add the section to `index.html` with an `id` attribute
2. Add a corresponding navigation link in the `.nav-menu` and footer
3. Style the section in `css/styles.css`
4. If the section needs scroll animations, add its class to the observer in `js/script.js`

### Modifying Navigation

The navigation highlight-on-scroll feature requires:
- Section elements must have an `id` attribute
- Navigation links must have `href="#section-id"` format
- The scroll listener (lines 128-146 in `js/script.js`) will automatically highlight the active link

### Smooth Scrolling

All anchor links with `href^="#"` automatically get smooth scrolling with an 80px header offset. The offset accounts for the sticky header height - adjust this value in `js/script.js` (line 39) if you change header height.
