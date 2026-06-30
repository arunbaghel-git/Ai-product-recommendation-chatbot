# Shopify AI Chat Widget

A reusable Shopify chatbot widget built using Liquid, HTML, CSS, and JavaScript.

## Installation

1. Copy `chatbot-widget.liquid` to your theme's `snippets` folder.
2. Render the snippet before the closing `</body>` tag in `layout/theme.liquid`.

```liquid
{% render 'chatbot-widget' %}
```

3. Replace the placeholder webhook URLs:

```javascript
var WEBHOOK = "YOUR_CHAT_WEBHOOK_URL";
var LEAD_URL = "YOUR_LEAD_WEBHOOK_URL";
```

## Features

- Floating chat widget
- Lead capture form
- AI chat integration
- Product card rendering
- Responsive design