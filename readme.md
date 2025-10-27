# 🚀 ReferralHub - Employee Referral Management System

A modern, full-stack employee referral management platform that streamlines the hiring process through employee referrals. Built with React, Node.js, Express, and MongoDB.



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

## 💻 Backend Code Examples

### Server Setup (server.js)
```javascript
const express = require('express');
const mongoose = require('mongoose');
const cors = require('cors');
const cookieParser = require('cookie-parser');
const dotenv = require('dotenv');

// Load environment variables
dotenv.config();

// Import routes
const authRoutes = require('./routes/authRoutes');
const candidateRoutes = require('./routes/candidateRoutes');
const metricsRoutes = require('./routes/metricsRoutes');

// Import middleware
const errorHandler = require('./middleware/errorHandler');

const app = express();

// Middleware
app.use(express.json());
app.use(express.urlencoded({ extended: true }));
app.use(cookieParser());

// CORS configuration
app.use(cors({
  origin: process.env.FRONTEND_URL,
  credentials: true
}));

// Database connection
mongoose.connect(process.env.MONGODB_URI)
  .then(() => console.log('✅ MongoDB connected'))
  .catch((err) => console.error('❌ MongoDB connection error:', err));

// Routes
app.use('/api/auth', authRoutes);
app.use('/api/candidate', candidateRoutes);
app.use('/api/matrics', metricsRoutes);

// Health check
app.get('/health', (req, res) => {
  res.status(200).json({ status: 'OK', message: 'Server is running' });
});

// Error handling middleware
app.use(errorHandler);

const PORT = process.env.PORT || 5000;

app.listen(PORT, () => {
  console.log(`🚀 Server running on port ${PORT}`);
});
```

### User Model (models/User.js)
```javascript
const mongoose = require('mongoose');
const bcrypt = require('bcrypt');

const userSchema = new mongoose.Schema({
  name: {
    type: String,
    required: [true, 'Name is required'],
    trim: true
  },
  email: {
    type: String,
    required: [true, 'Email is required'],
    unique: true,
    lowercase: true,
    trim: true,
    match: [/^\S+@\S+\.\S+$/, 'Please provide a valid email']
  },
  password: {
    type: String,
    required: [true, 'Password is required'],
    minlength: [8, 'Password must be at least 8 characters']
  }
}, {
  timestamps: true
});

// Hash password before saving
userSchema.pre('save', async function(next) {
  if (!this.isModified('password')) return next();
  
  try {
    const salt = await bcrypt.genSalt(10);
    this.password = await bcrypt.hash(this.password, salt);
    next();
  } catch (error) {
    next(error);
  }
});

// Method to compare passwords
userSchema.methods.comparePassword = async function(candidatePassword) {
  return await bcrypt.compare(candidatePassword, this.password);
};

module.exports = mongoose.model('User', userSchema);
```

### Candidate Model (models/Candidate.js)
```javascript
const mongoose = require('mongoose');

const candidateSchema = new mongoose.Schema({
  candidateName: {
    type: String,
    required: [true, 'Candidate name is required'],
    trim: true
  },
  email: {
    type: String,
    required: [true, 'Email is required'],
    lowercase: true,
    trim: true
  },
  phoneNumber: {
    type: String,
    required: [true, 'Phone number is required']
  },
  jobTitle: {
    type: String,
    required: [true, 'Job title is required'],
    trim: true
  },
  resume: {
    type: String, // Cloudinary URL
    default: ''
  },
  status: {
    type: String,
    enum: ['Pending', 'Reviewed', 'Hired'],
    default: 'Pending'
  },
  referredBy: {
    type: mongoose.Schema.Types.ObjectId,
    ref: 'User',
    required: true
  }
}, {
  timestamps: true
});

// Indexes for performance
candidateSchema.index({ referredBy: 1, status: 1 });
candidateSchema.index({ email: 1 });

module.exports = mongoose.model('Candidate', candidateSchema);
```

### Auth Controller (controllers/authController.js)
```javascript
const User = require('../models/User');
const jwt = require('jsonwebtoken');

// Generate JWT token
const generateToken = (userId) => {
  return jwt.sign({ userId }, process.env.JWT_SECRET, {
    expiresIn: process.env.JWT_EXPIRE
  });
};

// Signup
exports.signup = async (req, res) => {
  try {
    const { name, email, password, confirmPassword } = req.body;

    // Validation
    if (!name || !email || !password || !confirmPassword) {
      return res.status(400).json({
        status: false,
        message: 'All fields are required'
      });
    }

    if (password !== confirmPassword) {
      return res.status(400).json({
        status: false,
        message: 'Passwords do not match'
      });
    }

    // Check if user exists
    const existingUser = await User.findOne({ email });
    if (existingUser) {
      return res.status(400).json({
        status: false,
        message: 'Email already exists'
      });
    }

    // Create user
    const user = await User.create({ name, email, password });

    res.status(201).json({
      status: true,
      message: 'User registered successfully',
      data: {
        _id: user._id,
        name: user.name,
        email: user.email
      }
    });
  } catch (error) {
    res.status(500).json({
      status: false,
      message: error.message
    });
  }
};

// Login
exports.login = async (req, res) => {
  try {
    const { email, password } = req.body;

    // Validation
    if (!email || !password) {
      return res.status(400).json({
        status: false,
        message: 'Email and password are required'
      });
    }

    // Find user
    const user = await User.findOne({ email });
    if (!user) {
      return res.status(401).json({
        status: false,
        message: 'Invalid credentials'
      });
    }

    // Check password
    const isPasswordValid = await user.comparePassword(password);
    if (!isPasswordValid) {
      return res.status(401).json({
        status: false,
        message: 'Invalid credentials'
      });
    }

    // Generate token
    const token = generateToken(user._id);

    // Set cookie
    res.cookie('token', token, {
      httpOnly: true,
      secure: process.env.NODE_ENV === 'production',
      maxAge: 7 * 24 * 60 * 60 * 1000 // 7 days
    });

    res.status(200).json({
      status: true,
      message: 'Login successful',
      data: {
        _id: user._id,
        name: user.name,
        email: user.email,
        token
      }
    });
  } catch (error) {
    res.status(500).json({
      status: false,
      message: error.message
    });
  }
};

// Logout
exports.logout = (req, res) => {
  res.cookie('token', '', {
    httpOnly: true,
    expires: new Date(0)
  });

  res.status(200).json({
    status: true,
    message: 'Logged out successfully'
  });
};
```

### Candidate Controller (controllers/candidateController.js)
```javascript
const Candidate = require('../models/Candidate');
const cloudinary = require('../config/cloudinary');

// Add candidate
exports.addCandidate = async (req, res) => {
  try {
    const { userId } = req.params;
    const { candidateName, email, phoneNumber, jobTitle } = req.body;

    // Validate required fields
    if (!candidateName || !email || !phoneNumber || !jobTitle) {
      return res.status(400).json({
        status: false,
        message: 'All fields are required'
      });
    }

    let resumeUrl = '';

    // Upload resume to Cloudinary
    if (req.file) {
      const result = await cloudinary.uploader.upload(req.file.path, {
        folder: 'referralhub/resumes',
        resource_type: 'raw'
      });
      resumeUrl = result.secure_url;
    }

    // Create candidate
    const candidate = await Candidate.create({
      candidateName,
      email,
      phoneNumber,
      jobTitle,
      resume: resumeUrl,
      referredBy: userId
    });

    res.status(201).json({
      status: true,
      message: 'Candidate added successfully',
      data: candidate
    });
  } catch (error) {
    res.status(500).json({
      status: false,
      message: error.message
    });
  }
};

// Update candidate status
exports.updateCandidateStatus = async (req, res) => {
  try {
    const { id } = req.params;
    const { status } = req.body;

    if (!['Pending', 'Reviewed', 'Hired'].includes(status)) {
      return res.status(400).json({
        status: false,
        message: 'Invalid status'
      });
    }

    const candidate = await Candidate.findByIdAndUpdate(
      id,
      { status },
      { new: true }
    );

    if (!candidate) {
      return res.status(404).json({
        status: false,
        message: 'Candidate not found'
      });
    }

    res.status(200).json({
      status: true,
      message: 'Candidate status updated successfully',
      data: candidate
    });
  } catch (error) {
    res.status(500).json({
      status: false,
      message: error.message
    });
  }
};

// Delete candidate
exports.deleteCandidate = async (req, res) => {
  try {
    const { id } = req.params;

    const candidate = await Candidate.findByIdAndDelete(id);

    if (!candidate) {
      return res.status(404).json({
        status: false,
        message: 'Candidate not found'
      });
    }

    res.status(200).json({
      status: true,
      message: 'Candidate deleted successfully'
    });
  } catch (error) {
    res.status(500).json({
      status: false,
      message: error.message
    });
  }
};
```

### Auth Middleware (middleware/auth.js)
```javascript
const jwt = require('jsonwebtoken');
const User = require('../models/User');

exports.protect = async (req, res, next) => {
  try {
    let token;

    // Get token from cookie or header
    if (req.cookies.token) {
      token = req.cookies.token;
    } else if (req.headers.authorization?.startsWith('Bearer')) {
      token = req.headers.authorization.split(' ')[1];
    }

    if (!token) {
      return res.status(401).json({
        status: false,
        message: 'Not authorized to access this route'
      });
    }

    // Verify token
    const decoded = jwt.verify(token, process.env.JWT_SECRET);

    // Get user from token
    req.user = await User.findById(decoded.userId).select('-password');

    if (!req.user) {
      return res.status(401).json({
        status: false,
        message: 'User not found'
      });
    }

    next();
  } catch (error) {
    return res.status(401).json({
      status: false,
      message: 'Not authorized, token failed'
    });
  }
};
```

### Cloudinary Config (config/cloudinary.js)
```javascript
const cloudinary = require('cloudinary').v2;

cloudinary.config({
  cloud_name: process.env.CLOUDINARY_CLOUD_NAME,
  api_key: process.env.CLOUDINARY_API_KEY,
  api_secret: process.env.CLOUDINARY_API_SECRET
});

module.exports = cloudinary;
```

### Multer Config (middleware/upload.js)
```javascript
const multer = require('multer');
const path = require('path');

// Configure storage
const storage = multer.diskStorage({
  destination: function (req, file, cb) {
    cb(null, 'uploads/');
  },
  filename: function (req, file, cb) {
    cb(null, Date.now() + path.extname(file.originalname));
  }
});

// File filter for PDF only
const fileFilter = (req, file, cb) => {
  if (file.mimetype === 'application/pdf') {
    cb(null, true);
  } else {
    cb(new Error('Only PDF files are allowed'), false);
  }
};

const upload = multer({
  storage: storage,
  fileFilter: fileFilter,
  limits: {
    fileSize: parseInt(process.env.MAX_FILE_SIZE) || 10 * 1024 * 1024 // 10MB
  }
});

module.exports = upload;
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
POST /api/auth/logout       // Logout user
GET  /api/auth/me           // Get current user (protected)
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
GET /api/matrics/stats/:userId                 // Get user statistics
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
