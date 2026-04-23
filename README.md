# J&N Junk Removal Website

**Domain:** jandnjunkremoval.com  
**Phone:** (516) 672-5222  
**Email:** jnjunkremovalservices@gmail.com

Built with [Astro](https://astro.build) — fast, SEO-friendly static site.

---

## 📁 Project Structure

```
jandnjunkremoval/
├── public/
│   ├── favicon.svg
│   └── images/          ← Add logo.png and any photos here
├── src/
│   ├── layouts/
│   │   └── Layout.astro     ← Nav, footer, global HTML shell
│   ├── pages/
│   │   ├── index.astro      ← Homepage
│   │   ├── services.astro   ← Services + video carousel
│   │   └── contact.astro    ← Contact form + map + schedule
│   └── styles/
│       └── global.css       ← All CSS variables and shared styles
├── astro.config.mjs
├── package.json
└── tsconfig.json
```

---

## 🚀 Local Development

```bash
# 1. Install dependencies
npm install

# 2. Start dev server
npm run dev

# 3. Open http://localhost:4321
```

---

## 📸 Adding Your Logo & Photos

1. Copy your logo file to: `public/images/logo.png`
2. Add truck/team photos to `public/images/`
3. Reference them in pages as `/images/your-file.png`

---

## 🎬 Adding Videos to Services Page

Open `src/pages/services.astro` and find the video carousel section.
Replace each `video-placeholder` div with a YouTube embed:

```html
<iframe
  src="https://www.youtube.com/embed/YOUR_VIDEO_ID"
  title="Job Title"
  frameborder="0"
  allowfullscreen
  style="width:100%;height:100%;">
</iframe>
```

---

## 📧 Connect the Contact Form

The form currently shows a success message on submit. To actually receive emails:

**Option A — Formspree (easiest, free):**
1. Sign up at [formspree.io](https://formspree.io)
2. Create a new form, get your endpoint like `https://formspree.io/f/xabc1234`
3. In `contact.astro`, update the `<form>` tag:
   ```html
   <form action="https://formspree.io/f/YOUR_ID" method="POST">
   ```
4. Remove the `e.preventDefault()` line from the script

---

## 🌐 Deploy to GitHub + Cloudflare Pages

### Step 1: Push to GitHub
```bash
cd jandnjunkremoval
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/jandnjunkremoval.git
git push -u origin main
```

### Step 2: Connect to Cloudflare Pages
1. Go to [dash.cloudflare.com](https://dash.cloudflare.com)
2. Click **Workers & Pages** → **Create** → **Pages** → **Connect to Git**
3. Select your GitHub repo
4. Set build settings:
   - **Framework:** Astro
   - **Build command:** `npm run build`
   - **Output directory:** `dist`
5. Click **Save and Deploy**

### Step 3: Connect Custom Domain
1. In Cloudflare Pages → your project → **Custom domains**
2. Add `jandnjunkremoval.com`
3. Cloudflare will automatically configure DNS since your domain is already on Cloudflare

---

## 🎨 Customization

- **Colors:** Edit CSS variables in `src/styles/global.css` (`:root` block)
- **Phone/Email:** Search for `5166725222` and `jnjunkremoval` to update globally
- **Services:** Edit the `services` array in `src/pages/services.astro`
- **Service areas:** Edit the areas list in `src/pages/contact.astro`
