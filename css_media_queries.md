# 20 CSS Media Query Examples

## Basic Level (Used Very Frequently - Daily/Weekly)

### 1. Mobile-First Responsive Design
```css
/* Mobile styles by default */
.container {
  width: 100%;
  padding: 10px;
}

/* Tablet and up */
@media (min-width: 768px) {
  .container {
    width: 750px;
    margin: 0 auto;
  }
}
```
**Use Case:** Standard responsive breakpoint for mobile-first design.

### 2. Desktop Breakpoint
```css
@media (min-width: 1024px) {
  .header {
    display: flex;
    justify-content: space-between;
  }
  
  .nav-menu {
    display: block;
  }
}
```
**Use Case:** Common desktop breakpoint for navigation and layout changes.

### 3. Hide Elements on Mobile
```css
@media (max-width: 767px) {
  .desktop-only {
    display: none;
  }
}
```
**Use Case:** Hide complex elements on smaller screens.

### 4. Portrait vs Landscape Orientation
```css
@media (orientation: portrait) {
  .gallery {
    grid-template-columns: 1fr;
  }
}

@media (orientation: landscape) {
  .gallery {
    grid-template-columns: repeat(2, 1fr);
  }
}
```
**Use Case:** Adjust layouts based on device orientation.

### 5. Print Styles
```css
@media print {
  .no-print {
    display: none;
  }
  
  body {
    font-size: 12pt;
    color: black;
    background: white;
  }
}
```
**Use Case:** Optimize page appearance for printing.

### 6. Large Desktop Screens
```css
@media (min-width: 1440px) {
  .container {
    max-width: 1200px;
  }
  
  .hero-text {
    font-size: 4rem;
  }
}
```
**Use Case:** Enhance experience on large monitors.

## Intermediate Level (Used Regularly - Weekly/Monthly)

### 7. High DPI/Retina Displays
```css
@media (-webkit-min-device-pixel-ratio: 2), 
       (min-resolution: 192dpi) {
  .logo {
    background-image: url('logo@2x.png');
    background-size: 100px 50px;
  }
}
```
**Use Case:** Serve high-resolution images for crisp display on retina screens.

### 8. Dark Mode Preference
```css
@media (prefers-color-scheme: dark) {
  body {
    background-color: #1a1a1a;
    color: #ffffff;
  }
  
  .card {
    background-color: #2d2d2d;
    border-color: #444;
  }
}
```
**Use Case:** Respect user's system dark mode preference.

### 9. Reduced Motion Preference
```css
@media (prefers-reduced-motion: reduce) {
  * {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}
```
**Use Case:** Accessibility - reduce animations for users with motion sensitivity.

### 10. NOT Condition - Exclude Touch Devices
```css
@media not all and (pointer: coarse) {
  .hover-effect:hover {
    transform: scale(1.05);
    box-shadow: 0 10px 20px rgba(0,0,0,0.2);
  }
}
```
**Use Case:** Apply hover effects only on devices with precise pointers (not touch).

### 11. Medium Screen Range
```css
@media (min-width: 768px) and (max-width: 1023px) {
  .sidebar {
    width: 200px;
  }
  
  .main-content {
    margin-left: 200px;
  }
}
```
**Use Case:** Target specific tablet/small laptop screen range.

### 12. Screen Type Only
```css
@media screen and (max-width: 600px) {
  .mobile-nav {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
  }
}
```
**Use Case:** Apply styles only to screen displays, not print.

## Advanced Level (Used Occasionally - Monthly/Rarely)

### 13. Multiple Conditions with NOT
```css
@media not screen and (min-width: 1024px), 
       not (orientation: landscape) {
  .complex-layout {
    flex-direction: column;
  }
}
```
**Use Case:** Complex logic for specific layout requirements.

### 14. Aspect Ratio Detection
```css
@media (aspect-ratio: 16/9) {
  .video-container {
    height: 56.25vw; /* 16:9 aspect ratio */
  }
}

@media (min-aspect-ratio: 1/1) {
  .square-optimized {
    display: grid;
    grid-template-columns: 1fr 1fr;
  }
}
```
**Use Case:** Optimize layouts for specific screen proportions.

### 15. Feature Detection - Hover Capability
```css
@media (hover: hover) and (pointer: fine) {
  .interactive-element {
    cursor: pointer;
  }
  
  .interactive-element:hover {
    background-color: #f0f0f0;
  }
}

@media (hover: none) {
  .interactive-element {
    padding: 15px; /* Larger touch targets */
  }
}
```
**Use Case:** Detect if device supports hover interactions.

### 16. Ultra-Wide Monitors
```css
@media (min-width: 2560px) {
  .content-wrapper {
    max-width: 1800px;
    margin: 0 auto;
  }
  
  .sidebar {
    position: sticky;
    top: 20px;
  }
}
```
**Use Case:** Optimize for ultra-wide monitor experiences.

### 17. Inverted Colors Preference
```css
@media (inverted-colors: inverted) {
  img, video {
    filter: invert(1);
  }
}
```
**Use Case:** Handle system-level color inversion accessibility settings.

### 18. Resolution-Specific Adjustments
```css
@media (max-resolution: 150dpi) {
  .fine-details {
    font-size: 16px;
    line-height: 1.6;
  }
}

@media (min-resolution: 300dpi) {
  .fine-details {
    font-size: 14px;
    line-height: 1.4;
  }
}
```
**Use Case:** Adjust typography based on screen pixel density.

### 19. Monochrome Display Detection
```css
@media (monochrome) {
  .color-coding {
    border-left: 4px solid;
  }
  
  .success { border-left-style: solid; }
  .warning { border-left-style: dashed; }
  .error { border-left-style: dotted; }
}
```
**Use Case:** Provide alternative visual cues for monochrome displays.

### 20. Complex Multi-Condition Query
```css
@media screen and 
       (min-width: 1024px) and 
       (prefers-color-scheme: dark) and 
       (prefers-reduced-motion: no-preference) and
       not (prefers-contrast: high) {
  .animated-hero {
    background: linear-gradient(45deg, #1a1a1a, #333);
    animation: gradient-shift 3s ease-in-out infinite;
  }
}
```
**Use Case:** Highly specific targeting for enhanced experiences under exact conditions.

## Frequency Guide

**Basic (1-6):** Used in almost every responsive project
- Mobile breakpoints: Daily use
- Print styles: Weekly use
- Orientation queries: Weekly use

**Intermediate (7-12):** Used regularly in modern web development
- Dark mode: Weekly use (increasingly common)
- Reduced motion: Monthly use (important for accessibility)
- High DPI: Monthly use
- NOT conditions: Monthly use

**Advanced (13-20):** Used for specialized requirements
- Aspect ratio: Rarely (specific design needs)
- Feature detection: Rarely (progressive enhancement)
- Ultra-wide/resolution-specific: Very rarely
- Complex multi-condition: Very rarely (edge cases)