# 🚗 DriveEase — MERN Stack Car Rental App

A full-stack car rental platform built with MongoDB, Express, React, and Node.js.

---

## 📁 Project Structure

```
car-rental/
├── backend/          # Express + MongoDB API
│   ├── config/       # DB seed
│   ├── controllers/  # Route logic
│   ├── middleware/   # JWT auth
│   ├── models/       # Mongoose schemas
│   ├── routes/       # API routes
│   ├── server.js
│   └── .env
└── frontend/         # React app
    └── src/
        ├── components/
        ├── context/
        ├── pages/
        └── utils/
```

---

## ⚡ Quick Start

### Prerequisites
- Node.js v16+
- MongoDB running locally (`mongod`) OR a MongoDB Atlas connection string

---

### 1. Backend Setup

```bash
cd backend
npm install
```

Edit `.env` — update `MONGO_URI` if using Atlas:
```
MONGO_URI=mongodb://localhost:27017/carrental
JWT_SECRET=your_secret_key
PORT=5000
```

Seed the database with sample cars + admin user:
```bash
npm run seed
```

Start the backend:
```bash
npm run dev
```

Backend runs at: **http://localhost:5000**

---

### 2. Frontend Setup

```bash
cd frontend
npm install
npm start
```

Frontend runs at: **http://localhost:3000**

---

## 🔑 Demo Credentials (after seeding)

| Role  | Email                    | Password   |
|-------|--------------------------|------------|
| Admin | admin@carrental.com      | admin123   |
| User  | john@example.com         | admin123   |

---

## 🌐 Pages & Routes

### User
| Route            | Description          |
|------------------|----------------------|
| `/`              | Home page            |
| `/cars`          | Browse all cars      |
| `/cars/:id`      | Car details          |
| `/book/:id`      | Book a car           |
| `/pay/:id`       | Payment page         |
| `/my-bookings`   | User's bookings      |
| `/bookings/:id`  | Booking detail       |
| `/account`       | Profile settings     |
| `/contact`       | Contact form         |
| `/login`         | Login                |
| `/signup`        | Register             |

### Admin (`/admin/*`)
| Route               | Description       |
|---------------------|-------------------|
| `/admin`            | Dashboard stats   |
| `/admin/cars`       | Manage fleet      |
| `/admin/bookings`   | All bookings      |
| `/admin/messages`   | Customer messages |
| `/admin/users`      | User management   |

---

## 🔧 API Endpoints

### Auth
- `POST /api/auth/register`
- `POST /api/auth/login`
- `GET  /api/auth/profile` *(protected)*
- `PUT  /api/auth/profile` *(protected)*

### Cars
- `GET    /api/cars`
- `GET    /api/cars/:id`
- `POST   /api/cars` *(admin)*
- `PUT    /api/cars/:id` *(admin)*
- `DELETE /api/cars/:id` *(admin)*

### Bookings
- `POST /api/bookings` *(protected)*
- `GET  /api/bookings/my` *(protected)*
- `GET  /api/bookings/:id` *(protected)*
- `PUT  /api/bookings/:id/pay` *(protected)*
- `PUT  /api/bookings/:id/cancel` *(protected)*
- `GET  /api/bookings` *(admin)*
- `PUT  /api/bookings/:id/status` *(admin)*

### Messages
- `POST   /api/messages`
- `GET    /api/messages` *(admin)*
- `PUT    /api/messages/:id/read` *(admin)*
- `DELETE /api/messages/:id` *(admin)*

### Admin
- `GET    /api/admin/stats` *(admin)*
- `GET    /api/admin/users` *(admin)*
- `DELETE /api/admin/users/:id` *(admin)*

---

## 🛠 Tech Stack

| Layer     | Technology                    |
|-----------|-------------------------------|
| Frontend  | React 18, React Router 6      |
| Styling   | Plain CSS with CSS variables  |
| Backend   | Node.js, Express 4            |
| Database  | MongoDB + Mongoose            |
| Auth      | JWT + bcryptjs                |
| Toasts    | react-toastify                |
