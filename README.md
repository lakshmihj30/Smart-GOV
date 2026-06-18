# Smart GOV 🏛️

A citizen-facing web portal that simplifies access to Indian government services and document procedures. Smart GOV provides step-by-step guidance, official links, FAQs, and instructional videos for nine major government documents and registrations — all behind a secure, authenticated interface.

---

## Overview

Smart GOV is a full-stack web application built to bridge the gap between citizens and complex government processes. Instead of navigating multiple official portals, users can log in once and access clear, consolidated guidance for documents like Aadhaar, PAN, Passport, Driving License, and more.

The tagline: **"Navigating the Future with Innovation"**

---

## Features

- **User Authentication** — Secure registration and login with JWT tokens (1-hour expiry)
- **Protected Routes** — All service pages are accessible only to logged-in users
- **Multi-language Support** — Google Translate integration for English, Hindi, Kannada, Telugu, and Tamil
- **Personalized Header** — Displays the logged-in user's first name fetched from the backend
- **9 Government Service Guides** — Step-by-step instructions with official links, FAQs, and embedded YouTube videos
- **Responsive UI** — Built with Bootstrap 5 and Material UI for a clean, accessible layout
- **Smooth Navigation** — React Router v7 with conditional header rendering (hidden on login/signup)

---

## Tech Stack

### Frontend
| Technology | Purpose |
|---|---|
| React 18 | UI framework |
| React Router DOM v7 | Client-side routing |
| Axios | HTTP requests to backend |
| Bootstrap 5 | Responsive layout and styling |
| Material UI (MUI) v6 | UI components |
| React Icons | Icon library (profile icon etc.) |
| Google Translate Widget | Multi-language support |

### Backend
| Technology | Purpose |
|---|---|
| Node.js + Express | REST API server |
| MongoDB + Mongoose | Database and ODM |
| bcrypt | Password hashing |
| JSON Web Token (JWT) | Stateless authentication |
| CORS | Cross-origin request handling |
---

### Prerequisites

- **Node.js** v16 or higher
- **MongoDB** running locally on port `27017`
- **npm** (comes with Node.js)

---

### Backend Setup

```bash
# Navigate to the backend folder
cd "Smart GOV/backend"

# Install dependencies
npm install

# Start the server
node server.js
```

The backend runs on **http://localhost:5000**.

**API Endpoints:**

| Method | Endpoint | Description | Auth Required |
|---|---|---|---|
| POST | `/register` | Register a new user | No |
| POST | `/login` | Login and receive JWT | No |
| GET | `/protected` | Test protected access | Yes (JWT) |
| GET | `/user/name` | Fetch logged-in user's first name | Yes (JWT) |

---

### Frontend Setup

```bash
# Navigate to the frontend folder
cd "Smart GOV/my-app"

# Install dependencies
npm install

# Start the development server
npm start
```

The frontend runs on **http://localhost:3000**.

On first load, you will be redirected to `/user/login`. After logging in, you will land on `/home`.

---

## Supported Government Services

Each service page includes: step-by-step application instructions, required documents, official portal links, an embedded YouTube tutorial, and an FAQ section.

| Service | Official Portal |
|---------|----------------|
| Aadhaar Card | [UIDAI](https://uidai.gov.in) |
| PAN Card | [NSDL](https://nsdl.co.in), [UTIITSL](https://www.utiitsl.com) |
| Driving License | RTO Portals |
| Voter ID | [NVSP](https://www.nvsp.in) |
| Vehicle Registration | [Karnataka Transport](https://transport.karnataka.gov.in), [MoRTH](https://morth.nic.in) |
| Passport | [Passport India](https://portal1.passportindia.gov.in) |
| Land Registration | State Portals |
| Income Tax | Income Tax Portal |
| Business Registration | MCA / Startup India |

---

## Environment Notes

- The backend MongoDB URI is hardcoded to `mongodb://localhost:27017/authDB`. For production, replace this with an environment variable (e.g., using `dotenv`).
- The JWT secret is currently a plain string `"secretKey"`. Replace with a strong secret stored in an environment variable before deploying.
- The frontend API base URL is hardcoded to `http://localhost:5000`. For production builds, use an `.env` file with `REACT_APP_API_URL`.

Example `.env` for the frontend:
```
REACT_APP_API_URL=http://localhost:5000
```
