# 🚀 ReferralHub - Employee Referral Management System

A modern, full-stack employee referral management system that streamlines the hiring process through employee referrals. Built with React, Node.js, Express, MongoDB, and Cloudinary.



## ✨ Features

### 🎯 Core Features
- **User Authentication**: Secure JWT-based authentication with bcrypt password hashing
- **Referral Management**: Add, view, update, and delete candidate referrals
- **Resume Upload**: PDF resume upload with Cloudinary integration
- **Status Tracking**: Track candidates through Pending, Reviewed, and Hired stages
- **Real-time Dashboard**: Live statistics and activity feed
- **Search & Filter**: Advanced search by job title and filter by status
- **Responsive Design**: Fully responsive UI that works on all devices

### 🔐 Security Features
- JWT token authentication
- HTTP-only cookies
- Password strength validation with OWASP standards
- Email validation
- Phone number validation (Indian format)
- Secure file upload with type checking

### 🎨 UI/UX Features
- Modern gradient designs with glassmorphism effects
- Smooth animations and transitions
- Toast notifications for user feedback
- Loading states for better UX
- Activity timeline
- Performance metrics dashboard

## 🛠️ Tech Stack

### Frontend
- **React 19** - UI library
- **Vite** - Build tool and dev server
- **Tailwind CSS** - Utility-first CSS framework
- **React Router DOM v7** - Client-side routing
- **Axios** - HTTP client
- **React Toastify** - Toast notifications
- **Lucide React** - Icon library
- **Day.js** - Date manipulation
- **JWT Decode** - JWT token decoding

### Backend
- **Node.js** - Runtime environment
- **Express v5** - Web framework
- **MongoDB** - Database
- **Mongoose** - ODM for MongoDB
- **JWT** - Authentication
- **Bcrypt.js** - Password hashing
- **Multer** - File upload handling
- **Cloudinary** - Cloud storage for resumes
- **OWASP Password Strength Test** - Password validation
- **Validator** - Email and phone validation
- **CORS** - Cross-origin resource sharing
- **Cookie Parser** - Cookie handling

## 📋 Prerequisites

- Node.js (v20.19.0 or higher)
- MongoDB (local or Atlas)
- Cloudinary account (for resume storage)
- npm or yarn package manager

## 🚀 Installation

### 1. Clone the Repository
```bash
git clone <repository-url>
cd referral-management-system
```

### 2. Backend Setup

```bash
cd backend
npm install
```

Create a `.env` file in the backend directory:
```env
PORT=3000
MONGO_URI=your_mongodb_connection_string
SECRET_KEY=your_jwt_secret_key
CLOUDNAME=your_cloudinary_cloud_name
APIKEY=your_cloudinary_api_key
APISECRET=your_cloudinary_api_secret
NODE_ENV=production
```

### 3. Frontend Setup

```bash
cd frontend
npm install
```

Create a `.env` file in the frontend directory:
```env
VITE_API_URL=http://localhost:3000
# For production:
# VITE_API_URL=https://backend-nine-mu-93.vercel.app
```

## 🎮 Running the Application

### Development Mode

**Backend:**
```bash
cd backend
npm start
# Server runs on http://localhost:3000
```

**Frontend:**
```bash
cd frontend
npm run dev
# App runs on http://localhost:5173
```

### Production Build

**Frontend:**
```bash
cd frontend
npm run build
npm run preview
```

## 📁 Project Structure

```
referral-management-system/
├── backend/
│   ├── api/
│   │   └── index.js              # Main server file
│   ├── src/
│   │   ├── config/
│   │   │   └── db.config.js      # Database configuration
│   │   ├── controllers/
│   │   │   ├── auth.controller.js
│   │   │   ├── candidate.controller.js
│   │   │   └── metrics.controller.js
│   │   ├── middlewares/
│   │   │   ├── auth.middleware.js
│   │   │   └── multer.middleware.js
│   │   ├── models/
│   │   │   ├── user.model.js
│   │   │   └── candidate.model.js
│   │   ├── routes/
│   │   │   ├── auth.routes.js
│   │   │   ├── candidate.routes.js
│   │   │   └── metrics.routes.js
│   │   └── utils/
│   │       └── cloudinary.js
│   ├── .env
│   ├── package.json
│   └── vercel.json
│
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── assets/
│   │   ├── components/
│   │   │   ├── Dashboard/
│   │   │   │   ├── ActivityFeed.jsx
│   │   │   │   ├── Analytics.jsx
│   │   │   │   ├── CandidateCard.jsx
│   │   │   │   ├── MyReferrals.jsx
│   │   │   │   ├── PerformanceMetrics.jsx
│   │   │   │   ├── Rewards.jsx
│   │   │   │   ├── SearchFilter.jsx
│   │   │   │   ├── Sidebar.jsx
│   │   │   │   ├── StatsCard.jsx
│   │   │   │   └── TopBar.jsx
│   │   │   └── ProtectedRoute.jsx
│   │   ├── Context/
│   │   │   ├── AuthContext.jsx
│   │   │   └── CandidateContext.jsx
│   │   ├── Modals/
│   │   │   └── AddReferralModal.jsx
│   │   ├── pages/
│   │   │   ├── Dashboard.jsx
│   │   │   ├── LandingPage.jsx
│   │   │   ├── Login.jsx
│   │   │   └── Signup.jsx
│   │   ├── App.jsx
│   │   ├── main.jsx
│   │   └── index.css
│   ├── .env
│   ├── package.json
│   ├── tailwind.config.js
│   ├── vite.config.js
│   └── vercel.json
│
└── README.md
```

## 🔌 API Endpoints

### Authentication
```
POST   /api/auth/signup          # User registration
POST   /api/auth/login           # User login
```

### Candidates
```
POST   /api/candidate/candidates/:userId          # Add new referral
GET    /api/candidate/candidates/:userId          # Get all candidates
DELETE /api/candidate/candidates/:candidateId     # Delete candidate
PUT    /api/candidate/candidates/:candidateId     # Update candidate status
```

### Metrics
```
GET    /api/matrics/getReferedCandidates/:userId  # Get referral metrics
```

## 🎯 Key Functionalities

### Authentication Flow
1. User signs up with name, email, and password
2. Password is validated using OWASP standards
3. Password is hashed using bcrypt
4. User logs in with credentials
5. JWT token is generated and stored in HTTP-only cookie
6. Token is validated on protected routes

### Referral Management
1. User adds referral with candidate details
2. Resume (PDF only) is uploaded to Cloudinary
3. Candidate appears in dashboard
4. User can search, filter, update status, or delete
5. Activity feed shows recent actions
6. Metrics display referral statistics

### File Upload Process
1. Multer middleware handles file upload
2. File is stored in `/tmp` directory (Vercel compatible)
3. File is validated (PDF only)
4. File is uploaded to Cloudinary
5. Secure URL is stored in database
6. Local file is cleaned up

## 🔒 Security Features

### Password Requirements
- Minimum 8 characters
- Validated using OWASP password strength test
- Hashed with bcrypt (salt rounds: 10)

### JWT Configuration
- Tokens stored in HTTP-only cookies
- Secure flag enabled in production
- SameSite: Lax
- 24-hour expiration

### Input Validation
- Email validation using validator library
- Phone number validation (Indian format)
- File type validation (PDF only)
- XSS protection through React

## 🌐 Deployment

### Backend (Vercel)
1. Push code to GitHub
2. Import project in Vercel
3. Set environment variables
4. Deploy

**Environment Variables:**
- `PORT`
- `MONGO_URI`
- `SECRET_KEY`
- `CLOUDNAME`
- `APIKEY`
- `APISECRET`
- `NODE_ENV`

### Frontend (Vercel)
1. Push code to GitHub
2. Import project in Vercel
3. Set environment variables
4. Deploy

**Environment Variables:**
- `VITE_API_URL`

### Production URLs
- **Backend**: https://backend-nine-mu-93.vercel.app
- **Frontend**: https://referal-management-system-frontend.vercel.app

## 🐛 Troubleshooting

### Common Issues

**Port already in use:**
```bash
npx kill-port 3000  # or 5173
```

**MongoDB connection issues:**
- Check MONGO_URI in .env
- Ensure MongoDB is running
- Check network connectivity

**Cloudinary upload fails:**
- Verify Cloudinary credentials
- Check file size (max 5MB)
- Ensure file is PDF format

**CORS errors:**
- Check allowed origins in backend
- Ensure credentials: true in axios
- Verify cookie settings

**Environment variables not loading:**
- Restart dev server after .env changes
- Ensure .env is in correct directory
- Frontend variables must start with VITE_

## 📱 Responsive Breakpoints

- **Mobile**: < 640px
- **Tablet**: 640px - 1024px
- **Desktop**: > 1024px

## 🎨 Color Scheme

```css
Primary: Indigo-600 (#4F46E5)
Secondary: Purple-600 (#9333EA)
Accent: Pink-500 (#EC4899)
Success: Green-500 (#10B981)
Warning: Yellow-500 (#F59E0B)
Error: Red-500 (#EF4444)
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is private and proprietary.

## 👥 Authors

- *Pratik Zajam** - Initial work

## 🙏 Acknowledgments

- [React](https://react.dev/)
- [Tailwind CSS](https://tailwindcss.com/)
- [Lucide Icons](https://lucide.dev/)
- [Cloudinary](https://cloudinary.com/)
- [MongoDB](https://www.mongodb.com/)
- [Express](https://expressjs.com/)

## 📧 Support

For support, email zajampratik@gmail.com or open an issue in the repository.

## 🔮 Future Enhancements

- [ ] Email notifications for status updates
- [ ] Advanced analytics dashboard with charts
- [ ] Bulk candidate upload via CSV
- [ ] Export data to CSV/PDF
- [ ] Integration with popular ATS systems
- [ ] Mobile app (React Native)
- [ ] Dark/Light theme toggle
- [ ] Multi-language support
- [ ] Candidate interview scheduling
- [ ] Automated reminder system
- [ ] Referral bonus tracking
- [ ] Team leaderboard

---

**Built with ❤️ using React, Node.js, and MongoDB**
