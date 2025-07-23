 CEMS - Campus Event Management System (Backend)

This is the backend server for **CEMS**, a Campus Event Management System built with Node.js, Express, and MongoDB. It powers the core functionalities of student event registrations, admin event creation, user authentication, and participant management.

 Features

-  User & Admin login/signup with JWT-based authentication
-  Event creation with date, deadline, and participant limits
-  Student registration to events with validations (deadline, full event, duplicates)
-  Admin can update/delete events and view participants
-  Search, filter, and pagination of events
-  HttpOnly secure cookies for login sessions

Tech Stack

- Node.js
- Express.js
- MongoDB (Mongoose)
- JSON Web Tokens (JWT)
- dotenv
- bcrypt.js
- CORS
- cookie-parser

Folder Structure

backend/
│
├── controllers/ # Business logic
├── middleware/ # Authentication & authorization
├── models/ # Mongoose schemas
├── routes/ # API endpoints
├── config/ # Environment variables
├── utils/ # Reusable helper functions
├── .env.example # Sample environment config
├── server.js # Entry point
└── README.md


Getting Started

1. Clone the repository

git clone https://github.com/DineshKarthick03/CEMS-BACKEND.git
cd CEMS-BACKEND
2. Install dependencies

npm install
3. Create your .env file
MONGO_URI=your_mongodb_uri
JWT_SECRET=your_jwt_secret
NODE_ENV=development
PORT=5000
4. Start the server

npm run dev
Server runs at: http://localhost:5000

Authentication
Login/signup returns a JWT cookie stored securely via httpOnly.

Authenticated routes use protectRoute middleware.

Admin routes use additional isAdmin middleware.

API Routes
Auth Routes
Method	Endpoint	Description
POST	/api/auth/signup	Create new user/admin
POST	/api/auth/login	Login and get JWT
POST	/api/auth/logout	Logout (clear cookie)
GET	/api/auth/authCheck	Verify session

Event Routes
Method	Endpoint	Description
GET	/api/events/upcoming	List upcoming events (with pagination)
GET	/api/events/past	List past events (with pagination)
GET	/api/events/search?name=XYZ	Search event by name
POST	/api/events/register/:eventId	Register for an event (student only)
POST	/api/events/create	Create event (admin only)
PUT	/api/events/update/:eventId	Update event (admin only)
DELETE	/api/events/delete/:eventId	Delete event (admin only)
GET	/api/events/participants/:eventId	View event participants (admin only)

License
This project is licensed under the MIT License.
Feel free to contribute, fork, or use it for your campus projects!


Let me know if you want a logo, badges, or want to add frontend link later.
