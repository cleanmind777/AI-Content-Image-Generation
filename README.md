<div align="center">

# ✨ Nex.ai – AI SaaS Platform

**An intelligent, AI-powered SaaS platform** that enhances productivity through content generation, image creation, and smart AI-driven tools — built with a modern, scalable tech stack.

[![Live Demo](https://img.shields.io/badge/demo-live-success?style=for-the-badge)](https://nexai-saas.vercel.app/)
[![React](https://img.shields.io/badge/React-19-61DAFB?style=flat-square&logo=react)](https://react.dev/)
[![Vite](https://img.shields.io/badge/Vite-7-646CFF?style=flat-square&logo=vite)](https://vitejs.dev/)
[![Express](https://img.shields.io/badge/Express-5-000000?style=flat-square&logo=express)](https://expressjs.com/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-Neon-336791?style=flat-square&logo=postgresql)](https://neon.tech/)

</div>

---

## 📸 Preview

![Nex.ai Landing Page](https://res.cloudinary.com/dxzut3mlw/image/upload/v1769580509/landing_page_phjdfy.png)

🔗 **Live Demo:** [https://nexai-saas.vercel.app/](https://nexai-saas.vercel.app/)

---

## 📑 Table of Contents

- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [Authentication](#-authentication)
- [Database](#-database)
- [API Reference](#-api-reference)
- [Environment Variables](#️-environment-variables)
- [Getting Started](#-getting-started)
- [Contributing](#-contributing)

---

## ✨ Features

| Feature | Description |
|--------|-------------|
| 🔐 **Authentication** | Secure sign-in with **Clerk** — email, social login, session management, and protected routes |
| ✍️ **AI Article Writer** | Generate full-length articles from prompts using AI (Gemini) |
| 🏷️ **Blog Title Generator** | Get creative, SEO-friendly title suggestions for your posts |
| 🖼️ **AI Image Generation** | Create images from text prompts with AI |
| 🧽 **Background Removal** | Remove image backgrounds instantly (ClipDrop) |
| ✂️ **Object Removal** | Erase unwanted objects from images (ClipDrop) |
| 📊 **User Dashboard** | Track creation history, usage, and manage your content |
| 🆓 **Plans** | **Free** and **Premium** tiers with usage limits |
| 🌐 **Community** | Share and explore creations from other users |

---

## 🛠️ Tech Stack

### Frontend

| Technology | Purpose |
|------------|--------|
| **React 19** | UI library |
| **Vite 7** | Build tool & dev server |
| **React Router 7** | Client-side routing |
| **Tailwind CSS 4** | Styling |
| **Clerk (React)** | Authentication UI & hooks |
| **Axios** | HTTP client |
| **React Hot Toast** | Notifications |
| **React Markdown** | Render markdown (e.g. articles) |
| **Lucide React** | Icons |

### Backend

| Technology | Purpose |
|------------|--------|
| **Node.js** | Runtime |
| **Express 5** | Web framework |
| **Clerk (Express)** | Auth middleware & user verification |
| **Neon** | Serverless PostgreSQL |
| **Cloudinary** | Image upload & storage |
| **Multer** | File upload handling |
| **dotenv** | Environment config |

### External Services

| Service | Use Case |
|---------|----------|
| **Clerk** | Authentication & user management |
| **Gemini API** | Article writing, blog titles |
| **ClipDrop** | Background removal, object removal |
| **Cloudinary** | Image storage & delivery |

---

## 📁 Project Structure

```
AI-Content-Image-Generation/
├── client/                 # Frontend (React + Vite)
│   ├── src/
│   │   ├── components/     # Reusable UI (NavBar, Sidebar, Hero, etc.)
│   │   ├── pages/          # Route pages (Home, Dashboard, WriteArticle, etc.)
│   │   ├── assets/         # Static assets
│   │   ├── App.jsx
│   │   └── main.jsx
│   ├── index.html
│   ├── vite.config.js
│   └── package.json
│
├── server/                 # Backend (Node + Express)
│   ├── configs/            # DB, Cloudinary, Multer
│   ├── controllers/        # aiController, userController
│   ├── middlewares/        # auth
│   ├── routes/              # aiRoutes, userRoutes
│   ├── server.js
│   └── package.json
│
└── README.md
```

### Application Routes

| Path | Page | Description |
|------|------|-------------|
| `/` | Home | Landing page |
| `/ai` | Layout | Main app shell (sidebar + content) |
| `/ai` (index) | Dashboard | Overview & quick access to tools |
| `/ai/write-article` | Write Article | AI article generation |
| `/ai/blog-titles` | Blog Titles | AI blog title suggestions |
| `/ai/generate-images` | Generate Images | Text-to-image generation |
| `/ai/remove-background` | Remove Background | Background removal tool |
| `/ai/remove-object` | Remove Object | Object removal from images |
| `/ai/community` | Community | Shared creations feed |

---

## 🔐 Authentication

- **Provider:** [Clerk](https://clerk.com/)
- **Features:** Email/password and social logins, session management, protected API routes
- **Access control:** Plan-based (Free / Premium) — enforced on backend for AI and usage limits

---

## 🗄️ Database

PostgreSQL hosted on **[Neon](https://neon.tech/)** with a serverless driver.

| Table / Concept | Description |
|-----------------|-------------|
| **Users** | User profiles and auth-related data |
| **Creations** | Stored articles, titles, and generated images |
| **Usage Limits** | Tracks consumption per user/plan |
| **Subscriptions** | Plan details and billing information |

---

## 📡 API Reference

All listed routes require **authentication** (Clerk session).

| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/api/ai/generate-article` | Generate a full article from a prompt (body: prompt/content params) |
| `POST` | `/api/ai/generate-blog-title` | Generate blog title suggestions (body: topic/context) |
| `POST` | `/api/ai/generate-image` | Generate image from text prompt (body: prompt) |
| `POST` | `/api/ai/remove-image-background` | Remove background from image (`multipart/form-data`, field: `image`) |
| `POST` | `/api/ai/remove-image-object` | Remove object from image (`multipart/form-data`, field: `image`) |

User-related endpoints (profile, usage, creations) are under `/api/user/` — see `server/routes/userRoutes.js` for details.

---

## ⚙️ Environment Variables

### Frontend (`client/.env`)

```env
VITE_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
VITE_BASE_URL=http://localhost:3000
```

| Variable | Description |
|----------|-------------|
| `VITE_CLERK_PUBLISHABLE_KEY` | Clerk publishable key for frontend auth |
| `VITE_BASE_URL` | Backend base URL (e.g. `http://localhost:3000`) |

### Backend (`server/.env`)

```env
PORT=3000

# Database (Neon)
DATABASE_URL=your_neon_postgresql_connection_string

# Clerk
CLERK_SECRET_KEY=your_clerk_secret_key

# Gemini (articles & blog titles)
GEMINI_API_KEY=your_gemini_api_key

# ClipDrop (background & object removal)
CLIPDROP_API_KEY=your_clipdrop_api_key

# Cloudinary (image storage)
CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_API_SECRET=your_cloudinary_api_secret
```

| Variable | Description |
|----------|-------------|
| `PORT` | Server port (default `3000`) |
| `DATABASE_URL` | Neon PostgreSQL connection string |
| `CLERK_SECRET_KEY` | Clerk secret key for backend verification |
| `GEMINI_API_KEY` | Google Gemini API key |
| `CLIPDROP_API_KEY` | ClipDrop API key |
| `CLOUDINARY_*` | Cloudinary credentials for uploads |

---

## ▶️ Getting Started

### Prerequisites

- **Node.js** ≥ 16
- **npm** or **yarn**
- **PostgreSQL** (e.g. [Neon](https://neon.tech/) free tier)
- API keys: **Clerk**, **Gemini**, **ClipDrop**, **Cloudinary**

### 1. Clone the repository

```bash
git clone https://github.com/cleanmind777/AI-Content-Image-Generation.git
cd AI-Content-Image-Generation
```

### 2. Install dependencies

```bash
# Frontend
cd client
npm install

# Backend (from repo root)
cd ../server
npm install
```

### 3. Configure environment

- Create `client/.env` and `server/.env`
- Copy the variables from [Environment Variables](#️-environment-variables) and replace placeholders with your keys

### 4. Run the app

**Terminal 1 – Backend**

```bash
cd server
npm run server
```

Backend: **http://localhost:3000** (or the `PORT` you set).

**Terminal 2 – Frontend**

```bash
cd client
npm run dev
```

Frontend: **http://localhost:5173**

Open [http://localhost:5173](http://localhost:5173) in your browser.

### 5. Production build (optional)

```bash
# Frontend
cd client
npm run build
npm run preview   # preview production build locally
```

---

## 🤝 Contributing

Contributions, issues, and feature ideas are welcome.

1. **Fork** the repo
2. **Create a branch:** `git checkout -b feature/your-feature`
3. **Commit:** `git commit -m 'Add your feature'`
4. **Push:** `git push origin feature/your-feature`
5. **Open a Pull Request**

Please keep tests and code style consistent with the project.

---

## ⭐ Show your support

If this project helped you, consider giving it a ⭐ on GitHub.

---

<div align="center">

**[⬆ Back to top](#-nexai--ai-saas-platform)**

*Made with 💙 by [Clean Mind](https://github.com/cleanmind777)*

</div>
