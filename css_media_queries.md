# CSS Media Queries Reference Guide

A comprehensive reference for CSS media queries with practical examples and usage patterns.

## Table of Contents

1. [20 Media Query Examples](#20-media-query-examples)
   - [Basic Level](#basic-level-used-very-frequently---dailyweekly)
   - [Intermediate Level](#intermediate-level-used-regularly---weeklymonthly)
   - [Advanced Level](#advanced-level-used-occasionally---monthlyrarely)
   - [Frequency Guide](#frequency-guide)
2. [Additional Prompt Ideas](#additional-prompt-ideas)
   - [Device & Hardware Focused](#device--hardware-focused)
   - [Accessibility & User Preference](#accessibility--user-preference)
   - [Performance & Network](#performance--network)
   - [Environment & Context](#environment--context)
   - [Advanced Technical](#advanced-technical)
   - [Creative & Experimental](#creative--experimental)
   - [Industry-Specific](#industry-specific)
   - [Future-Focused](#future-focused)
3. [Quick Reference](#quick-reference)
4. [Resources & Further Reading](#resources--further-reading)

---

## 20 Media Query Examples

### Basic Level (Used Very Frequently - Daily/Weekly)

#### 1. Mobile-First Responsive Design
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

#### 2. Desktop Breakpoint
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

#### 3. Hide Elements on Mobile
```css
@media (max-width: 767px) {
  .desktop-only {
    display: none;
  }
}
```
**Use Case:** Hide complex elements on smaller screens.

#### 4. Portrait vs Landscape Orientation
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

#### 5. Print Styles
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

#### 6. Large Desktop Screens
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

### Intermediate Level (Used Regularly - Weekly/Monthly)

#### 7. High DPI/Retina Displays
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

#### 8. Dark Mode Preference
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

#### 9. Reduced Motion Preference
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

#### 10. NOT Condition - Exclude Touch Devices
```css
@media not all and (pointer: coarse) {
  .hover-effect:hover {
    transform: scale(1.05);
    box-shadow: 0 10px 20px rgba(0,0,0,0.2);
  }
}
```
**Use Case:** Apply hover effects only on devices with precise pointers (not touch).

#### 11. Medium Screen Range
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

#### 12. Screen Type Only
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

### Advanced Level (Used Occasionally - Monthly/Rarely)

#### 13. Multiple Conditions with NOT
```css
@media not screen and (min-width: 1024px), 
       not (orientation: landscape) {
  .complex-layout {
    flex-direction: column;
  }
}
```
**Use Case:** Complex logic for specific layout requirements.

#### 14. Aspect Ratio Detection
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

#### 15. Feature Detection - Hover Capability
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

#### 16. Ultra-Wide Monitors
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

#### 17. Inverted Colors Preference
```css
@media (inverted-colors: inverted) {
  img, video {
    filter: invert(1);
  }
}
```
**Use Case:** Handle system-level color inversion accessibility settings.

#### 18. Resolution-Specific Adjustments
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

#### 19. Monochrome Display Detection
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

#### 20. Complex Multi-Condition Query
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

### Frequency Guide

| **Level** | **Examples** | **Usage Frequency** | **Description** |
|-----------|--------------|-------------------|-----------------|
| **Basic (1-6)** | Mobile breakpoints, Print styles, Orientation | Daily/Weekly | Used in almost every responsive project |
| **Intermediate (7-12)** | Dark mode, Reduced motion, High DPI, NOT conditions | Weekly/Monthly | Used regularly in modern web development |
| **Advanced (13-20)** | Aspect ratio, Feature detection, Ultra-wide displays | Monthly/Rarely | Used for specialized requirements and edge cases |

---

## Additional Prompt Ideas

Use these prompts to generate more CSS media query examples:

### Device & Hardware Focused

- Show me CSS media queries for detecting and styling foldable/flexible screen devices
- Create media queries that target specific device capabilities like GPS, camera, or accelerometer
- Generate media queries for different input methods: stylus, voice control, eye-tracking
- Show examples of media queries that detect battery level or power-saving mode
- Create media queries for different display technologies: e-ink, OLED, LCD

### Accessibility & User Preference

- Generate media queries for all accessibility preferences like high contrast, reduced transparency, forced colors
- Show me media queries that detect cognitive accessibility needs and learning disabilities
- Create examples for users with visual impairments: low vision, color blindness, light sensitivity
- Generate media queries for different reading preferences and dyslexia-friendly layouts
- Show media queries that adapt to user's attention span or focus capabilities

### Performance & Network

- Create media queries that adapt based on network speed and data usage preferences
- Show examples of media queries for low-bandwidth or offline scenarios
- Generate media queries that detect device performance capabilities
- Create CSS that adapts based on available memory or processing power
- Show media queries for progressive enhancement based on device capabilities

### Environment & Context

- Generate media queries that adapt to ambient light conditions or time of day
- Show examples for different usage contexts: presentation mode, kiosk mode, embedded widgets
- Create media queries for different interaction contexts: one-handed use, gloved hands, wet conditions
- Generate CSS that adapts to user's physical environment or posture
- Show media queries for different privacy levels or public vs private viewing

### Advanced Technical

- Create complex media queries using CSS Grid and Container Queries together
- Show examples of nested and cascading media query logic
- Generate media queries that work with CSS custom properties and calculations
- Create responsive typography using media queries with clamp(), min(), max()
- Show media queries combined with CSS layers and cascade layers

### Creative & Experimental

- Generate artistic or creative media queries for interactive art projects
- Show media queries for gaming interfaces and interactive experiences
- Create media queries for augmented reality or mixed reality web apps
- Generate examples for voice-controlled interfaces using media queries
- Show media queries that create adaptive themes based on user behavior patterns

### Industry-Specific

- Create media queries specifically for e-commerce and shopping experiences
- Show examples for educational platforms and learning management systems
- Generate media queries for healthcare applications and patient interfaces
- Create examples for financial applications with security considerations
- Show media queries optimized for news, media, and content consumption

### Future-Focused

- Generate media queries using proposed or experimental CSS features
- Show examples that might work with future display technologies
- Create media queries for emerging input methods and interaction patterns
- Generate examples for next-generation web standards and capabilities
- Show media queries that prepare for upcoming accessibility guidelines

#### Combined Prompts

You can also combine prompts for more specific results:

- Show me 10 media queries for e-commerce sites that focus on accessibility and mobile performance
- Generate advanced media queries that combine dark mode, reduced motion, and high contrast preferences
- Create media queries for a news website that adapts to reading speed and attention preferences

---

## Quick Reference

### Common Breakpoints
```css
/* Mobile First Approach */
@media (min-width: 576px) { /* Small devices */ }
@media (min-width: 768px) { /* Medium devices */ }
@media (min-width: 992px) { /* Large devices */ }
@media (min-width: 1200px) { /* Extra large devices */ }
```

### Media Types
- `all` - All devices (default)
- `print` - Print preview and printed pages
- `screen` - Computer screens, tablets, phones
- `speech` - Screen readers

### Common Features
- `width`, `height` - Viewport dimensions
- `device-width`, `device-height` - Device screen dimensions
- `orientation` - `portrait` or `landscape`
- `resolution` - Screen resolution in dpi or dppx
- `aspect-ratio` - Width-to-height ratio
- `prefers-color-scheme` - `light`, `dark`, or `no-preference`
- `prefers-reduced-motion` - `reduce` or `no-preference`
- `hover` - `hover` or `none`
- `pointer` - `coarse`, `fine`, or `none`

---

## Resources & Further Reading

### Official Documentation
- [MDN Web Docs - CSS Media Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries)
- [W3C Media Queries Level 4 Specification](https://www.w3.org/TR/mediaqueries-4/)
- [W3C Media Queries Level 5 Specification (Draft)](https://www.w3.org/TR/mediaqueries-5/)

### Tools & Testing
- [Responsive Design Mode (Firefox)](https://firefox-source-docs.mozilla.org/devtools-user/responsive_design_mode/)
- [Chrome DevTools Device Mode](https://developer.chrome.com/docs/devtools/device-mode/)
- [Can I Use - CSS Media Queries](https://caniuse.com/css-mediaqueries)
- [Media Query Test Pages](https://www.quirksmode.org/css/mediaqueries/)

### Best Practices & Guides
- [Responsive Web Design Basics (Google)](https://web.dev/responsive-web-design-basics/)
- [A Complete Guide to CSS Media Queries (CSS-Tricks)](https://css-tricks.com/a-complete-guide-to-css-media-queries/)
- [Responsive Design Guidelines (Mozilla)](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design)

### Accessibility Resources
- [Understanding WCAG 2.1 Guidelines](https://www.w3.org/WAI/WCAG21/Understanding/)
- [Inclusive Design for Cognitive Disabilities](https://www.w3.org/WAI/WCAG2/supplemental/#cognitiveaccessibilityguidance)
- [prefers-reduced-motion Implementation](https://web.dev/prefers-reduced-motion/)

### Advanced Topics
- [Container Queries (CSS-Tricks)](https://css-tricks.com/say-hello-to-css-container-queries/)
- [CSS Environment Variables](https://developer.mozilla.org/en-US/docs/Web/CSS/env)
- [CSS Custom Properties with Media Queries](https://css-tricks.com/making-custom-properties-css-variables-dynamic/)

### Browser Support & Compatibility
- [Media Queries Browser Support](https://caniuse.com/?search=media%20queries)
- [CSS Grid Browser Support](https://caniuse.com/css-grid)
- [Flexbox Browser Support](https://caniuse.com/flexbox)

---

## Contributing

Found an error or have suggestions for additional examples? Feel free to:
- Open an issue with your feedback
- Submit a pull request with improvements
- Suggest new media query examples or use cases

---

**Last Updated:** August 2025

> **Note:** This guide focuses on widely-supported CSS media queries. Some advanced examples may require modern browsers. Always check browser compatibility for production use.
