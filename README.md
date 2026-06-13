# AI Resume Analyzer

AI-powered web application that analyzes resumes and provides ATS-style feedback, keyword matching, and improvement suggestions.

**Live Demo:** https://ai-resume-analyzer-ivory-psi.vercel.app

---

## Features

- Analyze a resume by pasting text or uploading a PDF
- Optional job description for ATS match scoring
- ATS-style scoring with strengths, weaknesses, and summary
- Keyword match and missing keyword detection
- AI-generated ATS and general improvement suggestions
- User authentication with JWT
- Save, view, and delete past analyses
- Demo mode (no login required)

---

## Tech Stack

| Layer | Technologies |
| --- | --- |
| Frontend | React 19, Vite, Tailwind CSS, React Router |
| Backend | Node.js, Express 5 |
| Database | MongoDB Atlas (Mongoose) |
| AI | Google Gemini (`gemini-2.5-flash`) |
| Deployment | Vercel (frontend), Render (backend) |

---

## Prerequisites

- Node.js 18+
- MongoDB Atlas cluster (or local MongoDB)
- [Google Gemini API key](https://aistudio.google.com/apikey)

---

## Local Setup

### 1. Clone the repository

```bash
git clone https://github.com/mahir-alam/AI-Resume-Analyzer.git
cd AI-Resume-Analyzer
```

### 2. Backend

```bash
cd server
npm install
```

Create `server/.env`:

```env
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=your_secret_key
GEMINI_API_KEY=your_gemini_api_key
CLIENT_URL=http://localhost:5173
PORT=5000
```

Start the API:

```bash
npm run dev
```

The server runs at `http://localhost:5000`.

### 3. Frontend

In a separate terminal:

```bash
cd client
npm install
```

Create `client/.env`:

```env
VITE_API_BASE_URL=http://localhost:5000
```

Start the app:

```bash
npm run dev
```

The client runs at `http://localhost:5173`.

---

## Environment Variables

| Variable | Location | Description |
| --- | --- | --- |
| `MONGODB_URI` | server | MongoDB connection string |
| `JWT_SECRET` | server | Secret for signing auth tokens |
| `GEMINI_API_KEY` | server | Google Gemini API key |
| `CLIENT_URL` | server | Allowed frontend origin for CORS |
| `PORT` | server | API port (default: `5000`) |
| `VITE_API_BASE_URL` | client | Backend base URL |

---

## How It Works

```text
React Frontend → Express API → MongoDB + Google Gemini
```

1. The user submits resume text or a PDF, optionally with a job description.
2. The backend extracts PDF text when needed and sends a structured prompt to Gemini.
3. Gemini returns JSON with scores, keywords, and suggestions.
4. Authenticated users can save analyses to MongoDB and revisit them from the dashboard.

---

## API Overview

| Method | Endpoint | Auth | Description |
| --- | --- | --- | --- |
| `POST` | `/api/analyzer` | Optional | Analyze resume (text or PDF upload) |
| `POST` | `/api/analyzer/save` | Required | Save an analysis |
| `GET` | `/api/analyzer/history` | Required | List saved analyses |
| `DELETE` | `/api/analyzer/:id` | Required | Delete a saved analysis |
| `POST` | `/api/auth/signup` | — | Create account |
| `POST` | `/api/auth/login` | — | Sign in |

---

## Notes

- The first backend request may be slow on Render's free tier (cold start).
- Demo mode runs analysis without saving results to the database.
- A valid `GEMINI_API_KEY` is required for resume analysis.
