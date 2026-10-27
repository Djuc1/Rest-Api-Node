# Rest API Node

A Node.js + Express + MongoDB REST API for a social media-style application. It includes user registration/login, profile updates, follow/unfollow logic, and post management.

## Features

- User authentication with password hashing using bcrypt
- User CRUD operations
- Follow and unfollow users
- Post creation, update, delete, like/dislike
- Timeline and profile post retrieval
- Security middleware with Helmet and request logging with Morgan

## Tech Stack

- Node.js
- Express.js
- MongoDB with Mongoose
- dotenv for environment configuration
- bcrypt for password hashing
- Helmet for HTTP security headers
- Morgan for request logging

## Project Structure

```text
Rest-Api-Node/
├── index.js
├── package.json
├── .env
├── models/
│   ├── Post.js
│   └── User.js
├── routes/
│   ├── auth.js
│   ├── posts.js
│   └── users.js
└── README.md
```

## Prerequisites

- Node.js 18+ recommended
- MongoDB running locally or a MongoDB Atlas connection string

## Installation

1. Clone the repository
2. Install dependencies:

```bash
npm install
```

3. Create a `.env` file in the project root and add your MongoDB connection string:

```env
MONGO_URL=mongodb://127.0.0.1:27017/socials
```

If you are using MongoDB Atlas, replace it with your Atlas connection string.

## Running the Server

```bash
npm start
```

The server starts on port `8800`.

## API Endpoints

### Auth

- `POST /api/auth/register` - Register a new user
- `POST /api/auth/login` - Log in a user

### Users

- `PUT /api/users/:id` - Update a user
- `DELETE /api/users/:id` - Delete a user
- `GET /api/users?userId=...` - Get user by ID
- `GET /api/users?username=...` - Get user by username
- `GET /api/users/friends/:userId` - Get a user's friends
- `PUT /api/users/:id/follow` - Follow a user
- `PUT /api/users/:id/unfollow` - Unfollow a user

### Posts

- `POST /api/post/` - Create a post
- `PUT /api/post/:id` - Update a post
- `DELETE /api/post/:id` - Delete a post
- `PUT /api/post/:id/like` - Like or unlike a post
- `GET /api/post/:id` - Get a post by ID
- `GET /api/post/timeline/:userId` - Get timeline posts
- `GET /api/post/profile/:username` - Get posts for a user profile

## Notes

This application is a backend API for a social application and is designed to be extended with authentication middleware, validation, and front-end integration.
