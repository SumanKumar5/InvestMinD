# 🧠 InvestMinD (Full Stack Capstone Project)

[![Node.js](https://img.shields.io/badge/Node.js-18.x-green?logo=node.js)](https://nodejs.org)
[![Express](https://img.shields.io/badge/Express-4.x-black?logo=express)](https://expressjs.com)
[![MongoDB](https://img.shields.io/badge/MongoDB-Atlas-success?logo=mongodb)](https://www.mongodb.com/atlas)
[![JWT](https://img.shields.io/badge/Auth-JWT-orange?logo=jsonwebtokens)](https://jwt.io)
[![React](https://img.shields.io/badge/React-18.2.0-61DAFB?logo=react)](https://react.dev)
[![Tailwind](https://img.shields.io/badge/TailwindCSS-3.4.1-06B6D4?logo=tailwindcss)](https://tailwindcss.com)
[![Vite](https://img.shields.io/badge/Vite-5.2-purple?logo=vite)](https://vitejs.dev)
[![AI Powered](https://img.shields.io/badge/Gemini_AI-Google-blue?logo=google)](https://deepmind.google/technologies/gemini/)

---

**InvestMinD** is a full-stack AI-powered investment management application built using the MERN stack, featuring:
- Secure portfolio management
- Real-time stock prices
- Financial analytics
- Excel export
- Gemini-powered investment insights

---

## 🚀 Key Features

- **Secure User Authentication** (JWT-based)
- **Portfolio & Holdings Management** — Add and track multiple assets including stocks and crypto
- **Transaction Logging** — Automatic average price recalculation for each buy/sell
- **Real-Time Price Integration** — Fetch live market prices via Twelve Data API
- **Performance Analytics** — Calculate total investment, current value, P&L, CAGR, and sector exposure
- **Excel Export** — Download clean and styled `.xlsx` files with financial breakdown
- **AI Insights** — Generate personalized summaries using Gemini (Google) API
- **Scalable Architecture** — Monorepo structure with plans for a CoinMarketCap-style UI

---

## 📁 Folder Structure

```
/InvestMinD
├── /server         # Backend (Node + Express + MongoDB)
│   ├── controllers/
│   ├── routes/
│   ├── models/
│   ├── middleware/
│   ├── services/
│   └── index.js
├── /client         # Frontend (React + Tailwind + Vite) 
└── README.md
```

---

## 🛠️ Tech Stack

| Layer     | Technologies                                      |
|-----------|---------------------------------------------------|
| Frontend  | React 18, Vite, TypeScript, Tailwind CSS (planned)|
| Backend   | Node.js, Express.js, MongoDB Atlas, JWT           |
| AI Layer  | Google Gemini API                                 |
| Market Data | Twelve Data API                                |
| Reports   | ExcelJS                                           |
| Tools     | GitHub, Postman, Vercel (frontend), Heroku        |

---

## 📡 API Endpoints Overview

### Authentication
- `POST /auth/signup` — Create account
- `POST /auth/login` — Get JWT token

### Portfolio
- `POST /portfolios` — Create new portfolio
- `GET /portfolios` — Get all user portfolios
- `GET /portfolios/:id/stats` — Financial stats (P&L, value)
- `GET /portfolios/:id/analytics` — CAGR and sector analysis

### Holdings
- `POST /portfolios/:id/holdings` — Add holding
- `GET /portfolios/:id/holdings` — Get all holdings
- `DELETE /holdings/:id` — Remove holding

### Transactions
- `POST /holdings/:id/transactions` — Log a buy/sell
- `GET /holdings/:id/transactions` — View transaction history

### AI + Export
- `POST /ai/asset-summary` — AI summary for a specific stock
- `GET /insight` — AI summary for full portfolio
- `GET /price/:symbol` — Live stock/crypto price
- `GET /portfolios/:id/export/excel` — Excel download (.xlsx)

---

## 📦 Installation

```bash
# Clone the repo
git clone https://github.com/SumanKumar5/InvestMinD.git
cd InvestMinD/server

# Setup backend
npm install
npm run dev

# Setup .env
PORT=5000
MONGO_URI=your_atlas_uri
JWT_SECRET=your_secure_key
GEMINI_API_KEY=your_google_gemini_api
TWELVE_API_KEY=your_twelvedata_api_key
```

---


## 📄 License

MIT License

> Built with precision and purpose by [Suman Kumar](https://github.com/SumanKumar5)