# MemoraX

AI-powered smart study assistant that transforms documents into flashcards, quizzes, summaries, analytics, contextual AI chat, and interactive annotations.

---
## Problem Statement

Students often work with large PDFs, lecture notes, and other study materials that are difficult to organize and revise efficiently. Creating flashcards and practice questions manually is time-consuming, while traditional study methods provide limited insights into learning progress and areas that need improvement.

Students also lack a centralized platform where they can manage study materials, practice concepts, interact with AI for clarification, and monitor their performance.

MemoraX addresses these challenges by converting static study materials into structured, interactive, and personalized learning experiences.

## Overview

MemoraX is a full-stack AI learning platform that helps students study smarter by converting raw study material into structured, interactive learning tools.

Users can upload documents and instantly generate:
- Flashcards
- Quizzes
- Summaries
- AI-powered chat responses
- Performance analytics dashboard
- Interactive PDF annotations

---

## Features

### 🔐 Authentication & User Management
- JWT-based authentication
- Login / Register
- Protected routes
- Profile management
- Profile image upload (Cloudinary integration)
- Password update functionality

---

### 📄 Document Processing
- Upload PDF documents (single + multiple upload support)
- Editable document titles before upload
- Duplicate document name prevention (frontend validation)
- Automatic text extraction
- Intelligent chunking
- Cloud storage support
- Document status tracking

---

### 🧠 AI Features (Gemini Powered)
- AI flashcard generation
- AI quiz generation (MCQs)
- AI summaries (structured)
- Context-aware chat with documents
- Persistent chat history

---

### 🃏 Flashcards
- Auto-generated flashcards
- Difficulty tagging
- Star / unstar
- Review tracking
- Centralized flashcard manager (across all documents)

---

### 📝 Quizzes
- Multiple-choice questions
- Score calculation
- Attempt tracking
- Result storage
- Performance-based analytics
- Centralized flashcard & quiz manager (across all documents)

---

### 🖊️ PDF Annotation System (NEW)
- Draw on PDFs (pen tool)
- Highlighter tool
- Eraser functionality
- Undo / Redo support
- Color selection & stroke control
- Collapsible annotation toolbar
- Save annotations (persisted per document)

---

### 📊 Analytics Dashboard
- User-specific analytics (NOT global)
- Study activity (last 30 days)
- Quiz performance tracking
- Flashcard mastery (donut chart)
- Weekly consistency graph
- Feature usage insights

---

### 🎨 UI/UX
- Fully responsive
- Dark theme across app
- Recharts-powered analytics
- Clean SaaS-style dashboard layout
- Interactive modals & smooth transitions

---

## 🛠 Tech Stack

### Backend
- Node.js
- Express.js
- MongoDB + Mongoose
- JWT Authentication
- Multer (file upload)
- Cloudinary (media storage)
- Google Gemini AI

---

### Frontend
- React.js (Vite)
- Tailwind CSS
- React Router
- Context API
- Recharts (analytics)
- React Hot Toast
- Lucide Icons
- React Konva (PDF annotations)

---

### AI Model
- gemini-2.5-flash-lite

---

## 📁 Updated Project Structure
```
MEMORAX
│
├── backend
│   ├── config
│   │   ├── cloudinary.js
│   │   ├── db.js
│   │   └── multer.js
│   │
│   ├── controllers
│   │   ├── aiController.js
│   │   ├── annotationController.js
│   │   ├── authController.js
│   │   ├── communityController.js
│   │   ├── documentController.js
│   │   ├── flashcardController.js
│   │   ├── notificationController.js
│   │   ├── progressController.js
│   │   └── quizController.js
│   │
│   ├── middleware
│   │   ├── auth.js
│   │   ├── errorHandler.js
│   │   └── upload.js
│   │
│   ├── models
│   │   ├── annotationModel.js
│   │   ├── chatHistoryModel.js
│   │   ├── commentModel.js
│   │   ├── documentModel.js
│   │   ├── flashcardModel.js
│   │   ├── notificationModel.js
│   │   ├── postModel.js
│   │   ├── quizModel.js
│   │   └── userModel.js
│   │
│   ├── routes
│   │   ├── aiRoutes.js
│   │   ├── annotationRoutes.js
│   │   ├── authRoutes.js
│   │   ├── communityRoutes.js
│   │   ├── documentRoutes.js
│   │   ├── flashcardRoutes.js
│   │   ├── notificationRoutes.js
│   │   ├── progressRoutes.js
│   │   └── quizRoutes.js
│   │
│   ├── utils
│   │   ├── fixShareIds.js
│   │   ├── geminiService.js
│   │   ├── migrateFlashcardReviewed.js
│   │   ├── notificationHelper.js
│   │   ├── pdfParser.js
│   │   └── textChunker.js
│   │
│   ├── server.js
│   ├── .env
│   └── package.json
│
└── frontend/memora-x
├── src
│   ├── assets
│   ├── components
│   │   ├── ai
│   │   ├── annotations
│   │   ├── auth
│   │   ├── chat
│   │   ├── common
│   │   ├── community
│   │   ├── dashboard
│   │   ├── documents
│   │   ├── flashcards
│   │   ├── layout
│   │   └── quizzes
│   │
│   ├── context
│   │   └── AuthContext.jsx
│   │
│   ├── pages
│   │   ├── Auth
│   │   ├── Community
│   │   ├── Dashboard
│   │   ├── Documents
│   │   ├── FlashCards
│   │   ├── Profile
│   │   ├── Quizzes
│   │   ├── LandingPage.jsx
│   │   └── NotFoundPage.jsx
│   │
│   ├── services
│   │   ├── aiService.js
│   │   ├── annotationService.js
│   │   ├── authService.js
│   │   ├── communityService.js
│   │   ├── documentService.js
│   │   ├── flashcardService.js
│   │   ├── notificationService.js
│   │   ├── progressService.js
│   │   └── quizService.js
│   │
│   ├── utils
│   │   ├── apiPaths.js
│   │   ├── axiosInstance.js
│   │   └── timeAgo.js
│   │
│   ├── App.jsx
│   ├── main.jsx
│   └── index.css
│
├── .env
├── tailwind.config.js
├── vite.config.js
└── package.json
```

---

## ⚙️ Environment Variables

### 📦 Backend `.env`
```
PORT=8000
MONGO_URI=your_mongodb_connection_string

JWT_SECRET=your_secret_key
JWT_EXPIRE=7d

NODE_ENV=development

GEMINI_API_KEY=your_gemini_api_key

MAX_FILE_SIZE=10485760

CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret
```

---

### 🌐 Frontend `.env`
```
VITE_API_BASE_URL=http://localhost:8000
```

---

## 🧪 Running Locally

### Backend
```
cd backend
npm install
npm run dev
```

---

### Frontend
```
cd frontend/memora-x
npm install
npm run dev
```

---

## 🔮 Future Improvements

- Spaced repetition algorithm
- AI study recommendations
- Real-time collaboration
- Advanced analytics (AI insights)
- Mobile app

---

## 📄 License

This project is for educational and development purposes.
