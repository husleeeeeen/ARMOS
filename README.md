# ARMOS
non-destructive testing
armos-site/
├── public/
│   ├── images/
│   │   └── logo.png
├── src/
│   ├── pages/
│   │   ├── index.html
│   │   ├── about.html
│   │   ├── services.html
│   │   └── contact.html
│   ├── styles/
│   │   └── theme.css
│   └── admin/
│       ├── config.yml
│       └── index.html
├── netlify.toml
└── package.json
:root {
  --color-primary: #162457;
  --color-accent: #BD9559;
  --font-main: "Geeks Mariad Pro Cond", sans-serif;
}

body {
  font-family: var(--font-main);
  color: var(--color-primary);
  background: #ffffff;
  margin: 0;
  padding: 0;
}

h1, h2, h3 {
  color: var(--color-primary);
}

button, .highlight {
  background-color: var(--color-accent);
  color: #fff;
  border: none;
  padding: 10px 20px;
  border-radius: 8px;
  cursor: pointer;
}
backend:
  name: git-gateway
  branch: main

media_folder: "public/images/uploads"
public_folder: "/images/uploads"

local_backend: true

collections:
  - name: "news"
    label: "Мэдээ"
    folder: "src/news"
    create: true
    slug: "{{slug}}"
    fields:
      - { label: "Гарчиг", name: "title", widget: "string" }
      - { label: "Огноо", name: "date", widget: "datetime" }
      - { label: "Агуулга", name: "body", widget: "markdown" }

  - name: "services"
    label: "Үйлчилгээ"
    folder: "src/services"
    create: true
    slug: "{{slug}}"
    fields:
      - { label: "Нэр", name: "title", widget: "string" }
      - { label: "Тайлбар", name: "description", widget: "markdown" }
