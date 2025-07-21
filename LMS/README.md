# Learning Management System (LMS)

## Overview

This is a full-featured Learning Management System (LMS) built with a modern tech stack. The platform allows instructors to create and manage courses, while students can browse, purchase, and learn from these courses. The application features a dual interface for both instructors and students with secure authentication and payment processing.

## Features

### For Instructors
- **Course Management**: Create, edit, and manage courses
- **Content Upload**: Upload video lectures with support for free previews
- **Revenue Tracking**: Monitor student enrollments and revenue
- **Dashboard**: View analytics on course performance and student engagement

### For Students
- **Course Discovery**: Browse and filter courses by category, level, and language
- **Course Preview**: Watch free preview lectures before purchasing
- **Secure Payments**: Purchase courses using PayPal integration
- **Learning Progress**: Track progress through course lectures
- **Course Library**: Access purchased courses anytime

## Tech Stack

### Frontend (Client)
- **React**: UI library for building the user interface
- **React Router**: For navigation and routing
- **Context API**: For state management
- **Tailwind CSS**: For styling and UI components
- **Axios**: For API requests
- **React Player**: For video playback

### Backend (Server)
- **Node.js**: JavaScript runtime
- **Express**: Web framework
- **MongoDB**: NoSQL database
- **Mongoose**: ODM for MongoDB
- **JWT**: For authentication
- **Cloudinary**: For media storage and streaming
- **PayPal SDK**: For payment processing

## Project Structure

### Client
```
client/
├── public/            # Static files
├── src/
│   ├── api/           # API configuration
│   ├── components/     # Reusable components
│   │   ├── common-form/
│   │   ├── instructor-view/
│   │   ├── student-view/
│   │   ├── ui/         # UI components
│   │   └── video-player/
│   ├── config/         # Configuration files
│   ├── context/        # Context providers
│   │   ├── auth-context/
│   │   ├── instructor-context/
│   │   └── student-context/
│   ├── hooks/          # Custom hooks
│   ├── lib/            # Utility functions
│   ├── pages/          # Page components
│   │   ├── auth/
│   │   ├── instructor/
│   │   └── student/
│   └── services/       # API service functions
```

### Server
```
server/
├── controllers/       # Request handlers
│   ├── auth-controller/
│   ├── instructor-controller/
│   └── student-controller/
├── helpers/           # Helper functions
├── middleware/        # Express middleware
├── models/            # Mongoose models
├── routes/            # API routes
│   ├── auth-routes/
│   ├── instructor-routes/
│   └── student-routes/
└── server.js          # Entry point
```

## Setup Instructions

### Prerequisites
- Node.js (v14 or higher)
- MongoDB
- Cloudinary account
- PayPal Developer account

### Environment Variables

#### Server (.env)
```
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
CLIENT_URL=http://localhost:5173

CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_API_SECRET=your_cloudinary_api_secret

PAYPAL_CLIENT_ID=your_paypal_client_id
PAYPAL_SECRET_ID=your_paypal_secret_id
```

### Installation

1. Clone the repository
```bash
git clone <repository-url>
cd LMS
```

2. Install dependencies for server
```bash
cd server
npm install
```

3. Install dependencies for client
```bash
cd ../client
npm install
```

4. Start the server
```bash
cd ../server
npm run dev
```

5. Start the client
```bash
cd ../client
npm run dev
```

## API Endpoints

### Authentication
- `POST /auth/register` - Register a new user
- `POST /auth/login` - Login a user
- `GET /auth/check-auth` - Check authentication status

### Instructor Courses
- `POST /instructor/course/add` - Add a new course
- `GET /instructor/course/get` - Get all instructor courses
- `GET /instructor/course/get/details/:id` - Get course details
- `PUT /instructor/course/update/:id` - Update a course

### Media
- `POST /media/upload` - Upload media file
- `POST /media/bulk-upload` - Upload multiple media files
- `DELETE /media/delete/:id` - Delete media file

### Student Courses
- `GET /student/course/get` - Get all courses with filters
- `GET /student/course/get/details/:id` - Get course details
- `GET /student/course/purchase-info/:id/:studentId` - Check purchase status

### Orders
- `POST /student/order/create` - Create a new order
- `POST /student/order/capture` - Capture payment and finalize order

### Course Progress
- `GET /student/course-progress/get/:userId/:courseId` - Get course progress
- `POST /student/course-progress/mark-lecture-viewed` - Mark lecture as viewed
- `POST /student/course-progress/reset-progress` - Reset course progress

## Author
Abhinav Mishra