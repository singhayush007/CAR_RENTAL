# 🚗 CarRental — Full-Stack Car Rental Platform

<div align="center">

![GitHub stars](https://img.shields.io/github/stars/singhayush007/CAR_RENTAL?style=flat-square)
![GitHub forks](https://img.shields.io/github/forks/singhayush007/CAR_RENTAL?style=flat-square)
![GitHub issues](https://img.shields.io/github/issues/singhayush007/CAR_RENTAL?style=flat-square)
![License](https://img.shields.io/badge/license-MIT-green?style=flat-square)
![Made with React](https://img.shields.io/badge/Stack-React_19_+_Node.js-61DAFB?style=flat-square&logo=react&logoColor=white)

**A production-ready full-stack car rental platform built with React 19, Node.js, Express, MongoDB, JWT Auth, and ImageKit.**

[🐛 Report Bug](https://github.com/singhayush007/CAR_RENTAL/issues) · [✨ Request Feature](https://github.com/singhayush007/CAR_RENTAL/issues)

</div>

---

## 📸 Screenshot

<div align="center">
  <img src="/client/public/car-rental.png" alt="CarRental Screenshot" width="100%" style="border-radius: 12px; border: 1px solid #e5e7eb;" />
</div>

---

## 📋 Table of Contents

- [About](#-about)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Folder Structure](#️-folder-structure)
- [Getting Started](#-getting-started)
- [Environment Variables](#-environment-variables)
- [Running the App](#️-running-the-app)
- [Deployment](#️-deployment)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🧠 About

**CarRental** is a full-stack car rental platform where users can browse available cars, book them for specific date ranges, and manage their bookings. Car owners can list their vehicles, manage availability, and track bookings through a dedicated owner dashboard. Built with a modern React frontend and a Node.js/Express backend, it uses JWT for authentication, MongoDB for data storage, and ImageKit for optimized media uploads.

---

## ✨ Features

- 🔐 **JWT Authentication** — Secure register/login with bcrypt password hashing and token-based auth
- 🚗 **Browse Cars** — Explore all available cars with location, fuel type, transmission, and pricing details
- 📅 **Date-Based Booking** — Pick up and return date selection with real-time availability checking
- 💳 **Auto Price Calculation** — Total price auto-calculated based on number of rental days
- 👤 **User Dashboard** — View and manage all personal bookings with status tracking
- 🏠 **Owner Dashboard** — Full analytics: total cars, bookings, revenue, and recent activity
- 🚘 **Car Management** — Add, remove, and toggle availability of listed cars
- 📋 **Booking Management** — Owners can confirm or cancel incoming booking requests
- 🖼️ **ImageKit Uploads** — Optimized image uploads with WebP conversion and auto-compression
- 📍 **Location Filter** — Search cars by pickup location and date range
- 👑 **Role System** — Users can upgrade to owner role to start listing cars
- ☁️ **Vercel Ready** — Both client and server configured for Vercel deployment

---

## 🛠 Tech Stack

| Category | Technology |
|----------|-----------|
| Frontend Framework | React 19 |
| Routing | React Router DOM v7 |
| State Management | React Context API |
| Backend | Node.js + Express 5 |
| Database | MongoDB + Mongoose |
| Authentication | JWT + bcrypt |
| Media Storage | ImageKit |
| File Uploads | Multer |
| Styling | Tailwind CSS v4 |
| Animations | Motion (Framer Motion) |
| Notifications | React Hot Toast |
| Build Tool | Vite 6 |
| Deployment | Vercel |

---

## 🗂️ Folder Structure

```
car-rental-fullstack/
│
├── client/                          # React frontend (Vite)
│   ├── public/
│   │   └── car-rental.png           # App screenshot / OG image
│   ├── src/
│   │   ├── assets/                  # SVG icons, images, assets.js barrel
│   │   ├── components/              # Reusable UI components
│   │   │   ├── Banner.jsx           # Promotional banner section
│   │   │   ├── CarCard.jsx          # Car listing card
│   │   │   ├── FeaturedSection.jsx  # Featured cars on homepage
│   │   │   ├── Footer.jsx           # Site footer
│   │   │   ├── Hero.jsx             # Hero section with search
│   │   │   ├── Loader.jsx           # Loading spinner
│   │   │   ├── Login.jsx            # Auth modal (login/register)
│   │   │   ├── Navbar.jsx           # Top navigation bar
│   │   │   ├── Newsletter.jsx       # Email subscription section
│   │   │   ├── Testimonial.jsx      # Customer reviews section
│   │   │   ├── Title.jsx            # Section title component
│   │   │   └── owner/
│   │   │       ├── NavbarOwner.jsx  # Owner panel top nav
│   │   │       ├── Sidebar.jsx      # Owner panel sidebar
│   │   │       └── Title.jsx        # Owner panel section title
│   │   ├── context/
│   │   │   └── AppContext.jsx       # Global state (auth, cars, dates)
│   │   ├── pages/                   # Route-level page components
│   │   │   ├── Home.jsx             # Landing page
│   │   │   ├── Cars.jsx             # All cars listing with filters
│   │   │   ├── CarDetails.jsx       # Single car detail + booking form
│   │   │   ├── MyBookings.jsx       # User's booking history
│   │   │   └── owner/
│   │   │       ├── Layout.jsx       # Owner panel shell
│   │   │       ├── Dashboard.jsx    # Owner analytics & stats
│   │   │       ├── AddCar.jsx       # Add new car listing
│   │   │       ├── ManageCars.jsx   # View/toggle/delete cars
│   │   │       └── ManageBookings.jsx # View/confirm/cancel bookings
│   │   ├── App.jsx                  # Routes definition
│   │   ├── main.jsx                 # App entry point
│   │   └── index.css                # Global styles + Tailwind
│   ├── .env                         # Frontend env vars
│   ├── index.html
│   ├── vite.config.js
│   ├── vercel.json
│   └── package.json
│
└── server/                          # Node.js + Express backend
    ├── configs/
    │   ├── db.js                    # MongoDB connection
    │   ├── imageKit.js              # ImageKit client init
    │   └── multer.js (if present)   # Multer disk storage config
    ├── controllers/
    │   ├── userController.js        # Register, login, get user, get cars
    │   ├── ownerController.js       # Add car, manage cars, dashboard, image upload
    │   └── bookingController.js     # Create booking, check availability, manage status
    ├── middleware/
    │   ├── auth.js                  # JWT verification middleware
    │   └── multer.js                # File upload middleware
    ├── models/
    │   ├── User.js                  # User schema (name, email, password, role)
    │   ├── Car.js                   # Car schema (brand, model, price, location...)
    │   └── Booking.js               # Booking schema (car, user, owner, dates, status)
    ├── routes/
    │   ├── userRoutes.js            # /api/user/*
    │   ├── ownerRoutes.js           # /api/owner/*
    │   └── bookingRoutes.js         # /api/bookings/*
    ├── server.js                    # Express app entry point
    ├── .env                         # Backend env vars
    ├── vercel.json
    └── package.json
```

---

## 🚀 Getting Started

### Prerequisites

- Node.js 18+
- npm
- A [MongoDB Atlas](https://mongodb.com/atlas) cluster
- An [ImageKit](https://imagekit.io) account

### 1. Clone the repository

```bash
git clone https://github.com/singhayush007/CAR_RENTAL.git
cd CAR_RENTAL
```

### 2. Install dependencies

```bash
# Install server dependencies
cd server && npm install

# Install client dependencies
cd ../client && npm install
```

### 3. Configure environment variables

Fill in the `.env` files for both `server/` and `client/` (see [Environment Variables](#-environment-variables) below).

### 4. Whitelist your IP on MongoDB Atlas

Go to **MongoDB Atlas → Network Access → Add IP Address** and add your current IP, or use `0.0.0.0/0` for open access during development.

### 5. Run the app

```bash
# Terminal 1 — Backend
cd server && npm run server

# Terminal 2 — Frontend
cd client && npm run dev
```

Open [http://localhost:5173](http://localhost:5173) to view the app.

---

## 🔐 Environment Variables

### `server/.env`

```env
# MongoDB
MONGODB_URI=mongodb+srv://<user>:<password>@cluster0.xxxxx.mongodb.net

# Auth
JWT_SECRET=your_jwt_secret_key

# ImageKit (use Standard keys, not Restricted)
IMAGEKIT_PUBLIC_KEY=public_...
IMAGEKIT_PRIVATE_KEY=private_...
IMAGEKIT_URL_ENDPOINT=https://ik.imagekit.io/your_id
```

### `client/.env`

```env
VITE_CURRENCY=$
VITE_BASE_URL=http://localhost:3000
```

---

## ▶️ Running the App

```bash
# Development (run in separate terminals)
cd server && npm run server       # Backend on :3000
cd client && npm run dev          # Frontend on :5173

# Production build (client)
cd client && npm run build

# Lint (client)
cd client && npm run lint
```

---

## ☁️ Deployment

Both `client/` and `server/` include a `vercel.json` for Vercel deployment.

1. Push your code to GitHub
2. Create two Vercel projects — one for `client/`, one for `server/`
3. Set the **Root Directory** to `client` or `server` respectively
4. Add all environment variables in each Vercel project's settings
5. Vercel auto-deploys on every push to `main`

> **Note:** For production, update `VITE_BASE_URL` in the client `.env` to your deployed server URL.

---

## 🤝 Contributing

Contributions are welcome! Please:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

---

## 📄 License

Distributed under the MIT License. See `LICENSE` for more information.

---

<div align="center">
  Built with ❤️ by <a href="https://github.com/singhayush007/CAR_RENTAL">Ayush Singh</a>
</div>
