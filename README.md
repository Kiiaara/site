# 🎨 Kiiaara Portfolio Website

Портфолио Ткачевой Валерии - Influence Marketing Manager. Кейсы со стримерами и блогерами в iGaming и Tech.

**Stack:** HTML5 + CSS3 + Vanilla JavaScript + AOS animations

**🌐 Live Site:** [tkacheva-media.ru](https://tkacheva-media.ru/)

---

## 📋 Overview

Одностраничный лендинг-портфолио:

- ✅ Кейсы и проекты со стримерами/блогерами (25+ кейсов, iGaming & Tech)
- ✅ Переключатель языков (RU/EN)
- ✅ Плавные анимации при скролле (AOS library)
- ✅ Соцсети и контакты
- ✅ Мобильная адаптация

---

## 🛠️ Tech Stack

- **Frontend:** HTML5, CSS3, Vanilla JS
- **Animation:** AOS (Animate On Scroll) library
- **Images:** WebP формат
- **Hosting:** FirstVDS (собственный сервер), Nginx, статика без сборки

---

## 📂 Structure

```text
site-tkacheva/
├── index.html          # вся разметка и стили (одна страница)
├── aos.js, aos.css     # библиотека анимаций при скролле
├── assets/
│   ├── icons/           # favicon, apple-touch-icon
│   └── images/          # картинки кейсов/проектов (webp)
```

---

## 🚀 Local Dev

```bash
python -m http.server 8000
# http://localhost:8000
```

Либо просто открыть index.html в браузере.

---

## 📝 Customization

### Добавить новый кейс/проект

Найти блок карточки проекта в index.html и продублировать структуру, заменив картинку/текст/ссылку.

### Поменять цвета

Цветовая палитра задана переменными в начале `<style>` в index.html:

```css
:root {
    --bg-dark: #020d06;
    --accent-light: #b5f2a1;
    --btn-green: #2ecc71;
}
```

### Обновить картинки

Класть новые webp в `assets/images/`, ссылаться относительным путём из index.html.

---

## 🚀 Deploy

Сайт лежит на FirstVDS под Nginx (домен tkacheva-media.ru), без CI/CD.

Обновление на сервере:
```bash
cd /var/www/site-tkacheva
git pull
```

Nginx настроен на раздачу статики напрямую из `/var/www/site-tkacheva` - пересборка не нужна, изменения видны сразу после pull.

---

## 📞 Contact

- Email: kiiaara2019@gmail.com
- Соцсети - в шапке/футере index.html

---

## 📄 License

MIT License - feel free to fork and customize!
