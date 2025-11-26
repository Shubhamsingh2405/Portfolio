# 💻 Shubham Kumar Singh — Portfolio Website
Welcome to my personal portfolio website built with **React.js**, **Framer Motion**, and **modern UI design** principles.
It showcases my work, projects, skills, and journey as a developer passionate about **AI, ML, and Web Technologies**.

🌐 **Website:** [Portfolio](https://shubhamsingh2405.github.io/Portfolio/)

---

## 🚀 Features

* 🎨 **Modern UI/UX** with black-based aesthetic theme
* ⚡ Smooth **Framer Motion** animations
* 💼 **Projects, Resume, and Contact sections**
* 🧠 Tech-focused portfolio highlighting AI/ML projects
* 📨 Functional contact form powered by **EmailJS**
* 🧩 Responsive design for all screen sizes

---

## 🛠️ Tech Stack

| Category            | Tools / Libraries                        |
| ------------------- | ---------------------------------------- |
| **Frontend**        | React.js, HTML5, CSS3, JavaScript (ES6+) |
| **Styling**         | Tailwind CSS / Custom CSS                |
| **Animation**       | Framer Motion                            |
| **Contact Form**    | EmailJS                                  |
| **Version Control** | Git & GitHub                             |
| **Deployment**      | GitHub Pages / GitHub Actions            |

---

## ⚙️ Local Development

To run this project locally:

```bash
# 1️⃣ Clone the repository
git clone https://github.com/Shubhamsingh2405/Portfolio.git

# 2️⃣ Navigate to project directory (folder name may vary)
cd Shubham-Portfolio-main

# 3️⃣ Install dependencies
npm install

# 4️⃣ Run development server
npm run dev
```

Now open [http://localhost:5173](http://localhost:5173) in your browser 🚀

---

## 📦 Production Build

To create an optimized build for deployment:

```bash
npm run build       # Build for production
npm run preview     # (Optional) Preview the production build locally
```

This generates a static production build in the `dist/` folder. The Vite config now reads the `DEPLOY_BASE` environment variable:

- Default (`DEPLOY_BASE` unset) → `/` (perfect for Netlify, Vercel, etc.)
- GitHub Pages workflow sets `DEPLOY_BASE=/Portfolio/` during the build so assets load correctly from the subpath.

---

## 📬 Contact

If you'd like to collaborate or just say hi 👋, feel free to reach out!

* 📧 **Email:** [shubhamkumarsingh9939@gmail.com](mailto:shubhamkumarsingh9939@gmail.com)
* 💼 **LinkedIn:** [linkedin.com/in/sks24](https://www.linkedin.com/in/sks24/)
* 💻 **GitHub:** [github.com/Shubhamsingh2405](https://github.com/Shubhamsingh2405)
* 📱 **WhatsApp:** [+917488535121](https://wa.me/+917488535121)
* 📸 **Instagram:** [@_shub.hamm._](https://www.instagram.com/_shub.hamm._/)

---

## 🌟 Deploying to GitHub Pages

GitHub Pages can serve the static files generated in the `dist/` folder. Make sure your repository is at `https://github.com/Shubhamsingh2405/Portfolio.git`.

### 1. Configure Vite for GitHub Pages (only if deploying to a project subpath)

If the site will be hosted at `https://Shubhamsingh2405.github.io/Portfolio/`, set the `base` option in `vite.config.mjs`:

```js
export default defineConfig({
  plugins: [react()],
  base: '/Portfolio/',
});
```

Skip this step if you deploy to a custom domain or the root `Shubhamsingh2405.github.io`.

### 2. Build locally

```bash
npm run build
```

### 3. Deploy with GitHub Actions (recommended)

1. Commit and push your code to the `main` branch of `Portfolio.git`.
2. In GitHub, go to **Settings → Pages → Build and deployment → Source** and choose **GitHub Actions**.
3. Select the **"Deploy Vite"** workflow or create `.github/workflows/deploy.yml` with:

```yaml
name: Deploy to GitHub Pages
on:
  push:
    branches: [main]
  workflow_dispatch:
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with:
          node-version: 18
          cache: npm
      - run: npm ci
      - run: npm run build
      - uses: actions/upload-pages-artifact@v3
        with:
          path: dist
  deploy:
    needs: build
    runs-on: ubuntu-latest
    permissions:
      pages: write
      id-token: write
    environment:
      name: github-pages
      url: ${{ steps.deploy.outputs.page_url }}
    steps:
      - id: deploy
        uses: actions/deploy-pages@v4
```

4. The workflow publishes your site automatically to `https://Shubhamsingh2405.github.io/Portfolio/` after each push.

### 4. Manual deployment alternative

If you prefer manual deployment without Actions:

```bash
npm run build
git add dist -f
git commit -m "Deploy to GitHub Pages"
git subtree push --prefix dist origin gh-pages
```

Then set **Settings → Pages → Source** to `gh-pages` / `root`.

---

## 🚀 Deploying to Netlify

Netlify reads build settings from `netlify.toml` (already added) and automatically handles SPA routing.

- **Build command**: `npm run build`
- **Publish directory**: `dist`
- **Node version**: `18` (declared in `netlify.toml`)
- Automatic fallback: `/* → /index.html` for client-side routing

### Steps

1. Push your latest code to GitHub.
2. Log in to [Netlify](https://app.netlify.com/), click **Add new site → Import an existing project**.
3. Choose your `Portfolio` repository.
4. Netlify will detect the settings from `netlify.toml`. Confirm and deploy.
5. Every push to `main` will trigger a fresh build and deployment.

---

### 🏁 License

This project is open source and available under the [MIT License](LICENSE).
Feel free to fork, use, and build upon it ⭐

---

> *“Showcasing my work and passion through technology 💻”*
