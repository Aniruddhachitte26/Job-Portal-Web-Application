# Job Portal Web Application

## Overview

Job Portal is a full-stack web application that connects job seekers with potential employers. The platform features separate interfaces for administrators and employees, with role-based access control ensuring users can only access authorized content. Administrators can manage users and job postings, while employees can browse job listings and company profiles.

## Features

### Authentication
- Secure login with email and password
- Role-based access control (Admin/Employee)
- Protected routes requiring authentication
- Session persistence

### Admin Portal
- Dashboard displaying employee information
- Add and manage job listings
- View all registered users

### Employee Portal
- Browse available job listings with search and filter capabilities
- View detailed company profiles
- Contact form for inquiries

### Common Features
- Responsive design for all devices
- Modern user interface with Material UI
- Intuitive navigation with React Router

## Technology Stack

### Frontend
- **React.js**: UI components and logic
- **Redux & Redux Toolkit**: State management
- **React Router**: Navigation and routing
- **Material UI**: Component library and styling
- **Axios**: API request handling

### Backend
- **Node.js**: Runtime environment
- **Express**: Web server framework
- **MongoDB**: NoSQL database
- **Mongoose**: ODM for MongoDB
- **Bcrypt.js**: Password hashing
- **Multer**: File uploads
- **CORS**: Cross-origin resource sharing

## Project Structure

```
project-root/
├── frontend/                  # React frontend application
│   ├── public/                # Public assets
│   ├── src/
│   │   ├── components/        # UI components
│   │   │   ├── admin/         # Admin-specific components
│   │   │   ├── employee/      # Employee-specific components
│   │   │   └── ...            # Shared components
│   │   ├── redux/             # Redux state management
│   │   │   ├── actions/       # Redux actions
│   │   │   ├── reducers/      # Redux reducers
│   │   │   ├── store.js       # Redux store configuration
│   │   │   └── types.js       # Action type constants
│   │   ├── routes/            # Route configurations
│   │   ├── services/          # API services
│   │   └── ...                # Main application files
│   └── ...                    # Configuration files
├── backend/                   # Node.js backend application
│   ├── app/
│   │   ├── controllers/       # Request handlers
│   │   ├── middleware/        # Express middleware
│   │   ├── models/            # Mongoose models
│   │   └── routes/            # API route definitions
│   ├── config/                # Configuration files
│   ├── images/                # Uploaded images storage
│   └── ...                    # Server and configuration files
```

## Setup Instructions

### Prerequisites
- Node.js (v18 or later)
- npm or yarn
- MongoDB

### Backend Setup
1. Navigate to the backend directory:
   ```
   cd backend
   ```

2. Install dependencies:
   ```
   npm install
   ```

3. Create an `images` directory in the root of the backend folder for file uploads:
   ```
   mkdir images
   ```

4. Update MongoDB connection string in `config/db.js` if needed

5. Start the backend server:
   ```
   npm run dev
   ```
   The server will run on http://localhost:3000

### Frontend Setup
1. Navigate to the frontend directory:
   ```
   cd frontend
   ```

2. Install dependencies:
   ```
   npm install
   ```

3. Start the development server:
   ```
   npm run dev
   ```
   The application will be available at http://localhost:5173

## API Documentation

### Authentication Endpoints
- `POST /login` - Authenticate a user

### User Management Endpoints
- `POST /` - Create a new user
- `PUT /edit` - Update user details
- `DELETE /delete` - Delete a user
- `GET /getUser` - Get all users
- `POST /uploadImage` - Upload a user profile image

### Job Management Endpoints
- `POST /jobs/create` - Create a new job listing
- `GET /jobs` - Get all job listings (with pagination)
- `GET /jobs/:id` - Get a specific job by ID
- `PUT /jobs/:id` - Update a job listing
- `DELETE /jobs/:id` - Delete a job listing

## User Roles and Access Control

### Admin
- Can view a dashboard of all employees
- Can create and manage job listings
- Has access to all administrative functions

### Employee
- Can view and search job listings
- Can explore company profiles
- Can submit inquiries through the contact form

## Test Accounts

For testing purposes, you can use the following credentials:

### Admin Account
- Email: admin@example.com
- Password: Admin@123

### Employee Account
- Email: employee@example.com
- Password: Employee@123

## Screenshots

### Admin Dashboard
![Admin Dashboard](https://example.com/screenshots/admin-dashboard.png)

### Job Listings
![Job Listings](https://example.com/screenshots/job-listings.png)

### Company Showcase
![Company Showcase](https://example.com/screenshots/company-showcase.png)

## Additional Information

### State Management
The application uses Redux for state management with the following stores:
- **Auth Store**: Manages authentication state
- **Job Store**: Manages job listings and related operations
- **User Store**: Manages user data and operations

### Form Validation
- Client-side validation for all forms
- Server-side validation using custom middleware
- Error messages displayed to users

### Security Features
- Passwords hashed using bcrypt
- Protected routes for authenticated users
- Role-based access control
- Input validation to prevent injection attacks

## Future Enhancements

- Job application submission functionality
- User profile customization
- Advanced search and filtering options
- Email notifications
- Resume parser
- Analytics dashboard for administrators
- Internationalization support

## Troubleshooting

### Common Issues
- If the backend server fails to connect to MongoDB, verify your connection string in `config/db.js`
- If image uploads aren't working, ensure the `images` directory exists in the backend root
- For CORS issues, verify that the backend is properly configured to accept requests from the frontend origin

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Contributors

- Your Name
- Additional Contributors

## Acknowledgements

- Material UI for the component library
- MongoDB Atlas for database hosting
- React and Redux communities for excellent documentation
