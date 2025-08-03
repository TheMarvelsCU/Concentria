# 🛡️ Concentria - Comprehensive Privacy Monitoring Platform

<div align="center">

![Concentria Logo](Logo.png)

**A complete digital privacy protection ecosystem that empowers users to monitor, understand, and control their digital footprint**

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Node.js](https://img.shields.io/badge/Node.js-18%2B-green.svg)](https://nodejs.org/)
[![React](https://img.shields.io/badge/React-19.1.0-blue.svg)](https://reactjs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.8.3-blue.svg)](https://www.typescriptlang.org/)
[![Chrome Extension](https://img.shields.io/badge/Chrome%20Extension-Manifest%20V3-orange.svg)](https://developer.chrome.com/docs/extensions/mv3/)

[🌐 Live Demo](https://concentria.netlify.app) • [📖 Documentation](#documentation) • [🚀 Quick Start](#quick-start) • [💻 API Reference](#api-reference)

</div>

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Architecture](#-architecture)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Quick Start](#-quick-start)
- [Project Structure](#-project-structure)
- [Installation & Setup](#-installation--setup)
- [API Reference](#-api-reference)
- [Deployment](#-deployment)
- [Contributing](#-contributing)
- [Security](#-security)
- [License](#-license)

---

## 🎯 Overview

Concentria is a comprehensive privacy monitoring platform that consists of three integrated components:

1. **🖥️ Web Application** - React-based dashboard for privacy analytics and account management
2. **⚙️ Backend API** - Node.js/TypeScript server handling authentication and data management
3. **🔍 Browser Extension** - Chrome extension for real-time API monitoring and data collection

The platform empowers users to understand and control their digital privacy by providing real-time monitoring of sensitive browser APIs, comprehensive activity logging, and intuitive privacy analytics.

### 🌟 Key Value Propositions

- **🔒 Real-time Privacy Monitoring** - Track clipboard access, geolocation requests, camera/microphone usage, and file downloads
- **📊 Comprehensive Analytics** - Visual dashboards showing privacy patterns and potential threats
- **🛡️ Proactive Protection** - Instant alerts and blocking capabilities for suspicious activities
- **👥 Human-Centered Design** - Privacy protection made simple and accessible for everyone
- **🔐 Enterprise-Grade Security** - JWT authentication, encrypted data transmission, and secure storage

---

## 🏗️ Architecture

```mermaid
graph TB
    subgraph "Frontend Ecosystem"
        A[React Web App<br/>Port 3000]
        B[Chrome Extension<br/>Manifest V3]
    end

    subgraph "Backend Infrastructure"
        C[Express API Server<br/>Port 5000]
        D[MongoDB Atlas<br/>User & Log Data]
        E[Redis Cloud<br/>Session & OTP Storage]
    end

    subgraph "External Services"
        F[Gmail SMTP<br/>Email Service]
        G[Netlify<br/>Frontend Hosting]
        H[Render<br/>API Hosting]
    end

    A --> C
    B --> C
    C --> D
    C --> E
    C --> F
    A --> G
    C --> H
```

### 🔄 Data Flow

1. **Extension Monitoring** → Chrome extension detects API usage → Sends logs to backend
2. **User Authentication** → JWT-based auth with refresh tokens → Secure session management
3. **Real-time Logging** → Activity logs stored in MongoDB → Displayed in web dashboard
4. **Privacy Analytics** → Data aggregation → Visual insights and recommendations

---

## ✨ Features

### 🌐 Web Application Features

#### 🔐 Authentication & Security

- **User Registration** with email verification via OTP
- **JWT-based Authentication** (Access & Refresh tokens)
- **Password Reset** functionality with OTP verification
- **Secure session management** with automatic token refresh
- **Protected routes** with authentication middleware

#### 📊 Privacy Dashboard

- **Real-time activity monitoring** with live updates
- **Interactive charts and analytics** using Recharts
- **Activity log management** with filtering and search
- **Privacy score calculation** based on user activity
- **Export capabilities** for logs and reports

#### 🎨 User Experience

- **Modern UI/UX** with Tailwind CSS and gradient themes
- **Responsive design** optimized for all devices
- **Dark/light mode support** (coming soon)
- **Accessibility features** with ARIA compliance
- **Progressive Web App** capabilities

### 🔍 Browser Extension Features

#### 📱 Real-time Monitoring

- **📋 Clipboard Access Detection** - Monitors cut/copy/paste operations
- **📍 Geolocation Tracking** - Detects location access requests
- **🎤 Microphone/Camera Access** - Monitors media device usage
- **📁 File Download Logging** - Tracks all downloaded files
- **🔐 Permission Requests** - Monitors permission API calls
- **🎮 Device Orientation** - Detects orientation event listeners

#### 🌟 Visual Feedback

- **Emoji Overlays** - Visual indicators for detected activities
- **Real-time Notifications** - Instant alerts for privacy events
- **Status Indicators** - Connection and monitoring status

#### 🍪 Cookie Management

- **Cookie Viewer** - Display all cookies for current domain
- **Cookie Editor** - Modify cookie values directly
- **Bulk Operations** - Clear all cookies or export as JSON
- **Domain Filtering** - View cookies by specific domains

### ⚙️ Backend API Features

#### 🔒 Authentication Services

- **User registration and verification**
- **Email OTP delivery via Gmail SMTP**
- **JWT token generation and refresh**
- **Password reset with security validation**
- **Rate limiting and security middleware**

#### 📊 Data Management

- **MongoDB integration** for persistent storage
- **Redis caching** for temporary data (OTP, sessions)
- **Comprehensive logging** with Winston
- **Data validation** using Zod schemas
- **CORS protection** with configurable origins

#### 🛡️ Security Features

- **Bcrypt password hashing** (10 rounds)
- **JWT token validation** middleware
- **Request/response logging** for audit trails
- **Input sanitization** and validation
- **Error handling** with detailed logging

---

## 🛠️ Tech Stack

### Frontend (Web Application)

```json
{
  "framework": "React 19.1.0",
  "language": "JavaScript/JSX",
  "routing": "React Router DOM 7.6.2",
  "styling": "Tailwind CSS 4.1.10",
  "charts": "Recharts 3.0.0",
  "icons": "React Icons 5.5.0",
  "build": "Vite 6.3.5",
  "deployment": "Netlify"
}
```

### Backend (API Server)

```json
{
  "runtime": "Node.js 18+",
  "framework": "Express.js 5.1.0",
  "language": "TypeScript 5.8.3",
  "database": "MongoDB (Mongoose 8.16.3)",
  "cache": "Redis (ioredis 5.6.1)",
  "authentication": "JWT (jsonwebtoken 9.0.2)",
  "validation": "Zod 3.25.67",
  "logging": "Winston 3.17.0",
  "deployment": "Render"
}
```

### Browser Extension

```json
{
  "manifest": "Chrome Extension Manifest V3",
  "language": "Vanilla JavaScript",
  "apis": ["Storage", "Cookies", "Tabs", "Downloads"],
  "permissions": ["<all_urls>", "storage", "cookies", "tabs", "downloads"],
  "architecture": "Content Script + Background Service Worker"
}
```

---

## 🚀 Quick Start

### Prerequisites

- **Node.js** 18.0+ and npm
- **MongoDB** database (Atlas recommended)
- **Redis** instance (Redis Cloud recommended)
- **Chrome browser** for extension testing

### 1. Clone the Repository

```bash
git clone https://github.com/TheMarvelsCU/Concentria.git
cd Concentria
```

### 2. Backend Setup

```bash
cd Concentria-Backend

# Install dependencies
npm install

# Create environment file
cp .env.example .env

# Configure environment variables (see Backend Environment Variables section)
# Start development server
npm run dev
```

### 3. Frontend Setup

```bash
cd ../Concentria-FrontEnd

# Install dependencies
npm install

# Start development server
npm run dev
```

### 4. Browser Extension Setup

```bash
# Navigate to Extension directory
cd ../Concentria-Extention

# Load extension in Chrome
# 1. Open chrome://extensions/
# 2. Enable "Developer mode"
# 3. Click "Load unpacked"
# 4. Select the Concentria-Extention folder
```

### 5. Access the Application

- **Web App**: http://localhost:3000
- **API Server**: http://localhost:5000
- **Extension**: Click the Concentria icon in Chrome toolbar

---

## 📁 Project Structure

```
Concentria/
├── 📖 README.md                              # This comprehensive guide
├── 📄 LICENSE                                # MIT License
│
├── 🖥️ Concentria-FrontEnd/                  # React Web Application
│   ├── 📁 public/                           # Static assets
│   ├── 📁 src/
│   │   ├── 📁 components/                   # Reusable UI components
│   │   │   ├── 📁 Auth/                     # Authentication forms
│   │   │   ├── 📁 Common/                   # Shared components
│   │   │   └── 📁 Dashboard/                # Dashboard-specific components
│   │   │       ├── 📁 Header/               # Dashboard header
│   │   │       ├── 📁 Logs/                 # Activity logs table
│   │   │       ├── 📁 MainContent/          # Main content area
│   │   │       ├── 📁 Sidebar/              # Navigation sidebar
│   │   │       └── 📁 Stats/                # Statistics cards
│   │   ├── 📁 contexts/                     # React contexts
│   │   │   ├── 🔐 AuthContext.jsx           # Authentication state
│   │   │   └── 🍞 ToastContext.jsx          # Notification system
│   │   ├── 📁 pages/                        # Page components
│   │   │   ├── 🏠 LandingPage.jsx           # Marketing landing page
│   │   │   ├── 🔐 AuthPage.jsx              # Login/register page
│   │   │   └── 📊 DashboardPage.jsx         # Main dashboard
│   │   ├── 📁 routes/                       # Route protection
│   │   ├── 📁 services/                     # API integration
│   │   │   ├── 🔐 authApi.js                # Authentication API calls
│   │   │   └── 📊 logsApi.js                # Logging API calls
│   │   └── 📁 config/                       # Configuration files
│   ├── 📋 package.json                      # Dependencies & scripts
│   ├── ⚙️ vite.config.js                    # Vite configuration
│   ├── 🎨 tailwind.config.js               # Tailwind CSS config
│   └── 🌐 netlify.toml                      # Netlify deployment config
│
├── ⚙️ Concentria-Backend/                   # Node.js API Server
│   ├── 📁 controllers/                      # Route controllers
│   │   ├── 🔐 authController.ts             # Authentication logic
│   │   ├── 📊 logController.ts              # Logging operations
│   │   └── 🔴 redisClient.ts                # Redis connection
│   ├── 📁 middlewares/                      # Express middlewares
│   │   ├── 🔐 authMiddleware.ts             # JWT verification
│   │   ├── ❌ errorHandler.ts               # Error handling
│   │   ├── 📝 requestLogger.ts              # Request logging
│   │   ├── 📝 responseLogger.ts             # Response logging
│   │   └── ✅ validateRequest.ts            # Input validation
│   ├── 📁 models/                           # Database schemas
│   │   ├── 👤 userModel.ts                 # User schema
│   │   ├── 📊 logModel.ts                  # Activity log schema
│   │   └── 🔢 otpModel.ts                  # OTP verification schema
│   ├── 📁 routes/                           # API route definitions
│   │   ├── 🔐 authRoutes.ts                # Authentication endpoints
│   │   ├── 📊 logRoutes.ts                 # Logging endpoints
│   │   └── 📧 emailVerification.ts         # Email utilities
│   ├── 📁 services/                         # Business logic
│   │   └── 🔐 authService.ts               # Authentication services
│   ├── 📁 types/                           # TypeScript definitions
│   │   ├── 🔐 authInterfaces.ts            # Auth type definitions
│   │   ├── 🌍 env.d.ts                     # Environment types
│   │   └── 🚀 express.d.ts                # Express extensions
│   ├── 📁 utils/                           # Utility functions
│   │   ├── ❌ customError.ts               # Custom error handling
│   │   ├── 📅 dateTimeUtils.ts             # Date/time utilities
│   │   ├── 🎫 generateToken.ts             # JWT token generation
│   │   ├── 📝 logger.ts                    # Winston logger setup
│   │   └── 🗄️ operateDB.ts                # Database operations
│   ├── 📁 validators/                       # Input validation schemas
│   │   ├── 🔐 authValidator.ts             # Auth validation rules
│   │   └── 📊 logValidator.ts              # Log validation rules
│   ├── 🚀 server.ts                        # Server entry point
│   ├── 📱 app.ts                           # Express app configuration
│   ├── ⚙️ config.ts                        # Environment configuration
│   ├── 📋 package.json                     # Dependencies & scripts
│   └── 📘 tsconfig.json                    # TypeScript configuration
│
└── 🔍 Concentria-Extention/                # Chrome Browser Extension
    ├── 📋 manifest.json                    # Extension manifest (V3)
    ├── 🎯 background.js                    # Service worker
    ├── 📄 content.js                       # Content script injection
    ├── ⚙️ config.js                        # API configuration
    ├── 🧪 test.html                        # Testing interface
    ├── 📁 popup/                           # Extension popup UI
    │   ├── 🖼️ popup.html                   # Popup interface
    │   ├── 🎨 popup.css                    # Popup styling
    │   └── ⚡ popup.js                     # Popup functionality
    ├── 📁 utils/                           # Utility modules
    │   ├── 🎣 apiHooks.js                  # API monitoring hooks
    │   └── 🍪 cookieUtils.js               # Cookie management
    ├── 📁 api/                             # API communication
    │   └── 📡 logger.js                    # Log transmission
    └── 📁 icons/                           # Extension icons
        └── 🖼️ icon.png                     # Extension icon
```

---

## 🔧 Installation & Setup

### Backend Environment Variables

Create a `.env` file in the `Concentria-Backend` directory:

```env
# Server Configuration
NODE_ENV=development
PORT=5000

# Database Configuration
DB_HOST=mongodb+srv://your-mongodb-host
DB_USER=your-username
DB_PASS=your-password
DB_NAME=concentria

# JWT Configuration
JWT_SECRET=your-super-secure-jwt-secret-key-minimum-32-characters
JWT_REFRESH_SECRET=your-super-secure-refresh-secret-key-minimum-32-characters

# Redis Configuration (Redis Cloud recommended)
REDIS_CLIENT_HOST=your-redis-host
REDIS_CLIENT_PORT=6379
REDIS_PASSWORD=your-redis-password
REDIS_USERNAME=default

# Email Configuration (Gmail SMTP)
EMAIL=your-gmail-address@gmail.com
EMAIL_PASSWORD=your-app-specific-password

# Security Configuration
ALLOWED_ORIGINS=http://localhost:3000,https://concentria.netlify.app,chrome-extension://
```

### Frontend Environment Variables

Create a `.env` file in the `Concentria-FrontEnd` directory:

```env
# API Configuration
VITE_API_URL=http://localhost:5000
VITE_APP_ENV=development

# Optional: Analytics and monitoring
VITE_ANALYTICS_ID=your-analytics-id
```

### Extension Configuration

Edit `Concentria-Extention/config.js`:

```javascript
export const config = {
  API_URL: "http://localhost:5000/api/logs", // Development
  // API_URL: 'https://concentria-fh4s.onrender.com/api/logs', // Production
  ENABLE_LOGGING: true,
  DEBUG_MODE: true,
};
```

### Database Setup

#### MongoDB Setup

1. Create a [MongoDB Atlas](https://www.mongodb.com/cloud/atlas) account
2. Create a new cluster
3. Add your IP address to the whitelist
4. Create a database user
5. Get the connection string and update `DB_HOST` in your `.env`

#### Redis Setup

1. Create a [Redis Cloud](https://redis.com/redis-enterprise-cloud/) account
2. Create a new database
3. Get the connection details and update Redis variables in your `.env`

### Email Setup (Gmail SMTP)

1. Enable 2-Factor Authentication on your Gmail account
2. Generate an [App Password](https://support.google.com/accounts/answer/185833)
3. Use the app password in the `EMAIL_PASSWORD` environment variable

---

## 📚 API Reference

### 🔐 Authentication Endpoints

#### Register User

```http
POST /auth/register
Content-Type: application/json

{
  "fullName": "John Doe",
  "email": "john@example.com",
  "password": "securePassword123",
  "countryCode": "+1",
  "phoneNumber": "1234567890",
  "tnc": true
}
```

**Response:**

```json
{
  "message": "OTP sent for verification",
  "uniqueKey": "uuid-key-for-verification"
}
```

#### Verify OTP

```http
POST /auth/verify-otp
Content-Type: application/json

{
  "uniqueKey": "uuid-key-from-registration",
  "otp": "123456"
}
```

#### Login

```http
POST /auth/login
Content-Type: application/json

{
  "email": "john@example.com",
  "password": "securePassword123"
}
```

**Response:**

```json
{
  "message": "Login successful",
  "user": {
    "email": "john@example.com",
    "fullName": "John Doe"
  }
}
```

#### Refresh Token

```http
GET /auth/refresh-token
Cookie: refreshToken=your-refresh-token
```

#### Forgot Password

```http
POST /auth/forgot-password
Content-Type: application/json

{
  "email": "john@example.com"
}
```

#### Reset Password

```http
POST /auth/reset-password
Content-Type: application/json

{
  "email": "john@example.com",
  "otp": "123456",
  "newPassword": "newSecurePassword123"
}
```

### 📊 Logging Endpoints

#### Create Activity Log

```http
POST /api/logs
Authorization: Bearer your-access-token
Content-Type: application/json

{
  "type": "clipboard",
  "timestamp": "2025-02-03T10:30:00.000Z",
  "url": "https://example.com",
  "filename": "optional-file.pdf"
}
```

**Supported Log Types:**

- `clipboard` - Clipboard access
- `geolocation` - Location requests
- `microphone` - Microphone access
- `camera` - Camera access
- `download` - File downloads
- `permissions` - Permission requests
- `cut`, `copy`, `paste` - Clipboard operations

#### Get User Logs

```http
GET /api/logs
Authorization: Bearer your-access-token
```

**Response:**

```json
[
  {
    "_id": "log-id",
    "userEmail": "john@example.com",
    "type": "clipboard",
    "timestamp": "2025-02-03T10:30:00.000Z",
    "url": "https://example.com",
    "createdAt": "2025-02-03T10:30:00.000Z"
  }
]
```

#### Delete All User Logs

```http
DELETE /api/logs
Authorization: Bearer your-access-token
```

### 🔒 Authentication Headers

All protected endpoints require the JWT token in the Authorization header:

```http
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...
```

### ❌ Error Responses

All endpoints return consistent error responses:

```json
{
  "error": "Error message",
  "details": "Detailed error information"
}
```

**Common HTTP Status Codes:**

- `200` - Success
- `201` - Created
- `400` - Bad Request (validation error)
- `401` - Unauthorized (invalid/expired token)
- `403` - Forbidden
- `404` - Not Found
- `429` - Too Many Requests
- `500` - Internal Server Error

---

## 🚀 Deployment

### Frontend Deployment (Netlify)

The frontend is configured for automatic deployment to Netlify:

1. **Connect Repository**: Link your GitHub repository to Netlify
2. **Build Settings**:
   - Build command: `npm run build`
   - Publish directory: `dist`
3. **Environment Variables**: Set `VITE_API_URL` to your production API URL
4. **Deploy**: Automatic deployment on every push to main branch

**Netlify Configuration** (`netlify.toml`):

```toml
[build]
  command = "npm run build"
  publish = "dist"

[build.environment]
  VITE_API_URL = "https://your-api-domain.com"
  VITE_APP_ENV = "production"

[[redirects]]
  from = "/*"
  to = "/index.html"
  status = 200
```

### Backend Deployment (Render)

The backend is deployed on Render with the following configuration:

1. **Service Type**: Web Service
2. **Build Command**: `npm run build`
3. **Start Command**: `npm start`
4. **Environment Variables**: Set all required environment variables
5. **Health Check**: `/auth/refresh-token` endpoint

**Production Environment Variables:**

```env
NODE_ENV=production
PORT=5000
DB_HOST=mongodb+srv://production-cluster
JWT_SECRET=production-secret-key
# ... other production variables
```

### Extension Distribution

For Chrome Web Store publication:

1. **Prepare Extension**:

   ```bash
   cd Concentria-Extention
   # Update config.js with production API URL
   # Test all functionality
   ```

2. **Package Extension**:

   - Zip the entire `Concentria-Extention` folder
   - Exclude development files (.git, node_modules, etc.)

3. **Chrome Web Store**:
   - Create a [Chrome Web Store Developer Account](https://chrome.google.com/webstore/devconsole)
   - Upload the extension package
   - Fill in store listing information
   - Submit for review

### Production Considerations

#### Security

- Use HTTPS for all communications
- Implement rate limiting
- Enable CORS only for trusted domains
- Use strong JWT secrets (minimum 32 characters)
- Implement proper input validation

#### Performance

- Enable gzip compression
- Use CDN for static assets
- Implement database indexing
- Use Redis for caching
- Monitor API response times

#### Monitoring

- Set up application monitoring (e.g., New Relic, DataDog)
- Implement error tracking (e.g., Sentry)
- Set up uptime monitoring
- Configure log aggregation

---

## 🤝 Contributing

We welcome contributions to Concentria! Here's how you can help:

### Development Workflow

1. **Fork the Repository**

   ```bash
   git fork https://github.com/TheMarvelsCU/Concentria.git
   ```

2. **Create a Feature Branch**

   ```bash
   git checkout -b feature/your-feature-name
   ```

3. **Make Changes**

   - Follow the existing code style
   - Add tests for new functionality
   - Update documentation as needed

4. **Test Your Changes**

   ```bash
   # Test backend
   cd Concentria-Backend
   npm test

   # Test frontend
   cd Concentria-FrontEnd
   npm test

   # Test extension manually
   ```

5. **Submit a Pull Request**
   - Provide a clear description of changes
   - Link any related issues
   - Ensure all checks pass

### Code Style Guidelines

#### TypeScript/JavaScript

- Use TypeScript for backend development
- Follow ESLint configuration
- Use meaningful variable names
- Add JSDoc comments for functions
- Implement proper error handling

#### React Components

- Use functional components with hooks
- Implement proper prop validation
- Follow component composition patterns
- Use meaningful component names
- Implement accessibility features

#### CSS/Styling

- Use Tailwind CSS utility classes
- Follow responsive design principles
- Maintain consistent spacing and colors
- Use semantic HTML elements

### Bug Reports

When reporting bugs, please include:

- Detailed description of the issue
- Steps to reproduce
- Expected vs actual behavior
- Browser and OS information
- Console errors (if any)

### Feature Requests

For new features, please:

- Check if the feature already exists
- Provide a clear use case
- Describe the expected behavior
- Consider backwards compatibility

---

## 🔒 Security

Security is a top priority for Concentria. Here's how we protect user data:

### Data Protection

- **Encryption**: All data in transit uses HTTPS/TLS
- **Hashing**: Passwords are hashed using bcrypt (10 rounds)
- **JWT Tokens**: Secure token-based authentication
- **Input Validation**: All inputs are validated and sanitized
- **CORS Protection**: Restricted cross-origin requests

### Privacy Measures

- **Data Minimization**: We only collect necessary data
- **User Control**: Users can delete their data anytime
- **Transparency**: Clear privacy policy and data usage
- **Consent**: Explicit consent for all data collection
- **Retention**: Automatic data cleanup after specified periods

### Security Reporting

If you discover a security vulnerability, please:

1. **Do not** open a public issue
2. Email us directly at security@concentria.com
3. Provide detailed information about the vulnerability
4. Give us reasonable time to fix the issue before disclosure

### Security Headers

The application implements security headers:

```http
Content-Security-Policy: default-src 'self'
X-Frame-Options: DENY
X-Content-Type-Options: nosniff
Referrer-Policy: strict-origin-when-cross-origin
```

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

```
MIT License

Copyright (c) 2025 Concentria Team

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

## 🙏 Acknowledgments

- **React Team** - For the amazing React framework
- **Express.js** - For the robust web framework
- **MongoDB** - For the flexible database solution
- **Tailwind CSS** - For the utility-first CSS framework
- **Chrome Extensions Team** - For the powerful extension APIs
- **Open Source Community** - For the countless libraries and tools

---

## 📞 Support & Contact

- **Website**: https://concentria.netlify.app
- **Documentation**: https://github.com/TheMarvelsCU/Concentria/wiki
- **Issues**: https://github.com/TheMarvelsCU/Concentria/issues
- **Discussions**: https://github.com/TheMarvelsCU/Concentria/discussions
- **Email**: support@concentria.com

---

<div align="center">

**Built with ❤️ for digital privacy and security**

[⭐ Star this project](https://github.com/TheMarvelsCU/Concentria) if you find it useful!

</div>
