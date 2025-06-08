# 💼 InvestMinD – Full-Stack Smart Investment Tracker (MERN + Gemini AI)

[![Node.js](https://img.shields.io/badge/Node.js-18.x-green?logo=node.js)](https://nodejs.org/)
[![Express](https://img.shields.io/badge/Express.js-Backend-lightgrey?logo=express)](https://expressjs.com/)
[![MongoDB](https://img.shields.io/badge/MongoDB-Atlas-green?logo=mongodb)](https://www.mongodb.com/atlas)
[![React](https://img.shields.io/badge/React-18-blue?logo=react)](https://reactjs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-Strict-blue?logo=typescript)](https://www.typescriptlang.org/)
[![Tailwind CSS](https://img.shields.io/badge/TailwindCSS-3.x-teal?logo=tailwindcss)](https://tailwindcss.com/)
[![JWT Auth](https://img.shields.io/badge/Auth-JWT-blue)](https://jwt.io/)
[![Deployed on DigitalOcean](https://img.shields.io/badge/Backend-DigitalOcean-blue?logo=digitalocean)](https://www.digitalocean.com/)
[![Deployed on Vercel](https://img.shields.io/badge/Frontend-Vercel-black?logo=vercel)](https://vercel.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE)

---

**InvestMinD** is a powerful, modern investment dashboard for tracking portfolios, managing holdings, analyzing performance, and receiving Gemini-powered AI insights. Built with a complete **MERN stack** and deployed on **DigitalOcean** (backend) + **Vercel** (frontend).

---

## 🌐 Live Demo

🔗 [https://www.investmind.live](https://www.investmind.live)


---

## 📸 Screenshots

![Homepage](.client/screenshots/homepage.png)
![Dashboard](.client/screenshots/dashboard.png)

---

## 🧱 Project Structure

```
investmind-monorepo/
├── server/        # Node.js + Express + MongoDB backend
├── client/       # React + TypeScript + Vite + Tailwind frontend
```

---

## 🚀 Core Features

- 🔐 Auth: JWT-based login/signup with OTP email verification
- 📁 Portfolio: Create/delete portfolios with real-time stats
- 💼 Holdings: Add/delete holdings, auto price updates, P/L logic
- 📊 Charts: Time-series, donut, and best/worst performer visualizations
- 🤖 Gemini AI: AI-powered summaries per stock or portfolio
- 📉 Price API: Twelve Data integration for live price fetching
- 📤 Export: Download .xlsx Excel reports with formatting
- 📱 Fully responsive UI with dark mode and Framer Motion animations

---

## 📦 Tech Stack

| Layer     | Tech                             |
|-----------|----------------------------------|
| Frontend  | React 18, TypeScript, Tailwind, Vite, Recharts |
| Backend   | Node.js, Express, MongoDB, JWT, Nodemailer |
| APIs      | Twelve Data API, Google Gemini AI |
| Hosting   | DigitalOcean App Platform (backend), Vercel (frontend) |
| DevTools  | Docker, ESLint, Prettier, GitHub Actions |

---

## 📚 API Documentation

All APIs are prefixed with `/api`.

### 🔐 Auth

| Method | Endpoint         | Description                      |
|--------|------------------|----------------------------------|
| POST   | `/auth/signup`   | Register + send OTP              |
| POST   | `/auth/login`    | Login with email & password      |
| POST   | `/auth/verify-email` | Verify OTP                 |
| POST   | `/auth/resend-otp`   | Resend verification OTP     |
| GET    | `/auth/me`       | Get logged-in user info          |

### 📁 Portfolios

| Method | Endpoint                        | Description                      |
|--------|----------------------------------|----------------------------------|
| GET    | `/portfolios`                   | Get all portfolios               |
| POST   | `/portfolios`                   | Create new portfolio             |
| DELETE | `/portfolios/:id`               | Delete a portfolio               |
| GET    | `/portfolios/:id/stats`         | Portfolio summary (P/L, total)   |
| GET    | `/portfolios/:id/analytics`     | CAGR + current stats             |
| GET    | `/portfolios/:id/stocks`        | Asset-wise distribution          |
| GET    | `/portfolios/:id/best-worst`    | Best/worst performers            |
| GET    | `/portfolios/:id/performance`   | Time-series performance data     |

### 💼 Holdings

| Method | Endpoint                            | Description                          |
|--------|--------------------------------------|--------------------------------------|
| POST   | `/portfolios/:id/holdings`           | Add a holding (buy/sell logic)       |
| GET    | `/portfolios/:id/holdings`           | Get holdings for a portfolio         |
| GET    | `/portfolios/:id/summary`            | Enriched summary (live prices)       |
| GET    | `/holdings/:id`                      | Single holding info                  |
| DELETE | `/holdings/:id`                      | Delete a holding                     |

### 🔁 Transactions

| Method | Endpoint                        | Description                     |
|--------|----------------------------------|---------------------------------|
| GET    | `/transactions/holdings/:id`    | Get transaction history         |

### 📉 Prices

| Method | Endpoint               | Description                    |
|--------|------------------------|--------------------------------|
| GET    | `/prices/price/:symbol`| Live stock/crypto price        |

### 📤 Exports

| Method | Endpoint                      | Description                  |
|--------|-------------------------------|------------------------------|
| GET    | `/exports/portfolios/:id`     | Export holdings to Excel     |

### 🤖 AI Insights

| Method | Endpoint                                | Description                        |
|--------|------------------------------------------|------------------------------------|
| GET    | `/insight`                              | Insight for all portfolios         |
| GET    | `/insight/:portfolioId`                 | Insight for a single portfolio     |
| GET    | `/ai/insight/:portfolioId/:symbol`      | Insight for one asset              |

---

## 🛠️ Setup Instructions

### 1. Clone Repo

```bash
git clone https://github.com/SumanKumar5/InvestMinD.git
cd InvestMinD
```

---

### 2. Backend Setup

```bash
cd server
npm install
cp .env.example .env
# Fill in: MONGO_URI, JWT_SECRET, EMAIL_USER, GEMINI_API_KEY, etc.
npm start
```

Or using Docker:

```bash
docker build -t investmind-api .
docker run -p 5000:5000 investmind-api
```

---

### 3. Frontend Setup

```bash
cd client
npm install
# Set environment variable
echo "VITE_API_BASE_URL=yourbackendurl" > .env
npm run dev
```

---

## 📎 License

This project is licensed under the [MIT License](./LICENSE)  
Created with ❤️ by [Suman Kumar](https://github.com/SumanKumar5)

---

## 🙌 Acknowledgements

- [Twelve Data](https://twelvedata.com/) for real-time financial data  
- [Gemini API](https://deepmind.google/technologies/gemini/) for AI-powered investment insights  
- [DigitalOcean](https://www.digitalocean.com/) and [Vercel](https://vercel.com/) for seamless hosting  
