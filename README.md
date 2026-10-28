# DCIT 26 Laboratory 5: Express and MongoDB

## Student Records REST API

A REST API built with Node.js, Express, MongoDB, and Mongoose to manage student records.

## Requirements

- Node.js and npm
- MongoDB Community Server

## Installation

1. Clone or download this project.
2. Open a terminal in the project folder.
3. Install the dependencies:

   ```bash
   npm install
   ```

4. Create a local `.env` file in the project root using `.env.example` as a reference.
5. Configure the MongoDB connection string in `.env`:

   ```env
   MONGODB_URI=mongodb://127.0.0.1:27017/lab5_students
   PORT=5000
   ```

6. Make sure MongoDB is running.

## Running the Server

For development:

```bash
npm run dev
```

For normal startup:

```bash
npm start
```

The API runs on port 5000 by default.

## API Routes

| Method | Endpoint | Description |
|---|---|---|
| GET | `/api/health` | Check API status |
| GET | `/api/students` | Retrieve all students |
| GET | `/api/students/:id` | Retrieve a student by ID |
| POST | `/api/students` | Create a student |
| PUT | `/api/students/:id` | Update a student |
| DELETE | `/api/students/:id` | Delete a student |

## Student Request Example

```json
{
  "fullName": "Alex Santos",
  "course": "BSIT",
  "yearLevel": 2,
  "section": "IT-2A"
}
```

## Student Fields

- `fullName`: Required string; whitespace is trimmed.
- `course`: Required string; whitespace is trimmed.
- `yearLevel`: Required number from 1 to 4.
- `section`: Optional string; whitespace is trimmed.
- `createdAt`: Date that defaults to the current time.

## Error Handling

- `400 Bad Request`: Invalid input or malformed ID.
- `404 Not Found`: Student record does not exist.
- `500 Internal Server Error`: Unexpected server error.

## Database

The application uses MongoDB through Mongoose. Student records are stored in the `lab5_students` database in the `students` collection.

## Security

The local `.env` file contains the local configuration and must not be committed. The `.gitignore` file excludes it from Git tracking. Use `.env.example` as the configuration template.
