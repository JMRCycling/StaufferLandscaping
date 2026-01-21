# GreenScape Landscaping Website

A modern, responsive website for a professional landscaping service company. This project features a clean design with smooth animations, mobile-friendly navigation, and an interactive contact form.

## Features

- **Responsive Design**: Fully responsive layout that works seamlessly on desktop, tablet, and mobile devices
- **Modern UI**: Clean, professional design with smooth animations and transitions
- **Service Showcase**: Dedicated section highlighting six core landscaping services
- **Interactive Gallery**: Project showcase with hover effects
- **Contact Form**: Functional contact form with client-side validation and success feedback
- **Mobile Navigation**: Hamburger menu with smooth animations for mobile users
- **Smooth Scrolling**: Enhanced user experience with smooth scroll navigation
- **SEO Optimized**: Semantic HTML structure with proper meta tags

## Project Structure

```
landscaping-website/
├── index.html          # Main HTML file
├── css/
│   └── styles.css      # All styles and responsive design
├── js/
│   └── script.js       # Interactive functionality
├── images/             # Placeholder for project images
└── README.md           # Project documentation
```

## Technologies Used

- **HTML5**: Semantic markup for better accessibility and SEO
- **CSS3**: Modern styling with CSS Grid, Flexbox, and custom properties
- **Vanilla JavaScript**: No dependencies - pure JavaScript for all interactions

## Getting Started

### Prerequisites

No special software is required. You just need a modern web browser to view the website.

### Installation

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd landscaping-website
   ```

2. Open the website:
   - Simply open `index.html` in your web browser
   - Or use a local development server (recommended):
     ```bash
     # Using Python 3
     python -m http.server 8000
     
     # Using Node.js (http-server)
     npx http-server
     ```

3. View in browser:
   - Navigate to `http://localhost:8000` (or the appropriate port)

## Customization

### Colors

The color scheme can be easily customized by modifying CSS custom properties in `css/styles.css`:

```css
:root {
    --primary-color: #2d7a3e;      /* Main green color */
    --primary-dark: #1f5c2e;       /* Darker green */
    --secondary-color: #7fb800;    /* Accent color */
    --text-dark: #333;             /* Main text color */
    --text-light: #666;            /* Secondary text */
}
```

### Content

- **Company Name**: Update "GreenScape" in `index.html`
- **Contact Information**: Modify the contact section with your actual phone, email, and address
- **Services**: Edit service cards in the services section
- **About Section**: Customize the company description and features

### Images

Replace placeholder images by:
1. Adding your images to the `images/` directory
2. Updating the `.placeholder-image` divs with actual `<img>` tags:
   ```html
   <img src="images/your-image.jpg" alt="Description">
   ```

## Features in Detail

### Mobile Navigation

- Hamburger menu automatically appears on screens smaller than 768px
- Smooth animations when opening/closing the menu
- Menu closes automatically when a link is clicked

### Contact Form

- Client-side form validation
- Success message appears on submission
- Form data is logged to console (ready for backend integration)
- Easy to connect to a backend API or email service

### Smooth Scrolling

- Navigation links smoothly scroll to their target sections
- Proper offset to account for the sticky header

### Scroll Animations

- Service cards and gallery items fade in as they enter the viewport
- Intersection Observer API for efficient scroll detection

## Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## Future Enhancements

Potential improvements for future versions:

- [ ] Connect contact form to a backend API or email service
- [ ] Add a lightbox/modal for the gallery images
- [ ] Implement a testimonials slider
- [ ] Add Google Maps integration for the location
- [ ] Create an admin panel for content management
- [ ] Add a blog section for landscaping tips
- [ ] Integrate with a booking/scheduling system

## License

This project is open source and available for personal and commercial use.

## Contact

For questions or customization requests, please use the contact form on the website or reach out directly.

---

**Built with ❤️ for professional landscaping businesses**
