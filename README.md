# Kiiaara Portfolio Website

Портфолио Ткачевой Валерии - Influence Marketing Manager. Кейсы со стримерами и блогерами в iGaming и Tech.

**Stack:** HTML5 + CSS3 + Vanilla JavaScript + AOS animations

**Live Site:** [tkacheva-media.ru](https://tkacheva-media.ru/)

**Hosting:** FirstVDS (собственный сервер), Nginx, статика без сборки

---

## Overview

Одностраничный лендинг-портфолио:

- Кейсы и проекты со стримерами/блогерами
- Информация об услугах
- Соцсети и контакты

---

## Structure

```text
site-tkacheva/
├── index.html          # вся разметка и стили (одна страница)
├── aos.js, aos.css     # библиотека анимаций при скролле
├── assets/
│   ├── icons/           # favicon, apple-touch-icon
│   └── images/          # картинки кейсов/проектов (webp)
```

---

## Local Dev

```bash
python -m http.server 8000
# http://localhost:8000
```

Либо просто открыть index.html в браузере.

---

## Deploy

Сайт лежит на FirstVDS под Nginx (домен tkacheva-media.ru), без CI/CD.

Обновление на сервере:
```bash
cd /var/www/site-tkacheva
git pull
```

Nginx настроен на раздачу статики напрямую из `/var/www/site-tkacheva` - пересборка не нужна, изменения видны сразу после pull.

---

## Contact

- Email: kiiaara2019@gmail.com
- Соцсети - в шапке/футере index.html

---

## License

MIT
