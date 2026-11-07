# 🎨 Design System — Campus IoT Platform

> **INSTRUKSI UNTUK AI:** File ini adalah sumber kebenaran untuk semua keputusan visual.
> Sebelum menulis CSS apapun, BACA file ini dan gunakan token yang sudah didefinisikan.
> JANGAN PERNAH hardcode warna, spacing, atau shadow — gunakan CSS custom properties.

---

## 🎨 Color Tokens

Salin blok CSS ini ke `:root` di setiap stylesheet:

```css
:root {
    color-scheme: light;

    /* === PRIMARY === */
    --color-primary:       #176b87;   /* Buttons, links, CTA */
    --color-primary-dark:  #10536d;   /* Hover states, section headings */
    --color-primary-light: #1e8fad;   /* Lighter variant for accents */
    --color-accent:        #65d6c3;   /* Highlights, tags, badges, decorative */

    /* === NEUTRAL === */
    --color-ink:           #17243b;   /* Heading text, strong emphasis */
    --color-muted:         #59677d;   /* Body text, secondary content */
    --color-subtle:        #8b97a8;   /* Placeholders, disabled text */
    --color-paper:         #f3f6f8;   /* Page background */
    --color-surface:       #ffffff;   /* Cards, panels, modals */
    --color-border:        #dce5eb;   /* Card borders, dividers */
    --color-border-light:  #e8eff2;   /* Subtle decorative borders */

    /* === SEMANTIC === */
    --color-success:       #22c55e;   /* Tersedia, berhasil */
    --color-success-bg:    #f0fdf4;   /* Background success state */
    --color-warning:       #f59e0b;   /* Peringatan, pending */
    --color-warning-bg:    #fffbeb;   /* Background warning state */
    --color-error:         #ef4444;   /* Error, rusak, gagal */
    --color-error-bg:      #fef2f2;   /* Background error state */
    --color-info:          #3b82f6;   /* Info, tips */
    --color-info-bg:       #eff6ff;   /* Background info state */

    /* === SHADOWS === */
    --shadow-sm:    0 1px 2px rgb(23 36 59 / 5%);
    --shadow-md:    0 4px 12px rgb(23 36 59 / 7%);
    --shadow-card:  0 16px 40px rgb(23 36 59 / 7%);
    --shadow-xl:    0 20px 60px rgb(0 0 0 / 15%);
    --shadow-hover: 0 8px 24px rgb(23 36 59 / 12%);

    /* === RADIUS === */
    --radius-sm:    4px;    /* Badges, tags */
    --radius-md:    8px;    /* Buttons, inputs */
    --radius-lg:    12px;   /* Small cards */
    --radius-xl:    20px;   /* 1.25rem — Large cards, sections */
    --radius-2xl:   24px;   /* Hero elements */
    --radius-full:  999px;  /* Pills, avatars, pill buttons */

    /* === SPACING (8pt Grid) === */
    --space-1:   4px;
    --space-2:   8px;
    --space-3:   12px;
    --space-4:   16px;
    --space-5:   20px;
    --space-6:   24px;
    --space-8:   32px;
    --space-10:  40px;
    --space-12:  48px;
    --space-16:  64px;
    --space-20:  80px;
    --space-24:  96px;

    /* === TYPOGRAPHY === */
    --font-family: Inter, "Segoe UI", system-ui, -apple-system, sans-serif;
    --text-xs:     0.75rem;    /* 12px */
    --text-sm:     0.875rem;   /* 14px */
    --text-base:   1rem;       /* 16px */
    --text-lg:     1.08rem;    /* ~17px — subheadings */
    --text-xl:     1.25rem;    /* 20px */
    --text-2xl:    1.5rem;     /* 24px */
    --text-3xl:    2rem;       /* 32px */
    --text-4xl:    clamp(2.4rem, 6vw, 4.7rem); /* Hero */

    /* === LINE HEIGHTS === */
    --leading-tight:   1.08;   /* Hero headings */
    --leading-snug:    1.3;    /* Section headings */
    --leading-normal:  1.55;   /* Subheadings, lead text */
    --leading-relaxed: 1.75;   /* Body text */

    /* === FONT WEIGHTS === */
    --weight-regular:  400;
    --weight-medium:   500;
    --weight-semibold: 600;
    --weight-bold:     700;
    --weight-extrabold: 760;   /* Hero headings */
    --weight-black:    800;    /* Badge labels */

    /* === TRANSITIONS === */
    --transition-fast: 160ms ease;
    --transition-base: 200ms ease;
    --transition-slow: 300ms ease;

    /* === Z-INDEX === */
    --z-base:    1;
    --z-card:    2;
    --z-sticky:  10;
    --z-overlay: 50;
    --z-modal:   100;
}
```

---

## 📐 Typography Scale

| Level | Size | Weight | Line-Height | Letter-Spacing | Usage |
|-------|------|--------|-------------|----------------|-------|
| Hero H1 | `clamp(2.4rem, 6vw, 4.7rem)` | 760 | 1.08 | -0.055em | Landing page hero |
| Page H1 | `clamp(1.8rem, 4vw, 2.5rem)` | 700 | 1.2 | -0.04em | Interior page titles |
| H2 | `clamp(1.45rem, 3.5vw, 2rem)` | 700 | 1.3 | -0.035em | Section headings |
| H3 | `1.08rem` | 650 | 1.4 | -0.015em | Sub-section headings |
| Body | `1rem` (16px) | 400 | 1.75 | 0 | Main content |
| Lead | `clamp(1.05rem, 2.4vw, 1.35rem)` | 400 | 1.55 | 0 | Intro paragraphs |
| Small | `0.875rem` (14px) | 400 | 1.5 | 0 | Captions, metadata |
| Label | `0.75rem` (12px) | 750-800 | 1.5 | 0.16em | Badges, uppercase labels |

---

## 🧩 Component Specifications

### Button — Primary
```css
.btn-primary {
    display: inline-flex;
    min-height: 44px;
    align-items: center;
    justify-content: center;
    padding: 0.65rem 1.1rem;
    border: none;
    border-radius: var(--radius-full);
    background: var(--color-primary);
    color: #f7fbfd;
    font-size: var(--text-sm);
    font-weight: var(--weight-semibold);
    text-decoration: none;
    cursor: pointer;
    transition: background-color var(--transition-fast),
                transform var(--transition-fast),
                box-shadow var(--transition-fast);
}

.btn-primary:hover {
    transform: translateY(-2px);
    background: var(--color-primary-dark);
    box-shadow: var(--shadow-hover);
}

.btn-primary:focus-visible {
    outline: 3px solid var(--color-accent);
    outline-offset: 4px;
}

.btn-primary:active {
    transform: translateY(0);
}
```

### Button — Ghost/Outline
```css
.btn-ghost {
    display: inline-flex;
    min-height: 44px;
    align-items: center;
    padding: 0.65rem 1.1rem;
    border: 1px solid rgb(255 255 255 / 28%);
    border-radius: var(--radius-full);
    background: transparent;
    color: inherit;
    font-weight: var(--weight-semibold);
    transition: background-color var(--transition-fast),
                border-color var(--transition-fast),
                transform var(--transition-fast);
}

.btn-ghost:hover {
    transform: translateY(-2px);
    border-color: var(--color-accent);
    background: rgb(255 255 255 / 10%);
}
```

### Card
```css
.card {
    position: relative;
    overflow: hidden;
    padding: clamp(1.5rem, 5vw, 3rem);
    border: 1px solid var(--color-border);
    border-radius: var(--radius-xl);
    background: var(--color-surface);
    box-shadow: var(--shadow-card);
}

.card:hover {
    transform: translateY(-2px);
    box-shadow: var(--shadow-hover);
}
```

### Input
```css
.input {
    width: 100%;
    min-height: 44px;
    padding: var(--space-3) var(--space-4);
    border: 1px solid var(--color-border);
    border-radius: var(--radius-md);
    background: var(--color-surface);
    color: var(--color-ink);
    font-family: var(--font-family);
    font-size: var(--text-base);
    transition: border-color var(--transition-fast),
                box-shadow var(--transition-fast);
}

.input:focus {
    border-color: var(--color-primary);
    box-shadow: 0 0 0 3px rgb(23 107 135 / 15%);
    outline: none;
}

.input::placeholder {
    color: var(--color-subtle);
}
```

### Badge / Tag
```css
.badge {
    display: inline-flex;
    align-items: center;
    padding: var(--space-1) var(--space-2);
    border-radius: var(--radius-sm);
    font-size: var(--text-xs);
    font-weight: var(--weight-black);
    letter-spacing: 0.04em;
    line-height: 1.5;
}

.badge--success {
    background: var(--color-success-bg);
    color: #166534;
}

.badge--warning {
    background: var(--color-warning-bg);
    color: #92400e;
}

.badge--error {
    background: var(--color-error-bg);
    color: #991b1b;
}

.badge--info {
    background: #e5f5f2;
    color: var(--color-primary-dark);
}
```

---

## 📱 Responsive Breakpoints

```css
/* Mobile first — base styles are for mobile */

/* Tablet */
@media (min-width: 640px) {
    /* Adjust grid columns, increase padding */
}

/* Desktop */
@media (min-width: 1024px) {
    /* Full layout, max-width containers */
}

/* Reduced Motion */
@media (prefers-reduced-motion: reduce) {
    *, *::before, *::after {
        transition-duration: 0.01ms !important;
        animation-duration: 0.01ms !important;
    }
}
```

---

## 🖼️ Image Grid Patterns

### 2-Column Grid
```css
.image-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 1.5rem;
    margin-top: 1.5rem;
}
```

### Before-After Comparison
```css
.before-after {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 1.5rem;
    padding: 1.5rem;
    border: 2px solid var(--color-border);
    border-radius: var(--radius-lg);
    background: #fafcfd;
}
```

---

## 🌊 Background Patterns

### Gradient Hero (Dark)
```css
background:
    radial-gradient(circle at 82% 18%, rgb(101 214 195 / 19%), transparent 25rem),
    linear-gradient(135deg, #10243b 0%, #173d58 58%, #176b87 100%);
```

### Subtle Page Background
```css
background:
    radial-gradient(ellipse at 50% 20%, rgb(213 230 236 / 36%), transparent 48%),
    var(--color-paper);
```

### Security/Success Background
```css
background: linear-gradient(135deg, #f3fbf8 0%, #e8f7f2 100%);
border: 2px solid #d5ece6;
```

---

## ✅ Visual Quality Checklist

Sebelum submit kode, pastikan:

1. [ ] Semua warna pakai CSS `var(--color-*)` — ZERO hardcoded hex
2. [ ] Spacing kelipatan 4px/8px (8pt grid)
3. [ ] Typography hierarchy: Hero > H2 > H3 > Body > Small
4. [ ] Responsive: mobile (< 640px), tablet (640-1024px), desktop (> 1024px)
5. [ ] Hover + focus-visible states di SEMUA interactive elements
6. [ ] `prefers-reduced-motion` support
7. [ ] Semantic HTML (bukan `<div>` soup)
8. [ ] Alt text di semua `<img>`
9. [ ] WCAG AA contrast ratio (4.5:1 body, 3:1 large text)
10. [ ] Shadows berlayer (bukan satu shadow besar)

