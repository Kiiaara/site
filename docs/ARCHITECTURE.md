# 🏗️ Site Architecture

## Overview

Static HTML portfolio website with client-side animations and responsive design.

---

## 🏛️ Architecture

```
┌─────────────────────────────────┐
│   Browser (Client-Side Only)    │
├─────────────────────────────────┤
│                                 │
│  index.html (main structure)    │
│       ↓                         │
│  ┌─────────────────────────┐   │
│  │  CSS Styling            │   │
│  │  • aos.css (animations) │   │
│  │  • Inline styles        │   │
│  └─────────────────────────┘   │
│       ↓                         │
│  ┌─────────────────────────┐   │
│  │  JavaScript             │   │
│  │  • aos.js (scroll anim) │   │
│  │  • Vanilla JS handlers  │   │
│  └─────────────────────────┘   │
│       ↓                         │
│  ┌─────────────────────────┐   │
│  │  Images (WebP)          │   │
│  │  • Project screenshots  │   │
│  │  • Icons                │   │
│  └─────────────────────────┘   │
│                                 │
└─────────────────────────────────┘
```

---

## 📁 File Organization

```
site-tkacheva/
├── index.html                (main structure + styles)
├── aos.js, aos.css           (scroll animation library)
├── assets/
│   ├── icons/                 (favicon, apple-touch-icon)
│   └── images/                (project/case screenshots, webp)
└── .gitignore
```

---

## 🎨 Design System

### Color Palette
- Primary: Dark theme (charcoal/dark gray)
- Accent: Vibrant blues/purples
- Text: White/light gray
- Hover: Brightness increase

### Typography
- Headlines: Bold sans-serif
- Body: Regular sans-serif
- Monospace: Code snippets

### Responsive Breakpoints
- Mobile: <600px (full width, single column)
- Tablet: 600-1024px (2 columns)
- Desktop: >1024px (3+ columns, full layout)

---

## 🔄 Page Load Flow

```
1. Browser requests index.html
2. HTML parsed (DOM construction)
3. CSS loaded → style calculation
4. aos.js loaded → scroll listener attached
5. Images lazy-loaded (WebP format)
6. User scrolls → AOS animations trigger
7. Smooth scroll to sections
8. Social links → external navigation
```

**Performance Timeline:**
```
0-100ms:   HTML parsing
100-200ms: CSS parsing
200-500ms: Image fetch
500-1000ms: Font rendering
1000ms+:   User interaction
```

---

## 🎯 Section Components

### Hero Section
- Background image or gradient
- Title + subtitle
- Call-to-action button
- Parallax scroll effect (optional)

### Projects Grid
- Responsive card layout
- Image + title + description
- Hover effects (zoom, overlay)
- Click → external link

### Skills Section
- Tech stack icons
- Categorized (Frontend, Backend, AI, etc.)
- Skill level bars (optional)

### Contact Footer
- Social media links
- Email form (static or Formspree)
- Copyright info

---

## 🚀 Deployment

### Hosting
```
FirstVDS (собственный сервер):
├─ Nginx раздаёт статику напрямую
├─ Домен: tkacheva-media.ru
├─ SSL: Let's Encrypt на сервере
└─ Деплой: git pull на сервере (без CI/CD)
```

Nginx конфиг и команды деплоя - в CLAUDE.md.

---

## 🔐 Security

- ✅ No server-side code (no SQL injection risk)
- ✅ Static files only (no authentication needed)
- ✅ HTTPS always enabled
- ✅ No private data exposed
- ⚠️ External links: validate before adding

---

## ⚡ Performance Optimizations

### Images
- ✅ WebP format (saves 30-50% vs JPEG)
- ✅ Optimized resolution (1920x1080 max)
- ✅ Lazy loading (load on scroll)
- ✅ Responsive images (srcset for retina)

### CSS/JS
- ✅ Minify on deploy
- ✅ Inline critical CSS
- ✅ Defer non-critical JS
- ✅ Tree-shake unused styles

### Caching
- ✅ Browser cache (index.html: no-cache, static assets: 1 year)
- ✅ Gzip compression enabled в Nginx

---

## 📊 Analytics Ready

To add analytics:

```html
<!-- Google Analytics (gtag) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_ID');
</script>

<!-- Or Plausible Analytics -->
<script defer data-domain="kiiaara.ru" src="https://plausible.io/js/script.js"></script>
```

---

## 🔄 Update Flow

```
1. Edit index.html locally
2. Test in browser (open index.html)
3. Commit to git, push в GitHub
4. На сервере: git pull в /var/www/site-tkacheva
5. Изменения видны сразу (статика без сборки)
```

---

## 📱 Mobile Optimization

- Viewport meta tag configured
- Touch-friendly buttons (min 48px)
- Readable font sizes (16px+ body)
- No horizontal scroll
- Fast tap responses (no 300ms delay)
- Mobile-first CSS

---

## 🎨 Customization Guide

### Change Colors
```css
/* In aos.css or inline style */
:root {
  --primary: #1a1a1a;
  --accent: #00d4ff;
  --text: #ffffff;
}
```

### Add New Section
```html
<section class="new-section" data-aos="fade-up">
  <h2>My New Section</h2>
  <p>Content here...</p>
</section>
```

### Modify AOS Animation
```html
<div data-aos="flip-left" data-aos-duration="1000" data-aos-easing="ease-in-out">
  Animated content
</div>
```

---

## 📈 Future Enhancements

- [ ] Dark/light mode toggle
- [ ] Blog section with markdown
- [ ] Contact form with email
- [ ] PDF resume download
- [ ] Video embeds (YouTube/Twitch clips)
- [ ] Testimonials carousel

