# CommunityHub API - Week 11

CommunityHub API with MongoDB integration and JWT authentication.

## Features

- User registration and login with JWT authentication
- Password hashing with bcrypt
- Post CRUD operations with MongoDB
- Comment management on posts
- Authorization middleware for protected routes

## MongoDB Atlas Setup

1. Go to [mongodb.com/atlas](https://www.mongodb.com/atlas)
2. Create an account with your email (colboykenya@gmail.com)
3. Create a new cluster (free tier)
4. Add database user (username/password)
5. Whitelist IP `0.0.0.0/0` for development
6. Get your connection string and update `.env`

## Installation

```bash
npm install
```

## Environment Variables

Create a `.env` file with:

```
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
JWT_EXPIRES_IN=7d
PORT=3000
```

## Running the Server

```bash
npm start
```

## API Endpoints

### Authentication
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - Login user
- `GET /api/auth/me` - Get current user (protected)
- `PUT /api/auth/me` - Update profile (protected)

### Posts
- `GET /api/posts` - Get all posts
- `GET /api/posts/:id` - Get single post
- `POST /api/posts` - Create post (protected)
- `PUT /api/posts/:id` - Update post (protected, author only)
- `DELETE /api/posts/:id` - Delete post (protected, author only)
- `POST /api/posts/:id/like` - Like post

### Comments
- `GET /api/posts/:postId/comments` - Get comments for post
- `POST /api/posts/:postId/comments` - Add comment
- `DELETE /api/posts/:postId/comments/:commentId` - Delete comment