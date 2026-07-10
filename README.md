# Authentication and Authorization System

A full-stack, production-ready Authentication and Authorization System with a modern, futuristic UI.

## Features
- **Frontend**: React, Vite, Tailwind CSS, Framer Motion, Recharts
- **Backend**: Node.js, Express, Sequelize (MySQL)
- **Security**: JWT, bcryptjs, Rate Limiting, Helmet, Password Policies, Account Lockout after 5 failed attempts
- **Authorization**: RBAC (Admin, Faculty, Student)
- **UI**: Glassmorphism, animated transitions, neon color scheme

## Prerequisites
- Node.js (v16+)
- MySQL Server (running locally or remote)

## Environment Variables

### Backend (`/backend/.env`)
Create a `.env` file in the `backend` directory with the following variables:
```env
PORT=5000
DB_NAME=auth_db
DB_USER=root
DB_PASSWORD=your_mysql_password
DB_HOST=localhost
JWT_SECRET=your_super_secret_jwt_key
```

### Frontend (`/frontend/.env`)
No strict environment variables are required out of the box, but you can define the API URL if needed.

## Setup Instructions

### 1. Database Setup
1. Open your MySQL client (e.g., MySQL Workbench, phpMyAdmin, or CLI).
2. Create a new database named `auth_db`:
   ```sql
   CREATE DATABASE auth_db;
   ```

### 2. Backend Setup
1. Navigate to the backend folder:
   ```bash
   cd backend
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Start the server:
   ```bash
   npm run dev
   ```
   *(The server will automatically connect to MySQL and sync the tables).*

### 3. Frontend Setup
1. Navigate to the frontend folder (in a new terminal):
   ```bash
   cd frontend
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Start the development server:
   ```bash
   npm run dev
   ```

## Testing Flow

1. Go to `http://localhost:3000/register` and create an account. Ensure your password meets the policy:
   - 8+ characters
   - 1 Uppercase, 1 Lowercase, 1 Number, 1 Special Character
   - Set the role to "Admin" for your first user to test the Admin Dashboard.
2. Go to `http://localhost:3000/login`.
3. Check the "Mock CAPTCHA".
4. After entering credentials, check your backend terminal for the simulated **OTP Code**.
5. Enter the OTP code in the UI to log in.
6. Explore the Dashboard and Admin Panel.
7. To test lockouts, fail a login attempt 5 times. You will need to unlock the account from the Admin panel (or manually in the DB).
