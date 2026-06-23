# AI Super Hub

![React](https://img.shields.io/badge/React-18-61DAFB?logo=react&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-646CFF?logo=vite&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-06B6D4?logo=tailwindcss&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-16+-339933?logo=nodedotjs&logoColor=white)
![Express](https://img.shields.io/badge/Express-4.x-000000?logo=express&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-5.x-47A248?logo=mongodb&logoColor=white)
![Google Gemini](https://img.shields.io/badge/Google_Gemini_AI-8E75B2?logo=googlegemini&logoColor=white)
![License](https://img.shields.io/badge/License-Educational-lightgrey)

A full-stack AI learning platform that combines course management, AI-powered chat assistance, a curated AI-tools directory, and an extensive prompt library — built with React, Node.js, and MongoDB, and integrated with Google Gemini for intelligent conversational experiences.

**Live Demo:** https://ai-super-hub.vercel.app
**Repository:** https://github.com/naikdivesh/ai-super-hub


<img width="2560" height="1290" alt="image" src="https://github.com/user-attachments/assets/6676f2ae-666c-48bc-a189-4712228558a4" />
<img width="2560" height="1302" alt="image" src="https://github.com/user-attachments/assets/5f513a0c-453f-4c27-b9bf-615f44443c1e" />




---

## Overview

AI Super Hub is a learning-management system for AI enthusiasts. It provides structured courses, four specialized AI assistants, a searchable directory of curated AI tools, a reusable prompt library, and a full admin panel for content and user management — all behind secure authentication and a documented REST API.

**At a glance:** 50+ React components · 29 pages · 70+ curated AI tools · 100+ prompts · 58+ REST endpoints · 7 MongoDB collections · 4 integrated external services.

---

## Key Features

### For Users
- **Courses** — browse and filter by category/difficulty, one-click enrollment, video + rich-text lessons, progress tracking, quizzes with instant scoring, and auto-generated completion certificates.
- **AI Chat Assistant** — four modes (General, Tutor, Coder, Summarizer) powered by Google Gemini, with context-aware conversations, persistent history, and automatic chat-title generation.
- **Tools Directory** — 70+ AI tools with category filtering, search, and bookmarking.
- **Prompt Library** — 100+ prompts with filtering, one-click copy, and favorites.
- **Dashboard & Profile** — learning analytics, certificates, bookmarks, avatar upload, theme toggle, and account management.

### For Administrators
- **Dashboard** — system-wide metrics for users, courses, tools, and prompts.
- **Content Management** — full CRUD for courses, lessons, quizzes, tools, and prompts, with publish and "featured" controls.
- **User Management** — directory with search, role assignment, and account controls.
- **Support** — ticket lifecycle management with status tracking, admin notes, and automated email notifications.

---

## Tech Stack

### Frontend
| Technology | Purpose |
|---|---|
| React 18 | UI framework |
| Vite | Build tool & dev server |
| Tailwind CSS | Utility-first styling |
| React Router | Client-side routing |
| Framer Motion | Animations |
| Axios | HTTP client |
| React Hot Toast | Notifications |
| Lucide React | Icon library |

### Backend
| Technology | Purpose |
|---|---|
| Node.js + Express | Runtime & web framework |
| MongoDB + Mongoose | Database & ODM |
| JWT + bcrypt | Authentication & password hashing |
| Passport.js | Google OAuth 2.0 strategy |
| Express Validator | Request validation |
| Swagger JSDoc | API documentation |
| Multer | File-upload handling |

### External Services
| Service | Purpose |
|---|---|
| Google Gemini AI | Conversational AI |
| Cloudinary | Image & file storage |
| SendGrid | Transactional email |
| Google OAuth 2.0 | Social authentication |

---

## Project Structure

```
ai-super-hub/
├── client/                     # React frontend (Vite)
│   ├── src/
│   │   ├── components/         # Shared, layout, and UI components
│   │   ├── context/           # React context providers
│   │   ├── pages/             # Page components (incl. admin/)
│   │   ├── services/          # API service layer
│   │   └── utils/             # Helpers
│   └── vite.config.js
│
└── server/                     # Node/Express backend
    └── src/
        ├── config/            # DB, Cloudinary, Passport, Swagger
        ├── controllers/       # Request handlers
        ├── middlewares/       # Auth & error handling
        ├── models/            # Mongoose schemas (7 collections)
        ├── routes/            # API routes
        ├── services/          # gemini.service.js, email.service.js
        └── validators/        # Input validation
```

---

## Getting Started

### Prerequisites
- Node.js v16+ and npm
- MongoDB (local or Atlas)
- API keys: Google Gemini, Google OAuth, Cloudinary, SendGrid

### 1. Clone
```bash
git clone https://github.com/naikdivesh/ai-super-hub.git
cd ai-super-hub
```

### 2. Install dependencies
```bash
cd server && npm install
cd ../client && npm install
```

### 3. Configure environment
Create `server/.env`:
```env
MONGODB_URI=mongodb://localhost:27017/ai-super-hub
JWT_SECRET=your_jwt_secret_min_32_chars
JWT_EXPIRE=7d
GOOGLE_CLIENT_ID=your_google_client_id
GOOGLE_CLIENT_SECRET=your_google_client_secret
GOOGLE_CALLBACK_URL=http://localhost:5000/api/auth/google/callback
CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret
SENDGRID_API_KEY=your_sendgrid_key
SENDGRID_FROM_EMAIL=noreply@aisuperhub.com
GEMINI_API_KEY=your_gemini_key
CLIENT_URL=http://localhost:3000
NODE_ENV=development
PORT=5000
```
Create `client/.env`:
```env
VITE_API_URL=http://localhost:5000/api
```

### 4. Run
```bash
# Terminal 1 — backend
cd server && npm run dev      # http://localhost:5000

# Terminal 2 — frontend
cd client && npm run dev      # http://localhost:3000
```
Swagger docs available at `http://localhost:5000/api/docs`.

---

## API Overview

A documented REST API with **58+ endpoints** across nine categories (OpenAPI 3.0 / Swagger):

| Category | Endpoints | Description |
|---|---|---|
| Authentication | 9 | Registration, login, OAuth, password management |
| Users | 5 | Profile and account management |
| Courses | 15 | CRUD, enrollment, lessons, quizzes |
| Tools | 9 | Directory and bookmark management |
| Chats | 6 | AI conversation management |
| Prompts | 6 | Prompt-library operations |
| Support | 4 | Ticket system |
| Upload | 4 | Media upload to Cloudinary |
| Health | 1 | Health check |

Protected endpoints expect a bearer token: `Authorization: Bearer <jwt>`.

---

## AI Integration

The chat experience is powered by **Google Gemini** through a dedicated service layer (`server/src/services/gemini.service.js`):

- **Four modes** with distinct system prompts — General, Tutor, Coder, and Summarizer.
- **Context-aware** conversations using the last 10 messages.
- **Resilient generation** via a 3-tier model fallback (Gemini 2.5 Flash → 2.5 Pro → 2.5 Flash Lite) with graceful error handling.
- **Automatic chat titles** generated from the first message.

---

## Security

- **JWT authentication** with bcrypt-hashed passwords (10 salt rounds).
- **Google OAuth 2.0** via Passport.js.
- **Role-based access control** (`protect`, `adminOnly`, `optionalAuth` middleware) — users access only their own data; admins manage all.
- **Email verification** (OTP) and **secure password reset** (time-limited tokens).
- **Input validation** on both client and server (Express Validator + Mongoose schema validation).

---

## Deployment

- **Frontend:** Vercel (Vite preset, `npm run build`, output `dist`).
- **Backend:** Render (Node web service, root `server`, start `node src/app.js`).
- **Database:** MongoDB Atlas.

After deploying, update `VITE_API_URL`, the Google OAuth callback URL, and `CLIENT_URL` to point at the production URLs.

---

## Author

**Divesh Naik** — M.S. Information Systems, Northeastern University
- Email: naik.di@northeastern.edu
- LinkedIn: https://www.linkedin.com/in/diveshnaik/
- GitHub: https://github.com/naikdivesh

Built as the final project for **INFO 6150 – Web Design & User Experience Engineering** (Fall 2025).

---

## License

Developed for educational purposes as part of coursework at Northeastern University.

## Acknowledgments

Google Gemini AI, Cloudinary, SendGrid, and MongoDB Atlas for their developer platforms, and the open-source maintainers of React, Express, Tailwind CSS, and Framer Motion.
