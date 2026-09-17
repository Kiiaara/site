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
├── index.html                (800+ lines, all content)
├── aos.js                    (animation library, 5KB)
├── aos.css                   (animation styles, 26KB)
├── favicon-64.png           (favicon)
├── apple-touch-icon.png     (iOS icon, 10KB)
├── img10-18.webp            (project images, 1.2MB total)
├── arena-breakout.webp
├── blue-protocol.webp
└── .gitignore
```

**Total Size:** ~1.8MB (mostly images)

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

## 🚀 Deployment Options

### Static Hosting (Recommended)
```
Vercel (recommended):
├─ Auto-deploy on git push
├─ Free SSL/HTTPS
├─ CDN everywhere
├─ Performance optimized
└─ Build time: ~30s

Netlify:
├─ Similar to Vercel
├─ Form handling available
└─ Build time: ~1min

GitHub Pages:
├─ Free hosting on GitHub
├─ No build step needed
├─ gh-pages deployment
└─ https://kiiaara.github.io/site-tkacheva
```

### Custom Domain
```
1. Buy domain (Namecheap, Cloudflare, etc.)
2. Update DNS to hosting provider
3. Add custom domain in Vercel/Netlify settings
4. Enable auto-redirect (www → non-www)
5. SSL auto-configured
```

---

## 🔐 Security

- ✅ No server-side code (no SQL injection risk)
- ✅ Static files only (no authentication needed)
- ✅ HTTPS always enabled
- ✅ No private data exposed
- ✅ CDN caching safe
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
- ✅ CDN cache (default: 24 hours)
- ✅ Gzip compression enabled

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
3. Commit to git
4. Push to GitHub
5. Vercel auto-deploys
6. Live in ~30 seconds
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
- [ ] Multi-language support (EN/RU)
- [ ] Blog section with markdown
- [ ] Contact form with email
- [ ] PDF resume download
- [ ] Video embeds (YouTube/Twitch clips)
- [ ] Testimonials carousel

