# AI Agents Intensive — 3-file deploy package

Самодостатній пакет з 3 файлів для будь-якого static-хоста.

## Файли

- **index.html** — головна сторінка (~120 KB). HTML + усі JSX-компоненти inline. Логотипи Genesis вшиті як base64.
- **styles.css** — повна стилізація (~34 KB). Genesis Academy токени + landing-стилі.
- **content.md** — весь текст лендингу в Markdown для редагування / переклади / документації.

## GitHub Pages

1. **github.com → New repository** (publиc).
2. **Add file → Upload files** → перетягни `index.html` і `styles.css` (markdown файл опційно).
3. **Commit changes**.
4. **Settings → Pages → Source: Deploy from a branch → `main` / `/ (root)` → Save**.
5. URL за 1-2 хв: `https://<твій-юзер>.github.io/<repo>/`

## Custom domain

DNS: CNAME `www → <твій-юзер>.github.io`
GitHub: **Settings → Pages → Custom domain** → `www.твій-домен.ua` → **Enforce HTTPS**

## Vercel / Netlify

Просто перетягни папку на vercel.com/new або app.netlify.com/drop. Працює без будь-якого білду.

## Локальний preview

```bash
python3 -m http.server 8000
# або
npx serve .
```

Відкрий [http://localhost:8000](http://localhost:8000).

> ⚠️ Просто двічі клікнути по `index.html` не спрацює — Babel-standalone потребує HTTP. Завжди через локальний сервер.

## Редагування контенту

- **Текст** → `content.md` (зручний reference). Для production-змін редагуй inline-`<script>` блоки в `index.html`.
- **Стилі** → `styles.css` (на початку — токени Genesis Academy, далі — лендинг).
- **Логотипи** → закодовані як base64 у блоці `<script>` з `window.LOGO_GENESIS` / `window.LOGO_MARK`.

## Якщо 404 на GitHub Pages

- `index.html` має лежати в **корені** репо, не в підпапці
- Branch має бути `main` (або `master`) і `/ (root)`
- Репо має бути **публічним** (приватні Pages = Pro)
- Зачекай 2-3 хвилини після push
