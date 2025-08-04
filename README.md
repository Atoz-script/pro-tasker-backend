
# 🛠️ Artis watson 
(help by Yusuf,Reagan,David,Rico,Manasa,Menro)
Welcome Pro-Tasker Backend 
{made alot of repos}
This is the **backend API** for **Pro-Tasker**, a full-stack project management app built using the **MERN stack**. It handles user authentication, project creation, task management, and secure access control. 

---

## 📁 Tech Stack

- **Node.js**
- **Express**
- **MongoDB + Mongoose**
- **JWT for authentication**
- **Bcrypt for password hashing**
- **CORS**
- **dotenv**

---

## 📂 Folder Structure

backend/
├── controllers/
│ └── userController.js
│ └── projectController.js
│ └── taskController.js
├── middleware/
│ └── authMiddleware.js
├── models/
│ └── User.js
│ └── Project.js
│ └── Task.js
├── routes/
│ └── userRoutes.js
│ └── projectRoutes.js
│ └── taskRoutes.js
├── utils/
│ └── generateToken.js
├── .env
├── server.js


---

## 🔐 Authentication

- Users can **register** and **log in**
- Passwords are **hashed** using `bcryptjs`
- `jsonwebtoken` is used to **issue JWT tokens**
- Protected routes use a middleware to verify JWT

---

## 📦 API Endpoints

### 👤 User Routes

| Method | Endpoint             | Description            | Access     |
|--------|----------------------|------------------------|------------|
| POST   | `/api/users/register` | Register a new user    | Public     |
| POST   | `/api/users/login`    | Login user + get token | Public     |
| GET    | `/api/users/me`       | Get current user       | Protected  |

---

### 📁 Project Routes

| Method | Endpoint              | Description             | Access    |
|--------|-----------------------|-------------------------|-----------|
| GET    | `/api/projects`       | Get all user's projects | Protected |
| POST   | `/api/projects`       | Create a new project    | Protected |
| PUT    | `/api/projects/:id`   | Update a project        | Protected |
| DELETE | `/api/projects/:id`   | Delete a project        | Protected |

---

### ✅ Task Routes

| Method | Endpoint                  | Description         | Access    |
|--------|---------------------------|---------------------|-----------|
| POST   | `/api/tasks/:projectId`   | Add task to project | Protected |
| PUT    | `/api/tasks/:taskId`      | Update a task       | Protected |
| DELETE | `/api/tasks/:taskId`      | Delete a task       | Protected |

---

## 🌐 Environment Variables

Create a `.env` file in the root with:

MONGO_URI=mongodb+srv://artisxwatson:darius101@appuser.zndrjkm.mongodb.net/protasker?retryWrites=true&w=majority&appName=appuser
JWT_SECRET=c49ca01a683dbb9d945f722ca1aacef4890c9f38c19d523203916b6f94c1d102


---

## 🚀 Run the Server

### Install dependencies:
```bash
npm install
Start in development:
bash
Copy
Edit
npm run dev
Server will run at:
http://localhost:5000

🔧 Notes
Login bug was resolved by correctly defining .methods.isCorrectPassword inside the User.js model

MongoDB Atlas was used with a secure password and correct %24 encoding

Protected routes require a Bearer token in headers

🧠 Author Notes
This backend was developed by Artis (a.k.a. "Rightouesking") as part of a capstone for a full-stack MERN bootcamp.
The goal: Build a real-world project showing full authentication, data modeling, and secure routing.
