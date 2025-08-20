# 20 CSS Media Query Examples

#### Generated with Claude.AI

### Prompt:
Provide 20 examples of css media queries. This should include a variety of use cases starting with basic common use cases, use cases that use "not" conditions and creative uses of media queries. Label the use cases as "basic", "intermediate" and "advanced" and how frequently the different use cases might be used

### Response:
I've created a comprehensive guide with 20 CSS media query examples, organized by complexity and frequency of use. The examples progress from essential responsive design patterns that you'll use daily, to intermediate accessibility and device-specific queries used regularly, and finally to advanced specialized queries used for edge cases.
The basic queries (1-6) form the foundation of responsive web design and you'll encounter these in virtually every project. The intermediate queries (7-12) are becoming increasingly important as web accessibility and user preferences gain prominence. The advanced queries (13-20) showcase the full power of CSS media queries for handling very specific scenarios.

Each example includes practical code and explains when you'd actually use it in real-world development. The frequency guide at the end helps you prioritize which media queries to learn first based on how often you're likely to need them.

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

## More CSS Media Query Prompts

### Device & Hardware Focused Prompts

"Show me CSS media queries for detecting and styling foldable/flexible screen devices"
"Create media queries that target specific device capabilities like GPS, camera, or accelerometer"
"Generate media queries for different input methods: stylus, voice control, eye-tracking"
"Show examples of media queries that detect battery level or power-saving mode"
"Create media queries for different display technologies: e-ink, OLED, LCD"

### Accessibility & User Preference Prompts

"Generate media queries for all accessibility preferences like high contrast, reduced transparency, forced colors"
"Show me media queries that detect cognitive accessibility needs and learning disabilities"
"Create examples for users with visual impairments: low vision, color blindness, light sensitivity"
"Generate media queries for different reading preferences and dyslexia-friendly layouts"
"Show media queries that adapt to user's attention span or focus capabilities"

### Performance & Network Prompts

"Create media queries that adapt based on network speed and data usage preferences"
"Show examples of media queries for low-bandwidth or offline scenarios"
"Generate media queries that detect device performance capabilities"
"Create CSS that adapts based on available memory or processing power"
"Show media queries for progressive enhancement based on device capabilities"

### Environment & Context Prompts

"Generate media queries that adapt to ambient light conditions or time of day"
"Show examples for different usage contexts: presentation mode, kiosk mode, embedded widgets"
"Create media queries for different interaction contexts: one-handed use, gloved hands, wet conditions"
"Generate CSS that adapts to user's physical environment or posture"
"Show media queries for different privacy levels or public vs private viewing"

### Advanced Technical Prompts

"Create complex media queries using CSS Grid and Container Queries together"
"Show examples of nested and cascading media query logic"
"Generate media queries that work with CSS custom properties and calculations"
"Create responsive typography using media queries with clamp(), min(), max()"
"Show media queries combined with CSS layers and cascade layers"

Creative & Experimental Prompts

"Generate artistic or creative media queries for interactive art projects"
"Show media queries for gaming interfaces and interactive experiences"
"Create media queries for augmented reality or mixed reality web apps"
"Generate examples for voice-controlled interfaces using media queries"
"Show media queries that create adaptive themes based on user behavior patterns"

### Industry-Specific Prompts

"Create media queries specifically for e-commerce and shopping experiences"
"Show examples for educational platforms and learning management systems"
"Generate media queries for healthcare applications and patient interfaces"
"Create examples for financial applications with security considerations"
"Show media queries optimized for news, media, and content consumption"

### Future-Focused Prompts

"Generate media queries using proposed or experimental CSS features"
"Show examples that might work with future display technologies"
"Create media queries for emerging input methods and interaction patterns"
"Generate examples for next-generation web standards and capabilities"
"Show media queries that prepare for upcoming accessibility guidelines"
