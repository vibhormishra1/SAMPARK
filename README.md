# SAMPARK

A full-stack web application that replicates the core functionality of Zoom, enabling users to create and join video meetings, chat in real-time, and manage their meeting history. 

## Features

- **User Authentication**: Secure user registration and login using JWT tokens and bcrypt password hashing.
- **Video Meetings**: Real-time video and audio communication powered by WebRTC and Socket.io.
- **Real-Time Chat**: In-meeting text chat capabilities using WebSocket connections.
- **Meeting History**: Users can view a log of their past meetings and activities.
- **Modern UI**: A responsive, clean user interface built with React and Material UI.

## Tech Stack

### Frontend
- **React.js**: Core frontend library.
- **Material UI (@mui/material)**: UI component library for modern, accessible design.
- **Socket.io-client**: Client-side library for real-time WebSocket communication.
- **React Router Dom**: For client-side routing.
- **Axios**: For making HTTP requests to the backend API.

### Backend
- **Node.js & Express.js**: Server environment and web framework.
- **Socket.io**: Real-time event-based communication for signaling (WebRTC) and chat.
- **MongoDB & Mongoose**: NoSQL database and ODM for storing user credentials and meeting history.
- **Bcrypt**: For secure password hashing.
- **Crypto**: For generating secure random tokens for user authentication.

## Project Structure

The repository is divided into two main directories:

- `/frontend`: Contains the React.js client application.
- `/backend`: Contains the Node.js/Express.js server application.

### Backend Architecture
- `src/app.js`: Main entry point for the server. Connects to MongoDB, configures middleware, sets up routes, and initializes the Socket.io server.
- `src/controllers/socketmanager.js`: Handles all Socket.io events, including users joining calls, exchanging WebRTC signaling data, sending chat messages, and handling disconnections.
- `src/controllers/user.controller.js`: Contains business logic for user authentication (login/register) and fetching/adding to user meeting history.
- `src/models/`: Contains Mongoose database schemas (`user.model.js`, `meeting.model.js`).
- `src/routes/`: Contains Express route definitions (`users.routes.js`).

## Getting Started

### Prerequisites
- Node.js (v14 or higher)
- MongoDB Database (Local or MongoDB Atlas)

### Installation

1. **Clone the repository**

2. **Backend Setup**
   ```bash
   cd backend
   npm install
   ```
   *Note: Ensure you update the MongoDB connection string in `backend/src/app.js` or use environment variables to configure your database connection and port.*

3. **Frontend Setup**
   ```bash
   cd frontend
   npm install
   ```

### Running the Application

1. **Start the Backend Server**
   ```bash
   cd backend
   npm run dev
   ```
   The backend will run on `http://localhost:8000`.

2. **Start the Frontend Client**
   ```bash
   cd frontend
   npm start
   ```
   The frontend will run on `http://localhost:3000`.

## License

This project is licensed under the ISC License.
