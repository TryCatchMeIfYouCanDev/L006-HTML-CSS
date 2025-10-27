# LESSON SIX – CSS Style Sheets and Selectors

## 1. Introduction to CSS3

CSS (Cascading Style Sheets) is a language used to define the presentation of an HTML or XML document — including layout, colors, fonts, and spacing.  
Created in 1996, CSS separates **structure** (HTML) from **presentation**, improving code maintainability and accessibility.  
The current standard, **CSS3**, is continuously evolving.

---

## 2. Types of Style Sheets

| Type                    | Description                                                                                                             | Syntax Example                            | Priority                  |
| ----------------------- | ----------------------------------------------------------------------------------------------------------------------- | ----------------------------------------- | ------------------------- |
| **Inline**              | Applied directly to a single HTML element using the `style` attribute. Not recommended as it mixes structure and style. | `<p style="color:red;">Text</p>`          | Highest                   |
| **Internal (Embedded)** | Written inside the `<style>` tag in the `<head>` section. Applies styles to the entire document.                        | `<style>p { color:red; }</style>`         | Medium                    |
| **External**            | Uses a separate `.css` file linked with `<link>` or imported via `@import`. Recommended best practice.                  | `<link rel="stylesheet" href="main.css">` | Lowest (depends on order) |

### Loading Order

1. External styles should be linked **before** internal styles.
2. Inline styles always override both.
3. The `!important` declaration overrides all other rules but should be avoided for maintainability.

---

## 3. Linking Methods

### Using `<link>` (Recommended)

```html
<link rel="stylesheet" href="css/main.css" />
```

### Using `@import`

```css
<style>
    @import url("css/main.css");
</style>
```

> `@import` is CSS syntax, while `<link>` is HTML syntax.  
> In modern workflows, `<link>` is preferred. Tools like **SASS** combine multiple CSS files into one optimized file.

---

## 4. CSS Selectors

Selectors are patterns used to target specific HTML elements for styling.

| Selector Type           | Syntax                  | Description                                                 |
| ----------------------- | ----------------------- | ----------------------------------------------------------- |
| **Type Selector**       | `p {}`                  | Targets all `<p>` elements.                                 |
| **Descendant Selector** | `nav a {}`              | Targets all `<a>` inside `<nav>`.                           |
| **Child Selector**      | `div > p {}`            | Targets `<p>` elements that are direct children of `<div>`. |
| **Adjacent Sibling**    | `h2 + p {}`             | Targets the first `<p>` immediately following an `<h2>`.    |
| **General Sibling**     | `h2 ~ p {}`             | Targets all `<p>` elements after `<h2>` at the same level.  |
| **Attribute Selector**  | `input[type="text"] {}` | Targets elements with a specific attribute or value.        |
| **Universal Selector**  | `* {}`                  | Targets all elements.                                       |
| **Group Selector**      | `h1, h2, h3 {}`         | Applies the same style to multiple elements.                |

---

## 5. Classes

Classes allow you to style multiple elements (even of different types) consistently.

### Syntax

```css
.warning {
  background-color: yellow;
  color: red;
  font-size: 1.5rem;
}
```

### Rules

- Classes are applied using the `class` attribute: `<p class="warning">Text</p>`
- Class names **can** start with numbers but **must not contain spaces**.
- Elements can have **multiple classes** separated by spaces.
- A **generic (open)** class can be applied to any tag: `.warning {}`
- A **restricted (closed)** class applies to a specific tag: `a.warning {}`

| Selector Type | Example                   | Applies To                                |
| ------------- | ------------------------- | ----------------------------------------- |
| Open Class    | `.warning {}`             | Any element with class "warning"          |
| Closed Class  | `a.warning {}`            | Only `<a>` elements with class "warning"  |
| Combined      | `a.warning, p.warning {}` | Both `<a>` and `<p>` with class "warning" |

---

## 6. IDs

IDs uniquely identify elements within a single HTML page.

### Syntax

```css
#sidebarRight {
  background-color: pink;
  border: 5px dotted red;
}
```

```html
<aside id="sidebarRight">I am the right sidebar</aside>
```

### Rules for IDs

1. Must be **unique** in the page.
2. **Case-sensitive** (`#Navbar` ≠ `#navbar`).
3. **No spaces** allowed.
4. Should **not start with a number**.

> Use IDs for **unique layout containers** (e.g., `main`, `section`, `aside`), not for general styling.  
> Never assign the same ID to multiple elements. If repeated styling is needed, use a class instead.

---

## 7. Units and Measurements

### Absolute Units

- `px`, `cm`, `mm`, `pt`, `pc`, `in`
- Independent of user device.
- Browser default font size: **16px**.

### Relative Units

- `%`, `em`, `rem`
- Adapt to user settings or parent elements.

| Unit  | Base Reference                    | Example             | Result                  |
| ----- | --------------------------------- | ------------------- | ----------------------- |
| `em`  | Relative to parent element        | `32px ÷ 16px = 2em` | 2 × base font size      |
| `rem` | Relative to root element (`html`) | `1.5rem`            | 1.5 × root font size    |
| `%`   | Relative to container             | `width: 50%;`       | Half the parent’s width |

> Use `em` or `rem` for font sizing and `%` for layout dimensions.

---

## 8. Shorthand Properties

Some CSS properties can group multiple values into a single declaration.

### Example: `border`

```css
border: 2px dashed pink;
```

| Property | Description                                           |
| -------- | ----------------------------------------------------- |
| Width    | `2px`                                                 |
| Style    | `solid`, `dashed`, `dotted`                           |
| Color    | Any valid CSS color (`red`, `#ff0000`, `rgb()`, etc.) |

> The order of shorthand values doesn’t matter, but **separate them with spaces**.

---

## 9. Best Practices

- Always use **external style sheets**.
- Minimize internal styles.
- Avoid inline styles completely.
- Use **semantic and reusable class names** (avoid `.big` or `.greenLink`).
- Use IDs for **unique** layout elements.
- Use classes for **repeated styling**.
- Understand the **Box Model** before building layouts.

---

**Useful Links**

1. https://placehold.co/
2. https://dummyimage.com/
3. https://www.css3buttongenerator.com/
4. https://caniuse.com/
5. https://pagespeed.web.dev/?hl=IT
6. https://tinyjpg.com/
7. https://ezgif.com/
8. https://www.dummyimage.com/?utm_content=cmp-true
9. https://developer.mozilla.org/en-US/docs/Web/Media/Guides/Formats/Image_types
10. https://www.flaticon.com/
11. https://www.image-map.net/
12. https://fonts.google.com/

---

**End of Lesson Six**
