# Cruftless CSS

## Overview

**Cruftless CSS** is a **modern, opinionated baseline** for writing clean, maintainable styles.  
It focuses on **only the standardized, widely supported features** developers should use in 2025 and beyond.  

It combines:

- **`reset.css`** → a minimal reset with predictable defaults and design tokens  
- **`.stylelintrc.json`** → linting rules to enforce the subset and block legacy CSS  
- **Demo HTML** → example showing flex, grid, container queries, and modal layering  

---

## Why Cruftless?

CSS has grown for 25+ years. Many legacy features (floats, clearfixes, table layouts) cause bugs and inconsistency.  
Cruftless CSS proposes a **curated subset**:

- ✅ **Modern layouts**: Flexbox, Grid, Container Queries  
- ✅ **Logical spacing**: `margin-inline`, `padding-block`, `gap`  
- ✅ **Predictable defaults**: border-box, system fonts, reset margins  
- ✅ **Intrinsic sizing**: `min-content`, `max-content`, `fit-content`, `aspect-ratio`  
- ✅ **Semantic tokens**: spacing, z-index layers, breakpoints, motion, shadows  
- ✅ **Linting enforcement**: prevents regressions into legacy CSS  

No floats. No clearfix. No `z-index: 99999`. Just modern, predictable CSS.

---

## What's Included

### 1. `reset.css`

A baseline reset that:

- Forces **border-box** everywhere  
- Normalizes **headings and body typography**  
- Makes media elements responsive (`max-width: 100%`)  
- Resets links, lists, forms  
- Declares **design tokens** for:  
  - 🎨 Colors  
  - 📐 Spacing scale  
  - 🔠 Font sizes  
  - 🧱 Z-index layers  
  - 🪟 Breakpoints  
  - 🎞 Motion durations/easing  
  - ☁️ Shadows  

### 2. `.stylelintrc.json`

Lint rules that:

- ✅ Allow only modern CSS properties (flex, grid, logical spacing, etc.)  
- ✅ Restrict units to `px`, `%`, `fr`, `vh`, `vw` (+ `s`/`ms` for timing)  
- ✅ Block floats, clears, multi-columns, vendor prefixes  
- ✅ Require logical spacing props instead of physical ones  
- ✅ Enforce semantic z-index tokens  

### 3. Demo

A sample page shows:

- A sticky header with semantic z-index  
- Sidebar nav adapting with container queries  
- Card grid collapsing at container breakpoints  
- Modal overlay layered with tokens  

---

## Usage

### Install deps

```bash
npm install --save-dev stylelint stylelint-config-standard postcss postcss-logical
```

### Setup PostCSS for autofix

`postcss.config.js`:

```js
module.exports = {
  plugins: [
    require("postcss-logical")()
  ]
};
```

### Import reset

In your main CSS:

```css
@import "./reset.css";
```

### Run lint

```bash
npx stylelint "**/*.css" --fix
```

### Quickstart

Open the demo HTML in your browser → resize → see sidebar and grid adapt independently.  
Click "Open Modal" → see modal layered predictably with tokens.

---

## License

MIT — free to use, adapt, and extend.