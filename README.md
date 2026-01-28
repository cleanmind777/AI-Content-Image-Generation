# Nex.ai – AI SaaS Platform

An intelligent, AI-powered SaaS platform designed to enhance productivity through content generation, image creation, and smart AI-driven tools, built using a modern and scalable tech stack.

🔗 **Live Demo:** https://nexai-saas.vercel.app/

![Nex.ai Landing Page](https://res.cloudinary.com/dxzut3mlw/image/upload/v1769580509/landing_page_phjdfy.png)
---

## ✨ Features

- 🔐 **Authentication** with Clerk
- ✍️ **AI Article Writer** - Generate full-length articles
- 🏷️ **Blog Title Generator** - Creative title suggestions
- 🖼️ **AI Image Generation** - Create images from text prompts
- 🧽 **Background Removal** - Remove image backgrounds instantly
- ✂️ **Object Removal** - Erase unwanted objects from images
- 📊 **User Dashboard** - Track creation history and usage
- 🆓 **Free** & 💎 **Premium** plan support
- 🌐 **Community Section** - Share and explore creations

---

## 🛠️ Tech Stack (PERN)

- **Frontend:** React + Vite
- **Backend:** Node.js + Express
- **Database:** PostgreSQL (Neon)
- **Authentication:** Clerk
- **AI Services:** GeminiAPI, ClipDrop
- **Image Storage:** Cloudinary

---

## 🔐 Authentication

- User authentication handled by **Clerk**
- Secure email & social login
- Session management and protected routes
- Plan-based access control (Free / Premium)

---

## 🗄️ Database (Neon)

PostgreSQL hosted on **Neon** with the following structure:

- **Users** - User profiles and authentication data
- **Creations** - Articles, titles, and images generated
- **Usage Limits** - Track user consumption
- **Subscriptions** - Plan details and billing info

---

## ⚙️ Environment Variables

### Frontend (`client/.env`)

```env
VITE_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
VITE_BASE_URL=http://localhost:3000
```

### Backend (`server/.env`)

```env
PORT=3000

# Database (Neon)
DATABASE_URL=your_neon_postgresql_url

# Clerk Authentication
CLERK_SECRET_KEY=your_clerk_secret_key

# GeminiAPI (Articles & Blog Titles)
GEMINI_API_KEY=your_gemini_api_key

# ClipDrop (Background & Object Removal)
CLIPDROP_API_KEY=your_clipdrop_api_key

# Cloudinary (Image Storage)
CLOUDINARY_CLOUD_NAME=your_cloudinary_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_API_SECRET=your_cloudinary_api_secret
```

---

## ▶️ Run Locally

### Prerequisites

- Node.js >= 16.0.0
- npm or yarn
- PostgreSQL database (Neon account)
- API keys for Clerk, OpenAI, ClipDrop, and Cloudinary

### 1️. Clone the Repository

```bash
git clone https://github.com/jayvar03/nexai.git
cd nexai
```

### 2️. Install Dependencies

```bash
# Install frontend dependencies
cd client
npm install

# Install backend dependencies
cd ../server
npm install
```

### 3️. Set Up Environment Variables

- Create `.env` files in both `client/` and `server/` directories
- Copy the environment variables from the sections above
- Replace placeholder values with your actual API keys

### 4️. Start the Application

```bash
# Start backend (from server/ directory)
cd server
npm run server
# Backend runs on http://localhost:5000

# In a new terminal, start frontend (from client/ directory)
cd client
npm run dev
# Frontend runs on http://localhost:5173
```

Visit `http://localhost:5173` to see the application running!

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

Please make sure to update tests as appropriate and adhere to the project's code style.

---

## ⭐ Show Your Support

Give a ⭐️ if this project helped you!

---

<div align="center">

**[⬆ back to top](#nexai-)**

Made with 💙 by Jay Varshney

</div>