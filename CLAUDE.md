# Site Tkacheva - CLAUDE.md

## Status: LIVE (prod - FirstVDS)
Портфолио. Статик сайт на HTML+CSS.

## Stack
- Frontend: HTML5, CSS3, JS (vanilla) - статик сайт
- Deploy: Nginx на FirstVDS

## Structure
```
site-tkacheva/
├── index.html           # главная страница
├── aos.js, aos.css      # анимация при скролле
├── img/*.webp           # картинки портфолио
```

## Deploy
Nginx config:
```bash
server {
    listen 80;
    server_name tkacheva-media.ru;
    root /var/www/site-tkacheva;
    index index.html;
}
```

## Local Dev
```bash
python -m http.server 8000 --directory .
# Open http://localhost:8000
```
