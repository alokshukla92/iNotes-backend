Certainly! Here's a `README.md` template for your iNotes backend application. This README will provide instructions and details about setting up and using your Node.js application with MongoDB for managing user authentication and notes.

---

# iNotes Backend Application

This backend application is designed to support a todo app along with user registration using Node.js and MongoDB.

## Features

- User registration and authentication using JWT tokens
- CRUD operations for managing user notes

## Technologies Used

- Node.js
- Express.js
- MongoDB (with Mongoose)
- JWT for authentication
- bcryptjs for password hashing
- Express-validator for input validation

## Prerequisites

Before you begin, ensure you have the following installed on your machine:

- Node.js (v14.x or higher)
- MongoDB (Make sure MongoDB server is running locally or have connection URI for MongoDB Atlas)

## Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/alokshukla92/iNotes-backend
   cd iNotes-backend
   ```

2. Install dependencies:

   ```bash
   npm install
   ```

3. Set up environment variables:

   Create a `.env` file in the root directory and add the following:

   ```plaintext
   JWT_SECRET=your_jwt_secret
   ```
   - `JWT_SECRET`: Secret key for JWT token generation.

4. Start the server:

   ```bash
   npm start
   ```

   This will start the server at `http://localhost:5000` (or your specified port).

## API Endpoints

### Authentication

#### Create User

- **URL:** `/api/auth/createuser`
- **Method:** `POST`
- **Body:**
  ```json
  {
    "name": "Your Name",
    "email": "youremail@example.com",
    "password": "yourpassword"
  }
  ```
- **Description:** Registers a new user.

#### Login User

- **URL:** `/api/auth/login`
- **Method:** `POST`
- **Body:**
  ```json
  {
    "email": "youremail@example.com",
    "password": "yourpassword"
  }
  ```
- **Description:** Logs in an existing user.

#### Get User Details

- **URL:** `/api/auth/getuser`
- **Method:** `POST`
- **Headers:** `auth-token: <token>`
- **Description:** Retrieves details of the logged-in user.

### Notes

#### Fetch All Notes

- **URL:** `/api/notes/fetchallnotes`
- **Method:** `GET`
- **Headers:** `auth-token: <token>`
- **Description:** Retrieves all notes of the logged-in user.

#### Add Note

- **URL:** `/api/notes/addnote`
- **Method:** `POST`
- **Headers:** `auth-token: <token>`
- **Body:**
  ```json
  {
    "title": "Note Title",
    "description": "Note Description",
    "tag": "Note Tag"
  }
  ```
- **Description:** Adds a new note for the logged-in user.

#### Update Note

- **URL:** `/api/notes/updatenote/:id`
- **Method:** `PUT`
- **Headers:** `auth-token: <token>`
- **Body:** (Fields to be updated)
  ```json
  {
    "title": "Updated Title",
    "description": "Updated Description",
    "tag": "Updated Tag"
  }
  ```
- **Description:** Updates an existing note.

#### Delete Note

- **URL:** `/api/notes/deletenote/:id`
- **Method:** `DELETE`
- **Headers:** `auth-token: <token>`
- **Description:** Deletes an existing note.

## Error Handling

- The API endpoints handle various error scenarios and return appropriate status codes and error messages.
- All sensitive information (like passwords) is securely hashed and stored in the database.

## License

This project is licensed under the MIT License - see the LICENSE file for details.
