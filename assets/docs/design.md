# Portfolio CSS Style Guide

## Global Settings

- **Font**: "Outfit", sans-serif
- **Box-sizing**: `border-box` for all elements to simplify padding and margin calculations.
- **Margin & Padding**: Reset `margin: 0` and `padding: 0` for all elements to maintain consistency across browsers.

## Color Scheme

### Light Mode (Default)

- **Background**: `#ffffff` (white)
- **Primary Text**: `#1a1a1a` (dark gray for readability)
- **Accent Color**: `#e91e63` (vibrant pink)
- **Hover Color**: `#c2185b` (darker pink for hover effects)

### Dark Mode

- **Background**: `#121212` (dark background for dark mode)
- **Primary Text**: `#e0e0e0` (light text for contrast)
- **Link Color**: `#ff4081` (bright pink for links)
- **Button Background**: `#333333` (dark button background)
- **Button Hover**: `#ff4081` (highlight button color on hover)

## Layout

### Navbar

- **Positioning**: Fixed navbar with a shadow effect for contrast.
- **Links**: Responsive, inline for desktop, vertical for mobile.
- **Mobile Menu**: Hidden by default, toggled via a button (`#menu-toggle`).

### Hero Section

- **Alignment**: Centered content for a clean layout.
- **Padding**: Generous padding for visual emphasis (`100px 20px`).
- **Buttons**: Large, bold buttons with hover effects to attract user interaction.

### Skills Section

- **Flexbox Layout**: Use `flex-wrap` and `justify-content` to ensure skills are displayed responsively.
- **Skill Background**: Use consistent background color for each skill label, changing color on hover.
- **Font Size**: Use bold, readable font sizes for skills (`1rem`).

### Projects Section

- **Cards**: Fixed width project cards that grow on hover (`scale(1.05)` effect).
- **Image Sizing**: Ensure images are responsive, covering the full width within the card without distortion.

### Footer

- **Social Links**: Centered with hover effects.
- **Background**: Matches the section background, with a slight shadow at the top.

## Responsiveness

- **Mobile First Design**: Always start with mobile styles, then use media queries for larger screens (e.g., `@media (max-width: 768px)`).
- **Fluid Layouts**: Use relative units (`%`, `em`, `rem`) rather than fixed pixel widths to ensure responsive behavior across all screen sizes.

## Dark Mode Toggle

- **Dark Mode**: Apply `.dark-mode` class to the body when dark mode is enabled.
- **Local Storage**: Store theme preference in `localStorage` to persist the dark mode state across page reloads.
- **Toggle Button**: Change the button emoji from 🌙 (moon) to 🌞 (sun) when dark mode is activated.
