# Mental Wellness Platform

## Overview
The Mental Wellness platform is a comprehensive solution designed to provide mental health support through personalized therapy, yoga and meditation resources, appointment scheduling, and communication with therapists and doctors. It consists of three main panels: Admin, Patient, and Doctor, each catering to the specific needs of its users. This system uses modern web technologies to ensure a seamless user experience and efficient backend operations.

## Tech Stack
- **Frontend**: React.js, Bootstrap
- **Backend**: Node.js, Express.js, MongoDB
- **Authentication**: JWT (JSON Web Tokens)
- **APIs**: RESTful APIs
- **Version Control**: GitHub

## Main Panels and Features

### 1. Admin Panel
**Features**:
- Manage Doctors:
  - Approve or reject doctor registration requests.
  - View and delete doctor profiles.
- Manage Patients:
  - Assign doctors to patients.
  - View patient profiles and their assigned doctors.
- Generate Reports:
  - View analytics and user statistics.
- Manage Threads:
  - Monitor discussion forums and delete inappropriate content.

### 2. Doctor Panel
**Features**:
- Manage Appointments:
  - View and accept/cancel upcoming appointments.
  - Create and manage available slots.
- Patient Management:
  - Access patient details and view their medical history.
  - Chat with patients for quick consultations.
- Dashboard:
  - View an overview of daily tasks and appointments.
  - Monitor performance through ratings and feedback.
- Discussion Forum:
  - Participate in community discussions to provide guidance.

### 3. Patient Panel
**Features**:
- Dashboard:
  - Track mood, sleep patterns, and therapy progress through the Activity Tracker and Progress Dashboard.
  - Access yoga and meditation resources.
- Appointment Management:
  - Schedule and manage appointments with doctors.
  - View upcoming and past appointments.
- Daily Journal:
  - Maintain a personal journal for mental health tracking.
- Chat:
  - Communicate directly with therapists.
- Educational Resources:
  - Access curated resources for mental health education.

## Backend Functionality
- **Authentication**: Role-based access control (Admin, Doctor, Patient) using JWT.
- **Database**: MongoDB for user profiles, appointments, and doctor-patient mappings.
- **API Endpoints**:
  - User Management (Registration, Login, Role Assignment)
  - Appointment Management (CRUD operations for appointments and slots)
  - Doctor-Patient Mappings
  - Thread Management for forums

## Getting Started
1. Clone the repository from GitHub.
2. Install dependencies:
   ```bash
   npm install
   ```
3. Set up environment variables in a `.env` file:
   ```env
   PORT=3000
   MONGO_URI=<your_mongo_db_connection_string>
   JWT_SECRET=<your_jwt_secret>
   EMAIL=<your_email>
   EMAIL_PASSWORD=<your_email_app_password>
   ```
4. Start the backend server:
   ```bash
   npm start
   ```
5. Set up the frontend's environment variable in `frontend/.env`:
   ```env
   REACT_APP_API_URL=http://localhost:3000
   ```
6. Start the frontend:
   ```bash
   cd frontend
   npm start
   ```
7. Access the application at `http://localhost:3001` (or whichever port React's dev server picks — the backend runs on 3000).

## Deployment

This app deploys as two separate services:

**Backend (Render, Railway, or similar):**
- Root directory: `backend`
- Build command: `npm install`
- Start command: `npm start`
- Environment variables: `MONGO_URI`, `JWT_SECRET`, `PORT`, `EMAIL`, `EMAIL_PASSWORD` (use a hosted MongoDB Atlas connection string, not `localhost`)

**Frontend (Vercel):**
- Root directory: `frontend`
- Environment variable: `REACT_APP_API_URL` set to your deployed backend's URL (e.g. `https://your-backend.onrender.com`)

The frontend reads `REACT_APP_API_URL` at build time and falls back to `http://localhost:3000` if unset, so local development works unchanged.

