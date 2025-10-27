# 🚀 ReferralHub - Employee Referral Management System

A modern, full-stack employee referral management platform that streamlines the hiring process through employee referrals. Built with React, Node.js, Express, and MongoDB.

## 🎥 Demo Video

<a href="https://youtu.be/a5RjmlKloZY" target="_blank">🎬 Watch Demo Video on YouTube</a>  



## ✨ Features

### 🎯 Core Functionality
- **User Authentication** - Secure JWT-based login and registration
- **Dashboard Analytics** - Real-time referral tracking and statistics
- **Candidate Management** - Add, update, delete, and track candidate referrals
- **Status Workflow** - Monitor candidates through Pending → Reviewed → Hired stages
- **Resume Upload** - PDF resume uploads with Cloudinary storage
- **Search & Filter** - Advanced search by job title and status filtering
- **Activity Feed** - Real-time updates on referral activities
- **Performance Metrics** - Track success rates and response times

### 🎨 User Experience
- **Responsive Design** - Fully responsive UI for all devices
- **Modern UI/UX** - Beautiful gradient designs with glassmorphism effects
- **Toast Notifications** - Real-time feedback for all operations
- **Protected Routes** - Secure navigation with authentication checks
- **Loading States** - Smooth loading indicators for async operations
- **Error Handling** - Comprehensive error messages and validation

## 🛠️ Tech Stack

### Frontend
- **React 19** - Latest version with modern hooks
- **Vite** - Lightning-fast build tool
- **Tailwind CSS** - Utility-first styling
- **React Router DOM v7** - Client-side routing
- **Axios** - HTTP client for API requests
- **React Toastify** - Toast notifications
- **Lucide React** - Beautiful icon library
- **Day.js** - Date manipulation and formatting
- **JWT Decode** - Token decoding

### Backend
- **Node.js** - JavaScript runtime
- **Express.js** - Web application framework
- **MongoDB** - NoSQL database
- **Mongoose** - MongoDB ODM
- **JWT** - JSON Web Tokens for authentication
- **bcrypt** - Password hashing
- **Multer** - File upload middleware
- **Cloudinary** - Cloud storage for resumes
- **dotenv** - Environment variable management
- **cors** - Cross-origin resource sharing
- **cookie-parser** - Parse cookies
- **express-validator** - Input validation

## 📋 Prerequisites

Before you begin, ensure you have the following installed:
- **Node.js** (v20.19.0 or higher)
- **MongoDB** (v6.0 or higher) or MongoDB Atlas account
- **npm** or **yarn**
- **Git**
- **Cloudinary Account** (for file uploads)

## 🔧 Installation & Setup

### 1. Clone the Repository
```bash
git clone https://github.com/pratikzajam/workoai.git
cd referralhub
```

### 2. Backend Setup

#### Install Dependencies
```bash
cd backend
npm install
```

#### Backend Environment Configuration
Create a `.env` file in the `backend` directory:

```env
# Server Configuration
PORT=5000
NODE_ENV=development

# Database
MONGODB_URI=mongodb://localhost:27017/referralhub
# OR use MongoDB Atlas
# MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net/referralhub

# JWT Configuration
JWT_SECRET=your-super-secret-jwt-key-change-this-in-production-min-32-chars
JWT_EXPIRE=7d

# Cloudinary Configuration (for resume uploads)
CLOUDINARY_CLOUD_NAME=your-cloud-name
CLOUDINARY_API_KEY=your-api-key
CLOUDINARY_API_SECRET=your-api-secret

# CORS Configuration
FRONTEND_URL=http://localhost:5173

# File Upload
MAX_FILE_SIZE=10485760
```

#### Start Backend Server
```bash
# Development mode with nodemon
npm run dev

# Production mode
npm start
```

The backend will be available at `http://localhost:5000`

### 3. Frontend Setup

#### Install Dependencies
```bash
cd frontend
npm install
```

#### Frontend Environment Configuration
Create a `.env` file in the `frontend` directory:

```env
VITE_API_URL=http://localhost:5000
# OR in production
# VITE_API_URL=https://your-backend-url.vercel.app
```

#### Start Frontend Development Server
```bash
npm run dev
```

The application will be available at `http://localhost:5173`

## 📜 Available Scripts

### Backend
```bash
# Development
npm run dev          # Start server with nodemon (auto-reload)
npm start            # Start production server


```

### Frontend
```bash
# Development
npm run dev          # Start development server

# Production
npm run build        # Build for production
npm run preview      # Preview production build


```

## 📁 Project Structure

```
referralhub/
├── backend/                # Backend server
│   ├── config/            # Configuration files
│   │   ├── cloudinary.js  # Cloudinary setup
│   │   └── db.js          # MongoDB connection
│   ├── controllers/       # Route controllers
│   │   ├── authController.js
│   │   ├── candidateController.js
│   │   └── metricsController.js
│   ├── middleware/        # Custom middleware
│   │   ├── auth.js        # Authentication middleware
│   │   ├── errorHandler.js
│   │   └── upload.js      # Multer configuration
│   ├── models/            # Mongoose models
│   │   ├── User.js        # User schema
│   │   └── Candidate.js   # Candidate schema
│   ├── routes/            # API routes
│   │   ├── authRoutes.js
│   │   ├── candidateRoutes.js
│   │   └── metricsRoutes.js
│   ├── utils/             # Utility functions
│   │   ├── generateToken.js
│   │   └── validators.js
│   ├── .env               # Environment variables
│   ├── .gitignore
│   ├── package.json
│   └── server.js          # Entry point
│
├── frontend/              # React frontend
│   ├── public/            # Static assets
│   │   └── vite.svg
│   ├── src/
│   │   ├── assets/       # Images, icons
│   │   ├── components/   # Reusable components
│   │   │   ├── Dashboard/  # Dashboard-specific components
│   │   │   │   ├── ActivityFeed.jsx
│   │   │   │   ├── Analytics.jsx
│   │   │   │   ├── CandidateCard.jsx
│   │   │   │   ├── MyReferrals.jsx
│   │   │   │   ├── PerfromanceMertics.jsx
│   │   │   │   ├── Rewards.jsx
│   │   │   │   ├── SearchFilter.jsx
│   │   │   │   ├── Sidebar.jsx
│   │   │   │   ├── StatsCard.jsx
│   │   │   │   └── TopBar.jsx
│   │   │   └── ProtectedRoute.jsx
│   │   ├── Context/      # React Context providers
│   │   │   ├── AuthContext.jsx
│   │   │   └── CandidateContext.jsx
│   │   ├── Modals/       # Modal components
│   │   │   └── AddReferralModal.jsx
│   │   ├── pages/        # Page components
│   │   │   ├── Dashboard.jsx
│   │   │   ├── LandingPage.jsx
│   │   │   ├── Login.jsx
│   │   │   └── Signup.jsx
│   │   ├── App.jsx       # Main app component
│   │   ├── main.jsx      # Entry point
│   │   └── index.css     # Global styles
│   ├── .env              # Environment variables
│   ├── .gitignore
│   ├── index.html
│   ├── package.json
│   ├── tailwind.config.js
│   ├── vite.config.js
│   └── vercel.json       # Vercel deployment config
│
└── README.md             # Project documentation
```



## 🔐 Authentication Flow

1. **Signup** - User creates account with name, email, and password
2. **Password Hashing** - Password encrypted with bcrypt (10 rounds)
3. **Login** - User authenticates with credentials
4. **JWT Generation** - Server generates JWT token
5. **Token Storage** - Token stored in localStorage (frontend) and HTTP-only cookie (backend)
6. **Protected Routes** - Routes check for valid authentication
7. **Token Verification** - Middleware verifies JWT on protected routes
8. **Context Management** - User state managed via AuthContext
9. **Auto-logout** - Invalid/expired tokens trigger logout

## 🎯 Key Components

### Context Providers

#### AuthContext (Frontend)
Manages authentication state and operations:
- `login(email, password)` - Authenticate user
- `signup(userData)` - Register new user
- `logout()` - Clear session
- `user` - Current user data
- `loading` - Loading state

#### CandidateContext (Frontend)
Manages candidate referrals:
- `metrics` - Referral statistics and candidates
- `addReferal(formData)` - Submit new referral
- `updateCandidateStatus(status, id)` - Update candidate status
- `deleteCandidate(id)` - Remove candidate
- `getmetricsData()` - Fetch latest data

### Protected Routes
```jsx
<ProtectedRoute>
  <Dashboard />
</ProtectedRoute>
```

## 🌐 API Integration

### Backend API Endpoints

#### Authentication Routes
```javascript
POST /api/auth/signup       // Register new user
POST /api/auth/login        // Login user

```

#### Candidate Routes
```javascript
POST   /api/candidate/candidates/:userId    // Create new referral
GET    /api/candidate/candidates/:userId    // Get user's candidates
PUT    /api/candidate/candidates/:id        // Update candidate status
DELETE /api/candidate/candidates/:id        // Delete candidate
```

#### Metrics Routes
```javascript
GET /api/matrics/getReferedCandidates/:userId  // Get all referral metrics

```

### Database Models

#### User Model
```javascript
{
  name: String (required),
  email: String (required, unique),
  password: String (required, hashed),
  createdAt: Date,
  updatedAt: Date
}
```

#### Candidate Model
```javascript
{
  candidateName: String (required),
  email: String (required),
  phoneNumber: String (required),
  jobTitle: String (required),
  resume: String (Cloudinary URL),
  status: String (enum: ['Pending', 'Reviewed', 'Hired']),
  referredBy: ObjectId (ref: 'User'),
  createdAt: Date,
  updatedAt: Date
}
```

### Request/Response Examples

#### 1. User Signup
**Request:**
```javascript
POST /api/auth/signup
Content-Type: application/json

{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "SecurePass123!",
  "confirmPassword": "SecurePass123!"
}
```

**Response:**
```javascript
{
  "status": true,
  "message": "User registered successfully",
  "data": {
    "_id": "60d5ec49f1b2c72b8c8e4f1a",
    "name": "John Doe",
    "email": "john@example.com"
  }
}
```

#### 2. User Login
**Request:**
```javascript
POST /api/auth/login
Content-Type: application/json

{
  "email": "john@example.com",
  "password": "SecurePass123!"
}
```

**Response:**
```javascript
{
  "status": true,
  "message": "Login successful",
  "data": {
    "_id": "60d5ec49f1b2c72b8c8e4f1a",
    "name": "John Doe",
    "email": "john@example.com",
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
  }
}
```

#### 3. Add Referral
**Request:**
```javascript
POST /api/candidate/candidates/:userId
Content-Type: multipart/form-data

FormData:
  candidateName: "Jane Smith"
  email: "jane@example.com"
  phoneNumber: "1234567890"
  jobTitle: "Software Engineer"
  resume: <File>
```

**Response:**
```javascript
{
  "status": true,
  "message": "Candidate added successfully",
  "data": {
    "_id": "60d5ec50f1b2c72b8c8e4f1b",
    "candidateName": "Jane Smith",
    "email": "jane@example.com",
    "phoneNumber": "1234567890",
    "jobTitle": "Software Engineer",
    "resume": "https://res.cloudinary.com/...",
    "status": "Pending",
    "referredBy": "60d5ec49f1b2c72b8c8e4f1a",
    "createdAt": "2025-01-15T10:30:00.000Z",
    "updatedAt": "2025-01-15T10:30:00.000Z"
  }
}
```

#### 4. Update Candidate Status
**Request:**
```javascript
PUT /api/candidate/candidates/:id
Content-Type: application/json

{
  "status": "Reviewed"
}
```

**Response:**
```javascript
{
  "status": true,
  "message": "Candidate status updated successfully",
  "data": {
    "_id": "60d5ec50f1b2c72b8c8e4f1b",
    "candidateName": "Jane Smith",
    "status": "Reviewed",
    "updatedAt": "2025-01-15T11:30:00.000Z"
  }
}
```

#### 5. Get Referral Metrics
**Request:**
```javascript
GET /api/matrics/getReferedCandidates/:userId
Authorization: Bearer <token>
```

**Response:**
```javascript
{
  "status": true,
  "data": {
    "totalCandidates": 15,
    "pending": 5,
    "reviewed": 7,
    "hired": 3,
    "candidates": [
      {
        "_id": "60d5ec50f1b2c72b8c8e4f1b",
        "candidateName": "Jane Smith",
        "email": "jane@example.com",
        "jobTitle": "Software Engineer",
        "status": "Reviewed",
        "createdAt": "2025-01-15T10:30:00.000Z"
      }
      // ... more candidates
    ]
  }
}
```

#### 6. Delete Candidate
**Request:**
```javascript
DELETE /api/candidate/candidates/:id
Authorization: Bearer <token>
```

**Response:**
```javascript
{
  "status": true,
  "message": "Candidate deleted successfully"
}
```

### Error Responses

**Validation Error:**
```javascript
{
  "status": false,
  "message": "Email already exists"
}
```

**Authentication Error:**
```javascript
{
  "status": false,
  "message": "Invalid credentials"
}
```

**Authorization Error:**
```javascript
{
  "status": false,
  "message": "Not authorized to access this resource"
}
```

**Server Error:**
```javascript
{
  "status": false,
  "message": "Internal server error",
  "error": "Error details..."
}
```

## 🎨 Styling

### Tailwind CSS Configuration
- **Mobile First** - Responsive breakpoints
- **Custom Colors** - Gradient themes
- **Animations** - Smooth transitions
- **Utility Classes** - Component styling

### Design System
- **Primary Colors**: Indigo, Purple, Pink
- **Typography**: Bold headings, medium body text
- **Spacing**: Consistent padding and margins
- **Shadows**: Layered elevation

## 🚀 Deployment

### Backend Deployment (Vercel)

#### Vercel Deployment
1. Install Vercel CLI
```bash
npm i -g vercel
```

2. Navigate to backend directory
```bash
cd backend
```

3. Create `vercel.json`:
```json
{
  "version": 2,
  "builds": [
    {
      "src": "server.js",
      "use": "@vercel/node"
    }
  ],
  "routes": [
    {
      "src": "/(.*)",
      "dest": "server.js"
    }
  ],
  "env": {
    "NODE_ENV": "production"
  }
}
```

4. Deploy
```bash
vercel deploy --prod
```

5. Set Environment Variables in Vercel Dashboard:
   - `MONGODB_URI`
   - `JWT_SECRET`
   - `CLOUDINARY_CLOUD_NAME`
   - `CLOUDINARY_API_KEY`
   - `CLOUDINARY_API_SECRET`
   - `FRONTEND_URL`




## 📚 Resources

### Documentation
- [React Documentation](https://react.dev)
- [Vite Guide](https://vitejs.dev)
- [Tailwind CSS](https://tailwindcss.com)
- [React Router](https://reactrouter.com)
- [Express.js](https://expressjs.com)
- [MongoDB Documentation](https://docs.mongodb.com)
- [Mongoose Docs](https://mongoosejs.com)
- [Cloudinary Documentation](https://cloudinary.com/documentation)

### Tutorials
- [MERN Stack Tutorial](https://www.mongodb.com/mern-stack)
- [JWT Authentication](https://jwt.io/introduction)
- [File Upload with Multer](https://github.com/expressjs/multer)
- [React Context API](https://react.dev/reference/react/useContext)

### Tools
- [Postman](https://www.postman.com) - API testing
- [MongoDB Compass](https://www.mongodb.com/products/compass) - Database GUI
- [VS Code](https://code.visualstudio.com) - Code editor
- [Git](https://git-scm.com) - Version control

## 🎉 Acknowledgments

- Design inspiration from modern SaaS platforms
- Icons by [Lucide React](https://lucide.dev)
- UI components built with [Tailwind CSS](https://tailwindcss.com)
- File storage powered by [Cloudinary](https://cloudinary.com)
- Database hosting by [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)

## 📊 Project Statistics

- **Total Lines of Code**: ~15,000+
- **Components**: 20+
- **API Endpoints**: 10+
- **Database Models**: 2
- **Dependencies**: 30+
- **Development Time**: 2-3 weeks



---

**Built with ❤️ by the ReferralHub Team**

⭐ Star this repository if you found it helpful!

📢 Follow us for updates and new features!

🤝 Contributions are welcome!

---

© 2025 ReferralHub. All rights reserved.
