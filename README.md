# Roadmap

A collection of personal and experimental projects, each designed to explore a specific stack, technology, or product idea. Includes project goals, chosen stack, and a short description of intended flow/architecture.

---

## ✅ ToDoList
- **Repo:** [github.com/gasbrieo/todolist](https://github.com/gasbrieo/todolist)
- **Goal:** Learn Supabase + TanStack Stack (Query, Router, Form) in a real-world SPA
- **Stack:** React, Vite, Supabase, TanStack, shadcn/ui, Clerk, Zod
- **Flow:** User signs up with Clerk, tasks are stored per-user using Supabase RLS. TanStack Query handles data loading and mutations. Notifications on actions via toast. Clean separation of components and logic.

---

## ✅ React UI
- **Repo:** [github.com/gasbrieo/react-ui](https://github.com/gasbrieo/react-ui)
- **Goal:** Build a reusable UI component system using shadcn/ui and Tailwind
- **Stack:** React, Tailwind CSS, shadcn/ui, Storybook, TypeScript
- **Flow:** Components are documented via Storybook with variants and interactive controls. Acts as a base for all other projects. Focus on composability, accessibility, and documentation-first development.

---

## 🔐 IdentityForge
- **Goal:** Build a complete user management and authentication system from scratch
- **Stack:** React SPA, shadcn/ui, TanStack Form, .NET Web API, PostgreSQL, JWT
- **Flow:** Users can register and log in via email/password, Google, or GitHub. All logic (login, OAuth, tokens, password recovery, email confirmation) is handled by the backend using Microsoft Identity. Frontend uses TanStack Form + Zod for form validation and calls the backend API directly. JWTs are used for protected routes. Future: admin interface for user roles, audit logs, and 2FA support.

---

## 🛠️ PayTrack
- **Goal:** Track bills with due dates, "mark as paid", and alert users before expiration
- **Stack:** React + Vite, TanStack, Clerk, shadcn/ui, .NET Web API backend, PostgreSQL
- **Flow:** User logs in with Clerk, adds bills with name, value, due date. Can mark them as paid. Alerts appear if a bill is due and not yet paid. Backend in .NET handles all business logic and schedules. Future: notification system or dashboard charts.

---

## 📱 Reminder *(Flutter-only)*
- **Goal:** App to schedule recurring reminders (e.g., "every Monday at 18h: study X")
- **Stack:** Flutter + Dart, Hive/Isar, flutter_local_notifications
- **Flow:** User defines weekly reminders (weekday + time + message). Stored locally with Hive/Isar. Notifications triggered locally on device. Lightweight and offline-friendly.

---

## 📦 Flashcards UI
- **Goal:** Build a real flashcard SPA with flip animation, answer tracking, markdown rendering, and Supabase persistence
- **Stack:** React + Vite, shadcn/ui, Zustand or TanStack Form, Supabase (Auth + DB), react-markdown, optional KaTeX
- **Flow:** User logs in via Supabase Auth. Can create decks and cards with markdown-based content. Each card can be flipped to reveal the answer. Cards are loaded from Supabase per user. User can mark answers as correct/incorrect. Markdown supports code, lists, titles, etc. Supabase RLS ensures secure access. Future: spaced repetition, tags, or AI-generated cards.

---

## 🔍 ScanGrade
- **Goal:** User exports a multiple-choice test, prints and completes it on paper, then scans it via OCR and QR code to auto-correct
- **Stack:** Flutter (mobile app), Python (OCR with EasyOCR or Tesseract), QR code for test ID, optional backend to link test definitions
- **Flow:** User creates a test in-app, exports a printable sheet with questions, answers, and embedded QR code. After answering on paper, user scans the sheet via camera. QR code identifies which test, and OCR reads marked answers. Python backend matches answers to correct ones and calculates result. Optionally displays score, breakdown, and exports report. Syncs with backend to handle offline scenarios and update status.

---

## ⚙️ DotNetUtils
- **Goal:** Reusable .NET library (e.g., recurrence engine, date utilities, validation logic)
- **Stack:** C# / .NET 8+, xUnit, NuGet
- **Flow:** Developed as a standalone package with unit tests and CI for publishing to NuGet. May support scenarios like date recurrence logic used in Reminder or bill validation logic used in PayTrack.

---

## 🧪 FlutterUtils
- **Goal:** Reusable widget or logic package (e.g., flashcard flip, spaced repetition logic)
- **Stack:** Flutter + Dart
- **Flow:** Components abstracted into a Dart package. Possible uses: flip animations, layout wrappers, simple SRS (spaced repetition system) core. Published via pub.dev for reuse in future Flutter projects.

---

## 🎵 Playlist Organizer AI
- **Goal:** Analyze and classify songs from a disorganized playlist based on patterns learned from curated playlists using AI
- **Stack:** Node.js or Python (backend), Spotify Web API, OpenAI API or embedding-based model, optional React frontend
- **Flow:**
  - User authenticates or provides public playlist URLs (organized and disorganized)
  - Backend fetches track data and optionally audio features
  - AI receives track names and artists from the disorganized playlist and matches them against categories learned from the organized playlists (e.g., "correndo", "voando")
  - Response suggests which playlist each song belongs to, or creates a new label if needed
  - Output format is a clean JSON mapping song → playlist
  - Future: interface to drag/drop or auto-move songs via Spotify API
