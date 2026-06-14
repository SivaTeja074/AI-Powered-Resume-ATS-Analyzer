# AI-Powered Resume ATS Analyzer

## Live Demo

🌐 [Live Application](https://ai-powered-resume-ats-analyzer.vercel.app)
⚙️ [Backend API](https://ai-powered-resume-ats-analyzer.onrender.com)

## Overview
AI-Powered Resume ATS Analyzer is a full-stack web application that helps students, fresh graduates, and job seekers evaluate their resumes using Generative AI. The platform analyzes resume content, compares it with a target job description, calculates ATS compatibility, identifies missing keywords, and provides actionable recommendations to improve interview readiness.

## Features

### AI Resume Analysis
- Analyze resume content using Google Gemini AI
- Professional resume review and scoring
- Resume strengths and weaknesses detection
- Personalized improvement suggestions

### ATS Optimization
- ATS Match Score calculation
- Missing keyword identification
- Matched keyword detection
- ATS-specific recommendations

### Resume Upload Support
- PDF resume upload
- Automatic text extraction from PDF files
- Manual resume text input

### User Authentication
- Secure registration and login
- JWT-based authentication
- Protected routes and user sessions

### Analysis History
- Save previous resume analyses
- Review past reports
- Track resume improvements over time

### Modern User Experience
- Responsive UI
- Dashboard workspace
- Demo mode
- Clean and professional design

---

## Tech Stack

### Frontend
- React 19
- React Router DOM
- Vite
- Tailwind CSS

### Backend
- Node.js
- Express.js
- MongoDB
- Mongoose

### AI & Processing
- Google Gemini 2.5 Flash
- PDF Parse

### Authentication
- JWT
- bcryptjs

### Deployment
- Vercel (Frontend)
- Render (Backend)
- MongoDB Atlas (Database)

---

## Project Structure

```text
AI-Powered-Resume-ATS-Analyzer/
│
├── client/
│   ├── public/
│   ├── src/
│   │   ├── assets/
│   │   ├── components/
│   │   │   ├── AnalysisCard.jsx
│   │   │   └── AnalysisSection.jsx
│   │   │
│   │   ├── pages/
│   │   │   ├── Home.jsx
│   │   │   ├── Login.jsx
│   │   │   ├── Signup.jsx
│   │   │   ├── Dashboard.jsx
│   │   │   ├── Demo.jsx
│   │   │   ├── History.jsx
│   │   │   └── AnalyzerWorkspace.jsx
│   │   │
│   │   ├── App.jsx
│   │   └── main.jsx
│   │
│   ├── package.json
│   └── vercel.json
│
├── server/
│   ├── config/
│   │   └── db.js
│   │
│   ├── controllers/
│   │   ├── analyzerController.js
│   │   ├── authController.js
│   │   └── messageController.js
│   │
│   ├── middleware/
│   │   └── authMiddleware.js
│   │
│   ├── models/
│   │   ├── User.js
│   │   └── Analysis.js
│   │
│   ├── routes/
│   │   ├── authRoutes.js
│   │   ├── analyzerRoutes.js
│   │   └── messageRoutes.js
│   │
│   ├── index.js
│   └── package.json
│
└── README.md
```

---

## Installation

### Clone Repository

```bash
git clone https://github.com/SivaTeja074/AI-Powered-Resume-ATS-Analyzer.git
cd AI-Powered-Resume-ATS-Analyzer
```

### Backend Setup

```bash
cd server
npm install
```

Create `.env`:

```env
PORT=5000

MONGODB_URI=your_mongodb_connection_string

JWT_SECRET=your_secret_key

GEMINI_API_KEY=your_gemini_api_key

CLIENT_URL=http://localhost:5173
```

Run backend:

```bash
npm run dev
```

---

### Frontend Setup

```bash
cd client
npm install
```

Create `.env`:

```env
VITE_API_URL=http://localhost:5000
```

Run frontend:

```bash
npm run dev
```

---

## Available Scripts

### Frontend

```bash
npm run dev
npm run build
npm run preview
```

### Backend

```bash
npm run dev
npm start
```

---

## API Endpoints

### Authentication

```http
POST /api/auth/register
POST /api/auth/login
```

### Resume Analysis

```http
POST /api/analyzer/analyze
GET  /api/analyzer/history
```

### Health Check

```http
GET /api/health
```

---

## Deployment

### Frontend (Vercel)

Build Command:

```bash
npm run build
```

Output Directory:

```text
dist
```

### Backend (Render)

Build Command:

```bash
npm install
```

Start Command:

```bash
npm start
```

---

## Future Improvements

- Resume version comparison
- Multiple job description matching
- AI-generated resume rewriting
- Cover letter generation
- Interview preparation assistant
- Skill gap analysis
- Export reports as PDF

---

## Author

Talari Siva Teja

B.Tech Student | Full Stack Developer | AI Enthusiast

