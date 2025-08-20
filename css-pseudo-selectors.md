# The Complete Guide to 50 CSS Pseudo-Classes

A comprehensive reference covering CSS pseudo-classes from basic to advanced, with practical examples and real-world use cases.

## Table of Contents

1. [Introduction](#introduction)
2. [Basic Pseudo-Classes (1-20)](#basic-pseudo-classes-1-20)
3. [Intermediate Pseudo-Classes (21-35)](#intermediate-pseudo-classes-21-35)
4. [Advanced Pseudo-Classes (36-50)](#advanced-pseudo-classes-36-50)
5. [Frequency Guide](#frequency-guide)
6. [Pseudo-Class Categories](#pseudo-class-categories)
7. [Browser Support Matrix](#browser-support-matrix)
8. [Best Practices](#best-practices)
9. [Resources](#resources)

---

## Introduction

CSS pseudo-classes are keywords added to selectors that specify a special state of the selected elements. They allow you to style elements based on their state, position, or relationship to other elements without requiring additional JavaScript or HTML modifications.

**Syntax:** `selector:pseudo-class { property: value; }`

---

## Basic Pseudo-Classes (1-20)

*Used daily/weekly in most projects*

### 1. `:hover`
**Frequency:** ⭐⭐⭐⭐⭐ (Daily)

Targets an element when the user hovers over it with a pointing device.

```css
.button:hover {
  background-color: #007bff;
  transform: translateY(-2px);
  box-shadow: 0 4px 8px rgba(0,123,255,0.3);
}
```

**Use Case:** Interactive feedback for buttons, links, and clickable elements. Essential for user experience and accessibility.

**How it works:** Activates when the cursor enters the element's bounding box and deactivates when it leaves.

---

### 2. `:active`
**Frequency:** ⭐⭐⭐⭐⭐ (Daily)

Targets an element during the time it's being activated (clicked/tapped).

```css
.button:active {
  transform: translateY(1px);
  box-shadow: 0 1px 2px rgba(0,123,255,0.3);
  background-color: #0056b3;
}
```

**Use Case:** Provides immediate visual feedback when users interact with clickable elements, creating a sense of responsiveness.

**How it works:** Triggers on mousedown/touchstart and ends on mouseup/touchend events.

---

### 3. `:focus`
**Frequency:** ⭐⭐⭐⭐⭐ (Daily)

Targets an element that has received focus (keyboard navigation or programmatic focus).

```css
.input-field:focus {
  outline: none;
  border-color: #007bff;
  box-shadow: 0 0 0 3px rgba(0,123,255,0.25);
}
```

**Use Case:** Critical for accessibility, especially keyboard navigation. Indicates which element is currently selected.

**How it works:** Activates when an element receives focus via Tab key, mouse click, or programmatically via JavaScript.

---

### 4. `:visited`
**Frequency:** ⭐⭐⭐⭐ (Weekly)

Targets links that have been visited by the user.

```css
a:visited {
  color: #6f42c1;
  text-decoration: none;
}

.link-list a:visited::before {
  content: "✓ ";
  color: #28a745;
}
```

**Use Case:** Helps users track which links they've already followed, improving navigation experience.

**How it works:** Browser maintains a history of visited URLs and applies this pseudo-class accordingly.

**Security Note:** Limited CSS properties can be applied due to privacy restrictions.

---

### 5. `:link`
**Frequency:** ⭐⭐⭐⭐ (Weekly)

Targets unvisited links (links with an `href` attribute that hasn't been visited).

```css
a:link {
  color: #007bff;
  text-decoration: underline;
}

.nav-menu a:link {
  position: relative;
  transition: color 0.3s ease;
}
```

**Use Case:** Establishes default styling for fresh, unvisited links to distinguish them from visited ones.

**How it works:** Applies to `<a>` elements with `href` attributes that don't match any URLs in the browser's history.

---

### 6. `:first-child`
**Frequency:** ⭐⭐⭐⭐⭐ (Daily)

Targets an element that is the first child of its parent.

```css
.article p:first-child {
  font-size: 1.2em;
  margin-top: 0;
  font-weight: 500;
}

.menu-item:first-child {
  border-top-left-radius: 8px;
  border-top-right-radius: 8px;
}
```

**Use Case:** Styling the first element differently, removing top margins, or applying special formatting to opening paragraphs.

**How it works:** Selects elements that appear first in their parent's list of child elements, ignoring text nodes.

---

### 7. `:last-child`
**Frequency:** ⭐⭐⭐⭐⭐ (Daily)

Targets an element that is the last child of its parent.

```css
.menu-item:last-child {
  border-bottom: none;
  border-bottom-left-radius: 8px;
  border-bottom-right-radius: 8px;
}

.article p:last-child {
  margin-bottom: 0;
}
```

**Use Case:** Removing bottom borders, margins, or applying closing styles to the final element in a sequence.

**How it works:** Selects elements that appear last in their parent's list of child elements.

---

### 8. `:nth-child(n)`
**Frequency:** ⭐⭐⭐⭐⭐ (Daily)

Targets elements based on their position among siblings using algebraic expressions.

```css
/* Every other row for table striping */
tr:nth-child(even) {
  background-color: #f8f9fa;
}

/* Every third item */
.gallery-item:nth-child(3n) {
  margin-right: 0;
}

/* First 3 items */
.priority-item:nth-child(-n+3) {
  border-left: 4px solid #dc3545;
  font-weight: bold;
}

/* All but first 2 items */
.list-item:nth-child(n+3) {
  opacity: 0.7;
}
```

**Use Case:** Creating patterns, zebra striping, responsive grids, and selective styling based on position.

**How it works:** Uses algebraic formulas where `n` starts from 0. Keywords like `odd`, `even` are shortcuts.

---

### 9. `:disabled`
**Frequency:** ⭐⭐⭐⭐ (Weekly)

Targets form elements that have the `disabled` attribute.

```css
input:disabled,
button:disabled {
  background-color: #e9ecef;
  color: #6c757d;
  cursor: not-allowed;
  opacity: 0.6;
}

.form-group input:disabled + label {
  color: #6c757d;
}
```

**Use Case:** Providing visual feedback for unavailable form controls and preventing user interaction.

**How it works:** Applies to form elements with the `disabled` attribute, making them non-interactive.

---

### 10. `:enabled`
**Frequency:** ⭐⭐⭐ (Monthly)

Targets form elements that are enabled (not disabled).

```css
input:enabled {
  border: 1px solid #ced4da;
  transition: border-color 0.15s ease-in-out;
}

input:enabled:focus {
  border-color: #80bdff;
}
```

**Use Case:** Applying styles specifically to interactive form elements, often used in combination with `:disabled`.

**How it works:** Default state for form elements; opposite of `:disabled`.

---

### 11. `:checked`
**Frequency:** ⭐⭐⭐⭐ (Weekly)

Targets checkboxes, radio buttons, or option elements that are selected/checked.

```css
/* Custom checkbox styling */
input[type="checkbox"]:checked + label::before {
  content: "✓";
  background-color: #007bff;
  color: white;
}

/* Radio button styling */
input[type="radio"]:checked + label {
  font-weight: bold;
  color: #007bff;
}

/* Toggle switch effect */
.toggle input:checked + .slider {
  background-color: #2196F3;
}
```

**Use Case:** Creating custom form controls, toggle switches, and visual feedback for selections.

**How it works:** Activates when the form element's checked state is true.

---

### 12. `:not()`
**Frequency:** ⭐⭐⭐⭐ (Weekly)

Negation pseudo-class that targets elements that don't match the specified selector.

```css
/* All buttons except the primary one */
button:not(.primary) {
  background-color: #6c757d;
}

/* All list items except the first */
li:not(:first-child) {
  border-top: 1px solid #dee2e6;
}

/* All inputs except checkboxes and radios */
input:not([type="checkbox"]):not([type="radio"]) {
  padding: 0.375rem 0.75rem;
  border-radius: 0.25rem;
}
```

**Use Case:** Applying styles to all elements except specific ones, reducing CSS repetition.

**How it works:** Inverts the selection - selects elements that don't match the inner selector.

---

### 13. `:empty`
**Frequency:** ⭐⭐⭐ (Monthly)

Targets elements that have no children (including text nodes).

```css
.message-container:empty {
  display: none;
}

.placeholder:empty::before {
  content: "No content available";
  color: #6c757d;
  font-style: italic;
}

/* Hide empty table cells */
td:empty {
  background-color: #f8f9fa;
}
```

**Use Case:** Hiding empty containers, showing placeholder content, or styling empty states.

**How it works:** Selects elements with no child nodes (elements, text, or whitespace).

---

### 14. `:only-child`
**Frequency:** ⭐⭐⭐ (Monthly)

Targets elements that are the only child of their parent.

```css
.container p:only-child {
  text-align: center;
  font-size: 1.1em;
}

.sidebar .widget:only-child {
  margin-bottom: 0;
}
```

**Use Case:** Special styling when there's only one child element, centering single elements.

**How it works:** Combines `:first-child` and `:last-child` - element must be both.

---

### 15. `:required`
**Frequency:** ⭐⭐⭐⭐ (Weekly)

Targets form elements with the `required` attribute.

```css
input:required {
  border-left: 3px solid #dc3545;
}

input:required + label::after {
  content: " *";
  color: #dc3545;
}

.form-group input:required:invalid {
  border-color: #dc3545;
  background-color: #f8d7da;
}
```

**Use Case:** Visually indicating required form fields and providing validation feedback.

**How it works:** Applies to form elements that have the HTML5 `required` attribute.

---

### 16. `:optional`
**Frequency:** ⭐⭐ (Rarely)

Targets form elements that don't have the `required` attribute.

```css
input:optional {
  border-left: 3px solid #28a745;
}

.form-group input:optional + label::after {
  content: " (optional)";
  color: #6c757d;
  font-size: 0.9em;
}
```

**Use Case:** Distinguishing optional form fields, providing different styling for non-required inputs.

**How it works:** Default state for form elements; opposite of `:required`.

---

### 17. `:valid`
**Frequency:** ⭐⭐⭐⭐ (Weekly)

Targets form elements that pass validation constraints.

```css
input:valid {
  border-color: #28a745;
  background-color: #d4edda;
}

input:valid + .feedback {
  color: #28a745;
  display: block;
}

.form-group input:valid::after {
  content: "✓";
  color: #28a745;
}
```

**Use Case:** Providing positive feedback for correctly filled form fields, real-time validation indication.

**How it works:** Applies to form elements that meet their validation criteria (pattern, type, required, etc.).

---

### 18. `:invalid`
**Frequency:** ⭐⭐⭐⭐ (Weekly)

Targets form elements that fail validation constraints.

```css
input:invalid {
  border-color: #dc3545;
  background-color: #f8d7da;
}

input:invalid + .error-message {
  display: block;
  color: #dc3545;
  font-size: 0.875em;
}

input:invalid:focus {
  box-shadow: 0 0 0 0.2rem rgba(220,53,69,0.25);
}
```

**Use Case:** Highlighting form validation errors, preventing form submission with invalid data.

**How it works:** Applies to form elements that don't meet their validation criteria.

---

### 19. `:root`
**Frequency:** ⭐⭐⭐⭐ (Weekly)

Targets the root element of the document (typically the `<html>` element).

```css
:root {
  /* CSS Custom Properties (Variables) */
  --primary-color: #007bff;
  --secondary-color: #6c757d;
  --font-size-base: 1rem;
  --border-radius: 0.25rem;
  
  /* Global styles */
  font-size: 16px;
  color-scheme: light dark;
}

/* Using the variables */
.button {
  background-color: var(--primary-color);
  border-radius: var(--border-radius);
}
```

**Use Case:** Defining CSS custom properties (variables), setting global styles, theming.

**How it works:** Represents the document's root element with higher specificity than `html`.

---

### 20. `:target`
**Frequency:** ⭐⭐⭐ (Monthly)

Targets the element whose ID matches the current URL fragment identifier.

```css
/* Highlight the targeted section */
:target {
  background-color: #fff3cd;
  padding: 1rem;
  border-left: 4px solid #856404;
  animation: highlight 2s ease-in-out;
}

/* Smooth scroll effect for targeted elements */
:target {
  scroll-margin-top: 80px; /* Account for fixed header */
}

@keyframes highlight {
  0% { background-color: #fff3cd; }
  100% { background-color: transparent; }
}
```

**Use Case:** Creating jump links, highlighting sections, single-page navigation, FAQ accordions.

**How it works:** Activates when the element's ID matches the URL hash (e.g., `#section1`).

---

## Intermediate Pseudo-Classes (21-35)

*Used weekly/monthly for specific functionality*

### 21. `:nth-of-type(n)`
**Frequency:** ⭐⭐⭐ (Monthly)

Targets elements based on their position among siblings of the same element type.

```css
/* Every other heading */
h2:nth-of-type(odd) {
  color: #007bff;
}

/* First 3 images in a gallery */
img:nth-of-type(-n+3) {
  border: 3px solid #ffd700;
}

/* Every 4th paragraph */
p:nth-of-type(4n) {
  font-weight: bold;
  margin: 2rem 0;
}
```

**Use Case:** Styling specific elements of the same type, creating patterns without affecting other element types.

**How it works:** Similar to `:nth-child()` but only counts elements of the same type (tag name).

---

### 22. `:first-of-type`
**Frequency:** ⭐⭐⭐ (Monthly)

Targets the first element of its type among siblings.

```css
/* First heading in each section */
section h2:first-of-type {
  margin-top: 0;
  font-size: 2rem;
  color: #007bff;
}

/* First image in an article */
article img:first-of-type {
  width: 100%;
  margin-bottom: 1rem;
}
```

**Use Case:** Special styling for the first occurrence of an element type, different from first child.

**How it works:** Selects the first element of its type, regardless of other element types before it.

---

### 23. `:last-of-type`
**Frequency:** ⭐⭐⭐ (Monthly)

Targets the last element of its type among siblings.

```css
/* Last paragraph in articles */
article p:last-of-type {
  margin-bottom: 0;
  font-style: italic;
}

/* Last list item of each type */
ul li:last-of-type,
ol li:last-of-type {
  border-bottom: none;
}
```

**Use Case:** Styling the final element of a specific type, removing bottom margins or borders.

**How it works:** Selects the last element of its type among siblings.

---

### 24. `:only-of-type`
**Frequency:** ⭐⭐ (Rarely)

Targets elements that are the only one of their type among siblings.

```css
/* Single image in a container */
.content img:only-of-type {
  display: block;
  margin: 2rem auto;
  max-width: 100%;
}

/* Single table in a section */
section table:only-of-type {
  margin: 0 auto;
  width: 100%;
}
```

**Use Case:** Special styling when there's only one element of a specific type.

**How it works:** Combines `:first-of-type` and `:last-of-type` for the same element.

---

### 25. `:nth-last-child(n)`
**Frequency:** ⭐⭐⭐ (Monthly)

Targets elements based on their position from the end among all siblings.

```css
/* Last 3 items */
.list-item:nth-last-child(-n+3) {
  background-color: #e9ecef;
}

/* Second to last item */
.menu-item:nth-last-child(2) {
  border-bottom: 2px solid #007bff;
}

/* All but last 2 items */
.card:nth-last-child(n+3) {
  margin-bottom: 1rem;
}
```

**Use Case:** Styling elements from the end, creating trailing effects, handling dynamic content.

**How it works:** Counts positions from the last child backwards.

---

### 26. `:nth-last-of-type(n)`
**Frequency:** ⭐⭐ (Rarely)

Targets elements based on their position from the end among siblings of the same type.

```css
/* Last 2 headings */
h3:nth-last-of-type(-n+2) {
  color: #dc3545;
  font-weight: bold;
}

/* All paragraphs except the last one */
p:nth-last-of-type(n+2) {
  margin-bottom: 1rem;
}
```

**Use Case:** Styling specific elements of the same type counting from the end.

**How it works:** Combines `:nth-of-type()` logic with reverse counting.

---

### 27. `:in-range`
**Frequency:** ⭐⭐ (Rarely)

Targets input elements whose value is within the specified range.

```css
input[type="number"]:in-range {
  border-color: #28a745;
  background-color: #d4edda;
}

input[type="range"]:in-range {
  background: linear-gradient(to right, #28a745 0%, #28a745 100%);
}

.price-input:in-range + .feedback {
  color: #28a745;
  content: "✓ Valid price range";
}
```

**Use Case:** Providing feedback for numeric inputs within acceptable ranges.

**How it works:** Applies to input elements with `min`/`max` attributes when value is within range.

---

### 28. `:out-of-range`
**Frequency:** ⭐⭐ (Rarely)

Targets input elements whose value is outside the specified range.

```css
input[type="number"]:out-of-range {
  border-color: #dc3545;
  background-color: #f8d7da;
}

input[type="range"]:out-of-range {
  background: linear-gradient(to right, #dc3545 0%, #dc3545 100%);
}

.age-input:out-of-range + .error {
  display: block;
  color: #dc3545;
}
```

**Use Case:** Highlighting invalid numeric input values, form validation feedback.

**How it works:** Applies to input elements when value is below `min` or above `max` attributes.

---

### 29. `:read-only`
**Frequency:** ⭐⭐ (Rarely)

Targets form elements that are not editable by the user.

```css
input:read-only {
  background-color: #f8f9fa;
  cursor: not-allowed;
  border-style: dashed;
}

.form-display input:read-only {
  border: none;
  background: transparent;
  font-weight: bold;
}
```

**Use Case:** Styling non-editable form fields, display-only inputs.

**How it works:** Applies to form elements with `readonly` attribute or non-editable elements.

---

### 30. `:read-write`
**Frequency:** ⭐⭐ (Rarely)

Targets form elements that are editable by the user.

```css
input:read-write {
  border: 2px solid #ced4da;
  transition: border-color 0.15s ease-in-out;
}

input:read-write:focus {
  border-color: #80bdff;
  outline: 0;
}

textarea:read-write {
  resize: vertical;
  min-height: 100px;
}
```

**Use Case:** Styling editable form elements, distinguishing from read-only fields.

**How it works:** Default state for most form elements; opposite of `:read-only`.

---

### 31. `:placeholder-shown`
**Frequency:** ⭐⭐⭐ (Monthly)

Targets input elements that are displaying placeholder text.

```css
input:placeholder-shown {
  border-color: #ced4da;
}

input:not(:placeholder-shown) {
  border-color: #007bff;
}

/* Floating label effect */
.form-group {
  position: relative;
}

.form-group label {
  position: absolute;
  top: 50%;
  left: 12px;
  transform: translateY(-50%);
  transition: all 0.2s ease;
  pointer-events: none;
}

.form-group input:not(:placeholder-shown) + label,
.form-group input:focus + label {
  top: 0;
  left: 8px;
  font-size: 0.75em;
  color: #007bff;
  background: white;
  padding: 0 4px;
}
```

**Use Case:** Creating floating label effects, conditional styling based on input state.

**How it works:** Applies when the input has a placeholder and no user-entered value.

---

### 32. `:indeterminate`
**Frequency:** ⭐⭐ (Rarely)

Targets form elements in an indeterminate state.

```css
/* Indeterminate checkbox */
input[type="checkbox"]:indeterminate {
  background-color: #007bff;
}

input[type="checkbox"]:indeterminate + label::before {
  content: "−";
  color: white;
  font-weight: bold;
}

/* Progress bar in indeterminate state */
progress:indeterminate {
  animation: progress-bar 2s linear infinite;
}

@keyframes progress-bar {
  0% { background-position: 0% 50%; }
  100% { background-position: 100% 50%; }
}
```

**Use Case:** Styling checkboxes in mixed state, indeterminate progress bars, partial selections.

**How it works:** Applies to checkboxes set to indeterminate via JavaScript, radio buttons with no selection, or progress elements without value.

---

### 33. `:default`
**Frequency:** ⭐⭐ (Rarely)

Targets form elements that are the default among a group.

```css
input[type="radio"]:default + label {
  font-weight: bold;
  color: #007bff;
}

input[type="checkbox"]:default + label::before {
  content: "★ ";
  color: #ffc107;
}

button:default {
  background-color: #007bff;
  color: white;
  border: 2px solid #0056b3;
}
```

**Use Case:** Highlighting default form options, primary buttons, pre-selected choices.

**How it works:** Applies to elements with `checked`, `selected`, or form's default submit button.

---

### 34. `:focus-within`
**Frequency:** ⭐⭐⭐ (Monthly)

Targets an element that contains a focused element.

```css
.form-group:focus-within {
  background-color: #f8f9fa;
  border-radius: 0.25rem;
  padding: 0.5rem;
}

.search-container:focus-within {
  box-shadow: 0 0 0 3px rgba(0,123,255,0.25);
  border-radius: 0.5rem;
}

.card:focus-within {
  transform: translateY(-2px);
  box-shadow: 0 4px 8px rgba(0,0,0,0.1);
}
```

**Use Case:** Styling parent containers when child elements receive focus, creating focus context.

**How it works:** Applies to elements that contain a focused descendant element.

---

### 35. `:focus-visible`
**Frequency:** ⭐⭐⭐ (Monthly)

Targets elements that have focus and should show a focus indicator.

```css
button:focus-visible {
  outline: 2px solid #007bff;
  outline-offset: 2px;
}

/* Remove focus styles for mouse users */
button:focus:not(:focus-visible) {
  outline: none;
}

.link:focus-visible {
  background-color: #fff3cd;
  padding: 2px 4px;
  border-radius: 3px;
}
```

**Use Case:** Providing focus indicators only when needed (keyboard navigation), improving accessibility without cluttering mouse interactions.

**How it works:** Applies focus styles only when the browser determines focus should be visible (typically keyboard navigation).

---

## Advanced Pseudo-Classes (36-50)

*Used occasionally for specialized functionality*

### 36. `:is()`
**Frequency:** ⭐⭐⭐ (Monthly)

Matches any element that matches any of the selectors in the list.

```css
/* Instead of writing multiple selectors */
:is(h1, h2, h3, h4, h5, h6) {
  font-family: 'Roboto', sans-serif;
  line-height: 1.2;
}

/* Complex nested selections */
:is(.article, .blog-post, .news-item) :is(h2, h3) {
  color: #007bff;
  margin-top: 2rem;
}

/* Multiple states */
:is(button, .btn):is(:hover, :focus) {
  transform: translateY(-1px);
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}
```

**Use Case:** Reducing CSS repetition, creating more maintainable selectors, grouping related elements.

**How it works:** Takes a selector list and matches elements that match any selector in that list. Forgiving selector parsing.

---

### 37. `:where()`
**Frequency:** ⭐⭐ (Rarely)

Similar to `:is()` but with zero specificity.

```css
/* Base styles with zero specificity */
:where(h1, h2, h3, h4, h5, h6) {
  color: #333;
  font-weight: bold;
}

/* Easy to override */
.special-heading {
  color: #007bff; /* This will override the above */
}

/* Utility classes with zero specificity */
:where(.mt-0) { margin-top: 0; }
:where(.mb-0) { margin-bottom: 0; }
```

**Use Case:** Creating base styles that are easily overridden, utility classes, reset styles.

**How it works:** Functions like `:is()` but contributes zero to specificity calculation.

---

### 38. `:has()`
**Frequency:** ⭐⭐⭐ (Monthly)

Parent selector - targets elements that contain specific descendants.

```css
/* Cards with images */
.card:has(img) {
  display: grid;
  grid-template-columns: 1fr 2fr;
  gap: 1rem;
}

/* Articles with code blocks */
article:has(pre) {
  font-family: 'Monaco', monospace;
  background-color: #f8f9fa;
  padding: 1rem;
}

/* Forms with errors */
.form-group:has(.error) {
  border-left: 4px solid #dc3545;
  padding-left: 1rem;
}

/* Navigation with dropdown */
.nav-item:has(.dropdown) {
  position: relative;
}
```

**Use Case:** Conditional styling based on content, parent-child relationship styling, dynamic layouts.

**How it works:** Selects elements that contain descendants matching the given selector.

**Note:** Browser support is still growing (2023+).

---

### 39. `:dir()`
**Frequency:** ⭐ (Very Rarely)

Targets elements based on text directionality.

```css
/* Right-to-left text */
:dir(rtl) {
  text-align: right;
}

:dir(rtl) .sidebar {
  float: right;
  margin-left: 2rem;
  margin-right: 0;
}

/* Left-to-right text */
:dir(ltr) .breadcrumb::before {
  content: "→ ";
}

:dir(rtl) .breadcrumb::before {
  content: "← ";
}
```

**Use Case:** Internationalization, supporting right-to-left languages, bidirectional text.

**How it works:** Matches elements based on the computed direction (from `dir` attribute or CSS `direction` property).

---

### 40. `:lang()`
**Frequency:** ⭐ (Very Rarely)

Targets elements based on their language.

```css
/* English quotes */
:lang(en) q::before { content: """; }
:lang(en) q::after { content: """; }

/* French quotes */
:lang(fr) q::before { content: "« "; }
:lang(fr) q::after { content: " »"; }

/* Different fonts for different languages */
:lang(ja) {
  font-family: "Hiragino Sans", "Yu Gothic", sans-serif;
  line-height: 1.8;
}

:lang(ar) {
  font-family: "Amiri", "Arabic Typesetting", serif;
  direction: rtl;
}
```

**Use Case:** Internationalization, language-specific typography, culturally appropriate styling.

**How it works:** Matches elements based on language determined by `lang` attribute, `<meta>` tags, or HTTP headers.

---

### 41. `:scope`
**Frequency:** ⭐ (Very Rarely)

Represents elements that are a reference point for selectors.

```css
/* In a stylesheet, :scope represents :root */
:scope {
  --main-color: #007bff;
}

/* When used with JavaScript querySelector */
/* If used inside a specific container */
@media (min-width: 768px) {
  :scope > .direct-child {
    display: flex;
    gap: 1rem;
  }
}
```

**Use Case:** JavaScript DOM queries with scoped selection, CSS-in-JS libraries, component isolation.

**How it works:** In stylesheets, equivalent to `:root`. In DOM APIs, represents the scoping root element.

---

### 42. `:defined`
**Frequency:** ⭐⭐ (Rarely)

Targets custom elements that have been defined.

```css
/* Style custom elements only after they're defined */
my-component:defined {
  display: block;
  opacity: 1;
  transition: opacity 0.3s ease;
}

/* Hide undefined custom elements */
my-component:not(:defined) {
  display: none;
}

/* Loading state for undefined elements */
web-component:not(:defined) {
  background: linear-gradient(90deg, #f0f0f0 25%, #e0e0e0 50%, #f0f0f0 75%);
  animation: loading 1.5s infinite;
}

@keyframes loading {
  0% { background-position: -200px 0; }
  100% { background-position: calc(200px + 100%) 0; }
}
```

**Use Case:** Web Components development, progressive enhancement with custom elements.

**How it works:** Applies to custom elements after they've been defined with `customElements.define()`.

---

### 43. `:fullscreen`
**Frequency:** ⭐⭐ (Rarely)

Targets elements that are currently in fullscreen mode.

```css
/* Fullscreen video player */
video:fullscreen {
  width: 100vw;
  height: 100vh;
  object-fit: contain;
  background: black;
}

/* Fullscreen document */
:fullscreen {
  background: white;
  padding: 2rem;
  font-size: 1.2em;
  line-height: 1.6;
}

/* Fullscreen button styling */
.fullscreen-container:fullscreen .exit-fullscreen {
  display: block;
  position: fixed;
  top: 20px;
  right: 20px;
  z-index: 1000;
}
```

**Use Case:** Fullscreen video players, immersive reading modes, presentation applications.

**How it works:** Applies to elements currently displayed in fullscreen mode via Fullscreen API.

**Note:** Vendor prefixes may be needed (`:-webkit-full-screen`, `:-moz-full-screen`).

---

### 44. `:picture-in-picture`
**Frequency:** ⭐ (Very Rarely)

Targets elements that are currently in picture-in-picture mode.

```css
/* Video in picture-in-picture mode */
video:picture-in-picture {
  border-radius: 8px;
  box-shadow: 0 4px 20px rgba(0,0,0,0.3);
}

/* Hide controls when in PiP mode */
video:picture-in-picture + .video-controls {
  display: none;
}

/* Style the source video differently */
video:picture-in-picture {
  opacity: 0.8;
  filter: grayscale(0.3);
}
```

**Use Case:** Video applications, media players, multitasking interfaces.

**How it works:** Applies to elements currently in picture-in-picture mode via Picture-in-Picture API.

---

### 45. `:modal`
**Frequency:** ⭐⭐ (Rarely)

Targets elements that are in a modal state.

```css
/* Dialog in modal state */
dialog:modal {
  background: white;
  border-radius: 8px;
  box-shadow: 0 10px 30px rgba(0,0,0,0.3);
  border: none;
  padding: 0;
  max-width: 500px;
  width: 90%;
}

/* Modal backdrop */
dialog:modal::backdrop {
  background: rgba(0,0,0,0.5);
  backdrop-filter: blur(3px);
}

/* Animation for modal */
dialog:modal {
  animation: modalAppear 0.3s ease;
}

@keyframes modalAppear {
  from {
    opacity: 0;
    transform: translateY(-50px) scale(0.9);
  }
  to {
    opacity: 1;
    transform: translateY(0) scale(1);
  }
}
```

**Use Case:** Dialog boxes, modal windows, overlay interfaces.

**How it works:** Applies to `<dialog>` elements opened with `showModal()` method.

---

### 46. `:paused`
**Frequency:** ⭐ (Very Rarely)

Targets media elements that are paused.

```css
/* Show play button overlay when paused */
video:paused::after {
  content: "▶";
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-size: 4rem;
  color: white;
  text-shadow: 0 2px 4px rgba(0,0,0,0.5);
  pointer-events: none;
}

audio:paused + .audio-controls .play-button {
  background-color: #28a745;
  color: white;
}

/* Dim paused media */
video:paused {
  opacity: 0.7;
  filter: brightness(0.8);
}
```

**Use Case:** Media players, video interfaces, audio controls.

**How it works:** Applies to media elements (`<video>`, `<audio>`) that are paused.

---

### 47. `:playing`
**Frequency:** ⭐ (Very Rarely)

Targets media elements that are playing.

```css
/* Hide controls during playback */
video:playing + .video-overlay {
  opacity: 0;
  transition: opacity 0.3s ease;
}

/* Playing indicator */
audio:playing + .status::before {
  content: "🔊 ";
  animation: pulse 1s infinite;
}

@keyframes pulse {
  0%, 100% { opacity: 1; }
  50% { opacity: 0.5; }
}

/* Full brightness when playing */
video:playing {
  opacity: 1;
  filter: brightness(1);
}
```

**Use Case:** Media players, audio visualizers, video applications.

**How it works:** Applies to media elements that are actively playing.

---

### 48. `:seeking`
**Frequency:** ⭐ (Very Rarely)

Targets media elements that are seeking to a new position.

```css
/* Show loading indicator while seeking */
video:seeking::after {
  content: "⏳";
  position: absolute;
  top: 20px;
  right: 20px;
  font-size: 2rem;
  animation: spin 1s linear infinite;
}

@keyframes spin {
  from { transform: rotate(0deg); }
  to { transform: rotate(360deg); }
}

/* Dim video during seeking */
video:seeking {
  opacity: 0.6;
}
```

**Use Case:** Video players, media applications, streaming interfaces.

**How it works:** Applies to media elements while seeking to a new playback position.

---

### 49. `:buffering`
**Frequency:** ⭐ (Very Rarely)

Targets media elements that are buffering content.

```css
/* Show buffering spinner */
video:buffering::before {
  content: "";
  position: absolute;
  top: 50%;
  left: 50%;
  width: 40px;
  height: 40px;
  border: 4px solid rgba(255,255,255,0.3);
  border-top: 4px solid white;
  border-radius: 50%;
  animation: spin 1s linear infinite;
  transform: translate(-50%, -50%);
}

/* Reduce opacity while buffering */
video:buffering {
  opacity: 0.8;
}

/* Show buffer status */
video:buffering + .status::after {
  content: "Buffering...";
  color: #ffc107;
  font-weight: bold;
}
```

**Use Case:** Streaming media, video players, network-dependent content.

**How it works:** Applies to media elements that are buffering data.

**Note:** Limited browser support - may require JavaScript implementation.

---

### 50. `:stalled`
**Frequency:** ⭐ (Very Rarely)

Targets media elements that have stalled while loading.

```css
/* Show network error indicator */
video:stalled::after {
  content: "⚠️ Connection Issues";
  position: absolute;
  top: 20px;
  left: 20px;
  background: rgba(220,53,69,0.9);
  color: white;
  padding: 0.5rem 1rem;
  border-radius: 4px;
  font-size: 0.9rem;
}

/* Indicate stalled state */
audio:stalled + .player-status {
  background-color: #f8d7da;
  color: #721c24;
  border: 1px solid #f5c6cb;
}

/* Retry button for stalled media */
video:stalled + .controls .retry-button {
  display: block;
  background-color: #dc3545;
  color: white;
  border: none;
  padding: 0.5rem 1rem;
  border-radius: 4px;
  cursor: pointer;
}
```

**Use Case:** Media applications, streaming services, network error handling.

**How it works:** Applies to media elements that have stopped loading due to network issues.

**Note:** Limited browser support - may require JavaScript implementation.

---

## Frequency Guide

| **Frequency** | **Count** | **Pseudo-Classes** | **Usage** |
|---------------|-----------|-------------------|-----------|
| ⭐⭐⭐⭐⭐ (Daily) | 8 | `:hover`, `:active`, `:focus`, `:first-child`, `:last-child`, `:nth-child()`, `:not()` | Essential for every project |
| ⭐⭐⭐⭐ (Weekly) | 12 | `:visited`, `:link`, `:disabled`, `:checked`, `:required`, `:valid`, `:invalid`, `:root` | Regular responsive and form styling |
| ⭐⭐⭐ (Monthly) | 15 | `:target`, `:nth-of-type()`, `:first-of-type`, `:last-of-type`, `:enabled`, `:empty`, `:only-child`, `:nth-last-child()`, `:placeholder-shown`, `:focus-within`, `:focus-visible`, `:is()`, `:has()` | Specific functionality and modern features |
| ⭐⭐ (Rarely) | 10 | `:optional`, `:only-of-type`, `:nth-last-of-type()`, `:in-range`, `:out-of-range`, `:read-only`, `:read-write`, `:indeterminate`, `:default`, `:where()`, `:fullscreen`, `:modal` | Specialized use cases |
| ⭐ (Very Rarely) | 5 | `:dir()`, `:lang()`, `:scope`, `:defined`, `:picture-in-picture`, `:paused`, `:playing`, `:seeking`, `:buffering`, `:stalled` | Advanced/experimental features |

---

## Pseudo-Class Categories

### **Interactive States**
`:hover`, `:active`, `:focus`, `:focus-within`, `:focus-visible`, `:target`

### **Form States**  
`:disabled`, `:enabled`, `:checked`, `:required`, `:optional`, `:valid`, `:invalid`, `:in-range`, `:out-of-range`, `:read-only`, `:read-write`, `:placeholder-shown`, `:indeterminate`, `:default`

### **Structural**
`:first-child`, `:last-child`, `:nth-child()`, `:only-child`, `:first-of-type`, `:last-of-type`, `:nth-of-type()`, `:only-of-type`, `:nth-last-child()`, `:nth-last-of-type()`, `:empty`

### **Link States**
`:link`, `:visited`

### **Logical**
`:not()`, `:is()`, `:where()`, `:has()`

### **Document/Language**
`:root`, `:lang()`, `:dir()`, `:scope`

### **Media States**
`:fullscreen`, `:picture-in-picture`, `:modal`, `:paused`, `:playing`, `:seeking`, `:buffering`, `:stalled`

### **Web Components**
`:defined`

---

## Browser Support Matrix

| **Support Level** | **Pseudo-Classes** | **Notes** |
|------------------|-------------------|-----------|
| **Universal** | `:hover`, `:active`, `:focus`, `:visited`, `:link`, `:first-child`, `:last-child`, `:nth-child()`, `:disabled`, `:enabled`, `:checked`, `:not()` | Supported in all modern browsers |
| **Modern** | `:nth-of-type()`, `:first-of-type`, `:last-of-type`, `:valid`, `:invalid`, `:required`, `:optional`, `:root`, `:target`, `:empty`, `:focus-within` | IE9+ support |
| **Recent** | `:is()`, `:where()`, `:focus-visible`, `:placeholder-shown` | Chrome 88+, Firefox 78+, Safari 14+ |
| **Cutting Edge** | `:has()`, `:modal` | Chrome 105+, limited Firefox support |
| **Experimental** | `:buffering`, `:stalled`, `:seeking` | May require JavaScript polyfills |

---

## Best Practices

### **Performance Considerations**
- Use specific selectors instead of complex `:has()` chains
- Avoid deep nesting with structural pseudo-classes
- Cache-friendly selectors improve rendering performance

### **Accessibility Guidelines**  
- Always include `:focus-visible` for keyboard navigation
- Use `:focus-within` for better form accessibility  
- Ensure sufficient color contrast in all states
- Test with screen readers and keyboard navigation

### **Modern CSS Patterns**
```css
/* Use :is() to reduce repetition */
:is(h1, h2, h3):is(:hover, :focus) {
  color: #007bff;
}

/* Combine :has() with other pseudo-classes */
.card:has(.image):hover {
  transform: scale(1.02);
}

/* Use :where() for utility classes */
:where(.reset) {
  margin: 0;
  padding: 0;
}
```

### **Form Enhancement Patterns**
```css
/* Progressive form validation */
.field:has(:valid) .success-icon {
  display: block;
}

.field:has(:invalid:not(:placeholder-shown)) .error-message {
  display: block;
}
```

---

## Resources

### **Official Documentation**
- [MDN Pseudo-Classes Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)
- [W3C Selectors Level 4](https://www.w3.org/TR/selectors-4/)
- [CSS Working Group Drafts](https://drafts.csswg.org/)

### **Browser Support**
- [Can I Use - CSS Selectors](https://caniuse.com/?search=css%20selectors)
- [MDN Browser Compatibility](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes#browser_compatibility)

### **Tools & Testing**
- [CSS Selector Tester](https://www.w3schools.com/cssref/trysel.asp)
- [Specificity Calculator](https://specificity.keegan.st/)
- [CSS Tree Shaking Tools](https://purgecss.com/)

### **Advanced Learning**
- [CSS Selectors Explained](https://css-tricks.com/almanac/selectors/)
- [Modern CSS Solutions](https://moderncss.dev/)
- [CSS Working Group Blog](https://www.w3.org/blog/CSS/)

---

**Last Updated:** August 2025  
**Version:** 1.0

> **Note:** Browser support varies for newer pseudo-classes. Always test in your target browsers and consider progressive enhancement strategies.
