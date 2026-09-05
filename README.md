# Healthcare Management System

A role-based healthcare platform where patients book appointments with doctors, doctors manage their schedule and availability, and admins run the whole operation — specialities, doctor onboarding, and appointment oversight.

## Live demo

[healthcare-website-y0yg.onrender.com](https://healthcare-website-y0yg.onrender.com)

## What it does

- Patients browse doctors by speciality, book and cancel appointments, and pay online via **Razorpay**
- Doctors get their own dashboard: set availability, view their schedule, manage notifications
- Admins manage specialities and doctor profiles (with image upload via **Cloudinary**), oversee all appointments, and can cancel on a patient's behalf
- Three separate JWT-authenticated roles (patient, doctor, admin/viewer) each with scoped access

## Stack

- **Frontend & Admin** — React, Tailwind CSS, React Router, AOS (scroll animations)
- **Backend** — Node.js, Express, MongoDB (Mongoose)
- **Auth** — Role-based JWT (separate middleware per role)
- **Payments** — Razorpay
- **Media** — Cloudinary
- **Deployment** — Render

## Project structure

```
├── frontend/   # Patient-facing app (React + Tailwind)
├── admin/      # Admin & doctor dashboard (React + Tailwind)
└── backend/    # Express API — auth, appointments, specialities, payments
    ├── controllers/
    ├── models/
    ├── routes/
    └── middlewares/
```

## API

| Method | Route | Description |
|---|---|---|
| POST | `/api/user/register` | Register a patient |
| POST | `/api/user/login` | Patient login |
| GET | `/api/user/get-profile` | Get patient profile |
| POST | `/api/user/update-profile` | Update profile |
| GET | `/api/user/all-specialities` | List specialities |
| POST | `/api/user/book-appointment` | Book an appointment |
| GET | `/api/user/appointments` | List a patient's appointments |
| POST | `/api/user/cancel-appointment` | Cancel an appointment |
| POST | `/api/user/payment-razorpay` | Create Razorpay order |
| POST | `/api/user/verify-payment` | Verify payment |
| POST | `/api/doctor/login` | Doctor login |
| GET | `/api/doctor/list` | List all doctors |
| GET | `/api/doctor/doctor-dashboard` | Doctor's dashboard data |
| POST | `/api/doctor/change-availability` | Toggle availability |
| POST | `/api/admin/login` | Admin login |
| GET | `/api/admin/dashboard` | Admin dashboard data |
| POST | `/api/admin/add-doctor` | Add a doctor |
| POST | `/api/admin/add-speciality` | Add a speciality |
| GET | `/api/admin/appointments` | All appointments |
| POST | `/api/admin/cancel-appointment` | Cancel an appointment (admin) |

## Getting started

```bash
cd backend && npm install && npm run dev
cd ../frontend && npm install && npm run dev
cd ../admin && npm install && npm run dev
```

Backend `.env`:

```
PORT=
MONGODB_URI=
JWT_SECRET=
RAZORPAY_KEY_ID=
RAZORPAY_KEY_SECRET=
CLOUDINARY_CLOUD_NAME=
CLOUDINARY_API_KEY=
CLOUDINARY_API_SECRET=
```

## Author

Atishay Jain — atishayjain8807@gmail.com
