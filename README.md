# 🎉 EventHub — College Event Discovery & Registration Platform

A full-stack, responsive web application for managing campus events, hackathons, seminars, and workshops.

## 🌟 Key Features

1. **Authentication & Role-Based Authorization**
   - **Student**: Discover events, filter by categories, register with 1-click, view & cancel registrations in *My Registrations*.
   - **Organizer**: Create events, edit details, track capacities, and inspect real-time participant rosters.
   - **Admin**: System-wide dashboard, moderation control, view all users and delete inappropriate events.
   - **1-Click Demo Logins**: Instant evaluator access buttons for Student, Organizer, and Admin on the Login & Landing pages.

2. **Capacity & Duplicate Prevention**
   - Prevents duplicate registrations by the same student.
   - Live seat counter (`availableSeats = capacity - registeredCount`).
   - Automatically disables registration with "Event Full" once maximum limit is reached.

3. **Dual-Mode Zero-Setup Database Engine**
   - Seamlessly uses **MongoDB** if `MONGODB_URI` is set.
   - Automatically falls back to persistent, local JSON storage if no MongoDB instance is running, guaranteeing instant execution on any system without configuration.

---

## 🚀 Quick Start Guide

### 1. Run the Full Application (Single Command)
From the project root (`eventhub`):
```bash
npm start
```
Then open your browser at **http://localhost:5000**! The server serves both the Express REST API and the built React web application.

---

### 2. Run in Development Mode (with Hot-Reload)
In one terminal (Backend):
```bash
cd server
npm start
```

In a second terminal (Frontend Vite Dev Server):
```bash
cd client
npm run dev
```
Frontend dev server will be live at **http://localhost:5173** with instant HMR and automatic API proxy to port 5000.

---

### 3. Run Automated Tests
Verify all 21 test assertions covering JWT auth, event creation, search, registration, duplicate checks, and capacity enforcement:
```bash
npm test
```

---

## 🔑 Pre-Configured Demo Credentials

| Role | Email | Password | Quick Action |
| :--- | :--- | :--- | :--- |
| **👩‍🎓 Student** | `student@eventhub.edu` | `password123` | Discover events & register |
| **👨‍💼 Organizer** | `organizer@eventhub.edu` | `password123` | Create events & view rosters |
| **🛡️ Admin** | `admin@eventhub.edu` | `password123` | View all users & system stats |

*(Or click the 1-click demo buttons on the landing page/login screen)*

---

## 🎬 Recommended 3-Minute Demo Walkthrough

1. Open **http://localhost:5000**.
2. Click **"👨‍💼 Organizer Demo"** on the hero banner.
3. In the Organizer Portal, click **"+ Create New Event"**:
   - Title: `AI Workshop: Hands-on Deep Learning`
   - Category: `Workshop`
   - Date: `2026-10-30`
   - Time: `10:00 AM`
   - Venue: `Lab 4, Tech Block`
   - Capacity: `30`
4. Click **Create Event**. It immediately appears in your managed events table.
5. In the top navbar, log out and click **"👩‍🎓 Student Demo"**.
6. Navigate to **Events** and type `AI Workshop` into the search bar.
7. Click **View Details** on the AI Workshop card.
8. Click **Register for Event**. See the instant success confirmation and badge change to **"Already Registered"** with seats updated to 29.
9. Click **My Registrations** in the navbar to confirm it is listed under the student's confirmed events.
10. Log back in as **Organizer** and click **"Participants (1)"** on the AI Workshop to view the student's name, email, and registration timestamp!