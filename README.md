# GenSeva AI 🇮🇳 — Complete Setup Guide

## 📋 Prerequisites

Before you begin, ensure you have the following installed:
- **Node.js** (v16 or higher) - [Download here](https://nodejs.org/)
- **npm** (comes with Node.js)
- A code editor (VS Code recommended)
- Git (optional, for cloning)

## ⚡ Get Running in 3 Minutes (FREE)

### Step 1 — Get FREE Groq API Key (2 min)
1. Go to → **https://console.groq.com**
2. Click **"Sign in"** → use your **Google account** (no credit card!)
3. Left menu → **"API Keys"**
4. Click **"Create API Key"** → name it anything → click Create
5. **Copy the key** (starts with `gsk_...`)

### Step 2 — Paste into .env
Open `genseva-app\.env` and replace:
```
GROQ_API_KEY=gsk_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

### Step 3 — Install Dependencies

Navigate to the project folder and install all required packages:

```bash
cd genseva-app
npm install
```

This will install:
- React & React Router (frontend)
- Vite (dev server & build tool)
- Express (backend server)
- Tailwind CSS (styling)
- All other dependencies from package.json

### Step 4 — Run the Application

You have two options:

**Option A: Run Both Servers Together (Recommended)**
```bash
npm start
```

**Option B: Run Servers Separately**

**Terminal 1 (Backend Server):**
```bash
cd genseva-app
npm install
npm audit fix --force
node server.js
```
You should see:
```
✅ GenSeva AI (Groq - FREE) → http://localhost:3001
   Model:   llama-3.3-70b-versatile
   API Key: gsk_xxxxxxxxxx... ✅ Ready!
```

**Terminal 2 (Frontend Dev Server):**
```bash
cd genseva-app
npm run dev
```

Open **http://localhost:5173** in your browser 🎉

---

## 🏗️ Project Structure

```
genseva-app/
├── src/
│   ├── components/       # Reusable UI components
│   │   ├── Navbar.jsx
│   │   ├── Footer.jsx
│   │   ├── LangBar.jsx
│   │   └── UIComponents.jsx
│   ├── pages/           # Main application pages
│   │   ├── Home.jsx
│   │   ├── Chat.jsx
│   │   ├── Schemes.jsx
│   │   ├── Eligibility.jsx
│   │   └── Alerts.jsx
│   ├── data/            # Static data & translations
│   │   ├── schemes.js
│   │   ├── translations.js
│   │   └── constants.js
│   ├── hooks/           # Custom React hooks
│   │   └── useChat.js
│   ├── services/        # External service integrations
│   │   └── awsService.js
│   ├── utils/           # Utility functions
│   │   └── api.js
│   ├── App.jsx          # Main app component
│   ├── main.jsx         # Entry point
│   └── index.css        # Global styles
├── server.js            # Express backend server
├── .env                 # Environment variables (API keys)
├── .env.example         # Example environment file
├── package.json         # Dependencies & scripts
├── vite.config.js       # Vite configuration
└── tailwind.config.js   # Tailwind CSS configuration
```

## 🚀 Available Scripts

| Command | Description |
|---------|-------------|
| `npm install` | Install all dependencies |
| `npm start` | Run both backend & frontend together |
| `npm run dev` | Run frontend dev server only (port 5173) |
| `npm server.js` | Run backend server only (port 3001) |
| `npm run build` | Build production-ready app |

## 🌐 Features

- **Multilingual Support**: Hindi, English, Tamil, Telugu, Bengali, Marathi
- **AI Chat Assistant**: Powered by Groq's Llama 3.3 70B model
- **Government Schemes**: Browse and check eligibility for Indian welfare schemes
- **Responsive Design**: Works on desktop and mobile devices
- **Real-time Alerts**: Stay updated with important notifications

## 🔧 Configuration

### Environment Variables (.env)

```env
GROQ_API_KEY=your_groq_api_key_here
PORT=3001
```

### Ports

- **Frontend (Vite)**: http://localhost:5173
- **Backend (Express)**: http://localhost:3001

## 📝 Development Tips

1. **Hot Reload**: Both frontend and backend support hot reload during development
2. **API Endpoint**: Frontend calls backend at `http://localhost:3001/api/chat`
3. **Styling**: Uses Tailwind CSS - modify `tailwind.config.js` for theme changes
4. **Add New Pages**: Create in `src/pages/` and add route in `App.jsx`

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

---

## Why Groq instead of AWS Bedrock?
Your AWS key (`AKIAT...`) is a **temporary IAM key** that expires and needs a session token.
Groq is 100% free with no expiry — perfect for hackathon demos.
