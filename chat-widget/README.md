# Custom Chat Widget

A lightweight, reusable AI chatbot widget built using HTML, CSS, and JavaScript.  
It can be embedded in any website (Shopify, WordPress, React apps, or plain HTML pages).

---

## 🚀 Features

- Floating chat widget UI
- AI chat integration via webhook
- Lead capture form
- Product card rendering support
- Fully responsive design
- Easy to embed in any website

---

## 📦 Installation

### 1. Include the widget files

Add the widget files (HTML/CSS/JS) into your project or serve them via CDN.

---

### 2. Add widget to your site

Place this before closing `</body>` tag:

```html
<script src="path/to/chatbot-widget.js"></script>
<link rel="stylesheet" href="path/to/chatbot-widget.css" />

##Note: i used This widget  in Shopify stores by renaming the file to `.liquid` and placing it inside the theme snippets folder.  
It can then be rendered using `{% render 'chatbot-widget' %}` in `theme.liquid`.