#  Flux Learn (Learning Management System)

A modern, full-featured Learning Management System that empowers instructors to create and manage online courses while enabling students to discover, purchase, and learn from those courses.

---

##  Features

### 👨‍🏫 For Instructors
- Create and manage courses
- Upload and preview video lectures
- Track enrollments and revenue
- Analytics dashboard for course insights

### 👨‍🎓 For Students
- Browse courses by filters like category, level, and language
- Watch free course previews
- Secure course purchase via PayPal
- Track learning progress across all enrolled courses
- Lifetime access to purchased content

---

##  Tech Stack

### Frontend
- **React**: Component-based UI
- **React Router**: Navigation & routing
- **Tailwind CSS**: Utility-first CSS framework
- **Context API**: Global state management
- **Axios**: HTTP client
- **React Player**: Video playback

### Backend
- **Node.js + Express**: Server-side logic
- **MongoDB + Mongoose**: NoSQL database with schema modeling
- **JWT**: Authentication with tokens
- **Cloudinary**: Media storage and streaming
- **PayPal SDK**: Payment gateway integration

---

## 📁 Folder Structure

### Client (`/client`)
```
client/
├── public/
├── src/
│   ├── api/               # API configs
│   ├── components/
│   │   ├── common-form/
│   │   ├── instructor-view/
│   │   ├── student-view/
│   │   ├── ui/
│   │   └── video-player/
│   ├── config/
│   ├── context/
│   │   ├── auth-context/
│   │   ├── instructor-context/
│   │   └── student-context/
│   ├── hooks/
│   ├── lib/
│   ├── pages/
│   │   ├── auth/
│   │   ├── instructor/
│   │   └── student/
│   └── services/
```

### Server (`/server`)
```
server/
├── controllers/
│   ├── auth-controller/
│   ├── instructor-controller/
│   └── student-controller/
├── helpers/
├── middleware/
├── models/
├── routes/
│   ├── auth-routes/
│   ├── instructor-routes/
│   └── student-routes/
└── server.js
```

---

## ⚙️ Environment Setup

### Prerequisites
- Node.js (v14+)
- MongoDB (local or Atlas)
- Cloudinary account
- PayPal Developer account

### Environment Variables (`/server/.env`)
```
PORT=5000
MONGO_URI=your_mongodb_uri
JWT_SECRET=your_jwt_secret
CLIENT_URL=http://localhost:5173

CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_API_SECRET=your_cloudinary_api_secret

PAYPAL_CLIENT_ID=your_paypal_client_id
PAYPAL_SECRET_ID=your_paypal_secret
```

---

## 🧑‍💻 Installation Guide

1. **Clone the repository**
```bash
git clone <repo-url>
cd LMS
```

2. **Install backend dependencies**
```bash
cd server
npm install
```

3. **Install frontend dependencies**
```bash
cd ../client
npm install
```

4. **Run backend server**
```bash
cd ../server
npm run dev
```

5. **Run frontend**
```bash
cd ../client
npm run dev
```

---

## 📡 API Endpoints

### 🔐 Authentication
- `POST /auth/register` – Register a user
- `POST /auth/login` – User login
- `GET /auth/check-auth` – Validate session

### 🎓 Instructor APIs
- `POST /instructor/course/add` – Create course
- `GET /instructor/course/get` – Get instructor's courses
- `GET /instructor/course/get/details/:id` – Course details
- `PUT /instructor/course/update/:id` – Update course

### 📦 Media APIs
- `POST /media/upload` – Upload single media
- `POST /media/bulk-upload` – Upload multiple files
- `DELETE /media/delete/:id` – Delete media file

### 🧑‍🎓 Student APIs
- `GET /student/course/get` – List all courses
- `GET /student/course/get/details/:id` – Get course details
- `GET /student/course/purchase-info/:id/:studentId` – Check purchase status

### 💳 Orders & Payments
- `POST /student/order/create` – Create order
- `POST /student/order/capture` – Capture PayPal payment

### 📈 Course Progress
- `GET /student/course-progress/get/:userId/:courseId` – Fetch course progress
- `POST /student/course-progress/mark-lecture-viewed` – Mark lecture as completed
- `POST /student/course-progress/reset-progress` – Reset progress

---
