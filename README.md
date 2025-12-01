# 📘 Full Stack Software Application Development — Frontend

## Module Details

- **Module**: CST3144 – Full Stack Development
- **Programme**: BSc Computer Science
- **Department**: School of Science and Technology
- **University**: Middlesex University London
- **Module Leader**: Dr. Luca Piras
- **Semester**: 1, Academic Year 2024–2025

## 🧩 Overview

This folder contains the Vue.js front-end for the Course Shop application used in CW1. The front-end displays lessons, supports sorting, search-as-you-type, an Add-to-Cart flow and checkout with client-side validation. The front-end communicates with the Express.js back-end via fetch() promises.

## 🚀 Front-End Features

- Display lessons (v-for) with Subject, Location, Price, Spaces and Image.
- Sort by subject, location, price or spaces (ascending/descending).
- Search-as-you-type (sends queries to backend `/api/search`).
- Add to Cart: button always visible; enabled only when spaces > 0.
- Cart page: show items, remove items (restores spaces), checkout form.
- Checkout validation: Name (letters only), Phone (digits only).
- Uses Tailwind CSS (or your CSS framework) for styling.

## 📂 Frontend Structure

```
frontend/
├── src/
│   ├── components/
│   │   ├── Main.vue
│   │   ├── Hero.vue
│   │   ├── CartPage.vue
│   │   └── Product.vue
│   ├── info.json
│   └── assets/
├── public/
├── index.html
├── vite.config.js
├── package.json
├── jsconfig.json
└── README.md (this file)
```

## 🛠️ Setup & Local Development

Prerequisites:

- Node.js (LTS recommended, e.g., 18 or 20)
- npm

Install and run:

```bash
cd frontend
npm install
npm run dev
# Open http://localhost:5173
```

Build for production:

```bash
npm run build
# output: dist/
```

Preview production build locally:

```bash
npm run preview
```

## 🔧 Environment

- Use `VITE_API_URL` to configure the backend base URL (default: `http://localhost:3000`).
- Create `frontend/.env` or `frontend/.env.development`:

```
VITE_API_URL="http://localhost:3000"
```

- For production, set `VITE_API_URL` to your deployed backend (Render/AWS) in `.env.production`.

## 📡 Scripts (package.json)

- `dev` — start Vite dev server
- `build` — build production assets
- `preview` — preview built assets

## 📡 API Endpoints Used (calls via fetch)

- GET `${VITE_API_URL}/api/lessons` — retrieve all lessons
- GET `${VITE_API_URL}/api/search?q=...` — search lessons
- POST `${VITE_API_URL}/api/orders` — submit order
- PUT `${VITE_API_URL}/api/lessons/:id` — update lesson (spaces)

## 🧪 Testing Checklist (Front-End)

1. Load app at http://localhost:5173 — lessons should display (v-for).
2. Test sorting by subject/location/price/spaces in both asc/desc.
3. Type in search box — results update as you type (search-as-you-type).
4. Click Add to Cart (button visible, disabled at 0 spaces) — spaces should decrement and cart badge increase.
5. Open Cart: verify items, remove item restores spaces.
6. Enter Name (letters only) and Phone (numbers only) in checkout — button becomes enabled; submit shows confirmation.

## 🚀 Deploying Frontend (GitHub Pages)

1. Set `VITE_API_URL` to your backend production URL in `.env.production`.
2. Build: `npm run build`
3. Use `gh-pages` package or GitHub Actions to publish `dist/` to `gh-pages` branch.
4. Enable GitHub Pages in repository settings and confirm site URL.

# Course_purchase

## Deploy to GitHub Pages
- Ensure your build outputs to `dist/`.
- Set default branch to `main`.
- Push to GitHub; the GitHub Actions workflow will build and deploy.
- In repo Settings → Pages, set Source to "GitHub Actions".

## Commands
- Install: `npm ci`
- Build: `npm run build`  <!-- adjust if your project uses a different command -->

## Troubleshooting GitHub Pages
- Verify Actions ran successfully on `main` (check workflow logs).
- In Settings → Pages, Source must be "GitHub Actions".
- Ensure build outputs to `dist/` (or update workflow path).
- If using a project subpath (username.github.io/repo), set base/publicPath in your bundler:
  - Vite: `export default { base: '/<repo>/' }`
  - CRA: set `"homepage": "https://<user>.github.io/<repo>/"` in `package.json`
- For SPA routing, ensure `404.html` exists (added).
- Clear browser cache or force refresh.

## 🔗 Project Links
- [Vue.js App Repository](https://github.com/paschalmario/Course_Purchase_FronteEnd2)
- [Vue.js App GitHub Pages](https://paschalmario.github.io/Course_Purchase_FronteEnd2/)

## 📁 What NOT to commit / submit

- Do NOT include `node_modules/` or `.env` (contains secrets) in the repository or zip submission.
- Include `package-lock.json` to ensure reproducible installs.

## 📚 Notes for Submission

- Include the above links clearly for assessment.
- Include this `frontend/` folder (without node_modules) in your ZIP.
- Provide link to frontend GitHub repo and GitHub Pages URL in the main README.
- Ensure `VITE_API_URL` points to your deployed backend when demonstrating remotely.

## 👤 Author

- **Name**: Zikora P. Okafor
- **Student ID**: M01092421
- **Email**: ZO078@live.mdx.ac.uk

## 📅 Important Dates

- **Submission**: 2nd December, 2PM
- **Demo Weeks**: Week 11–12
