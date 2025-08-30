# NEOBIZE Airport Shuttle Reservation System

A full-stack web application for managing airport shuttle reservations with React frontend, Node.js backend, and PostgreSQL database.

## Project Structure

```
ride.neobize/
├── frontend/           # React + Vite frontend application
│   ├── src/           # React components and assets
│   ├── index.html     # Main HTML file
│   ├── package.json   # Frontend dependencies
│   └── ...           # Frontend configuration files
├── backend/           # Node.js Express backend API
│   ├── server.js      # Main server file
│   ├── package.json   # Backend dependencies
│   ├── .env.example   # Environment variables template
│   └── README.md      # Backend documentation
├── database/          # Database configuration and setup
│   ├── database.js    # Database connection and queries
│   └── POSTGRESQL_SETUP.md  # Database setup instructions
└── README.md          # This file
```

## Getting Started

### Prerequisites

- Node.js (v18 or higher)
- PostgreSQL (v12 or higher)
- npm or yarn package manager

### 1. Database Setup

```bash
# Navigate to database directory and install dependencies
cd database
npm install

# Install and start PostgreSQL
# Follow the instructions in database/POSTGRESQL_SETUP.md
# Create a database for the application
```

### 2. Backend Setup

```bash
# Navigate to backend directory
cd backend

# Install dependencies
npm install

# Copy environment variables template
cp .env.example .env

# Edit .env file with your database credentials and other settings
# Then start the backend server
npm start
```

The backend will run on `http://localhost:3007` by default.

### 3. Frontend Setup

```bash
# Navigate to frontend directory
cd frontend

# Install dependencies
npm install

# Start the development server
npm run dev
```

The frontend will run on `http://localhost:5173` by default.

## Features

- **Customer Portal**: Book shuttle reservations with real-time availability
- **User Dashboard**: View and manage existing reservations
- **Admin Dashboard**: Manage all reservations and user accounts
- **Email & WhatsApp Notifications**: Automated booking confirmations
- **Responsive Design**: Works on desktop and mobile devices

## API Endpoints

- `GET /api/health` - Health check
- `POST /api/reservations` - Create new reservation
- `POST /api/users/login` - User login
- `GET /api/users/:userId/reservations` - Get user reservations
- `GET /api/admin/users-with-reservations` - Admin: Get all users and reservations
- `PUT /api/admin/reservations/:id/status` - Admin: Update reservation status

## Environment Variables

### Backend (.env)
```
# Database
DATABASE_URL=postgresql://username:password@localhost:5432/database_name

# Email Configuration
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=587
EMAIL_USER=your-email@gmail.com
EMAIL_PASS=your-app-password
EMAIL_FROM=your-email@gmail.com
EMAIL_TO=reservations@neobize.com

# WhatsApp/Twilio Configuration
TWILIO_ACCOUNT_SID=your-twilio-account-sid
TWILIO_AUTH_TOKEN=your-twilio-auth-token
TWILIO_WHATSAPP_FROM=whatsapp:+14155238886
WHATSAPP_TO=whatsapp:+1234567890

# Frontend URL
FRONTEND_URL=http://localhost:5173
```

## Development

### Frontend Development
```bash
cd frontend
npm run dev    # Start development server
npm run build  # Build for production
npm run preview # Preview production build
```

### Backend Development
```bash
cd backend
npm run dev    # Start with nodemon (auto-restart)
npm start      # Start production server
```

## Deployment

1. Build the frontend: `cd frontend && npm run build`
2. Set up production environment variables
3. Deploy backend to your hosting service
4. Deploy frontend build files to a web server
5. Configure database connection for production

## Technologies Used

### Frontend
- React 18
- TypeScript
- Vite
- Tailwind CSS
- React Router

### Backend
- Node.js
- Express.js
- PostgreSQL
- Nodemailer (Email)
- Twilio (WhatsApp)

### Database
- PostgreSQL
- Custom database layer with connection pooling

## License

Private project for NEOBIZE LLC.
