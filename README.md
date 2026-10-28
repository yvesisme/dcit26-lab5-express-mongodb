# DCIT 26 Laboratory 5: Express and MongoDB

## Student Records REST API

This project is about creating an API for student records using Express and MongoDB. It can be used to add new students, view their information, update their records, and delete records when needed.

## Requirements

- Node.js and npm
- MongoDB Community Server

## Installation

1. Download or clone the repository.
2. Open the project folder in your terminal.
3. Run this command to install the needed packages:

   ```bash
   npm install
   ```

4. Create a `.env` file in the project folder. You can copy the settings from `.env.example`.
5. Put these settings in your `.env` file:

   ```env
   MONGODB_URI=mongodb://127.0.0.1:27017/lab5_students
   PORT=5000
   ```

6. Start MongoDB before running the project.

## Running the Project

Use this command to run the server during development:

```bash
npm run dev
```

Or use this command for normal startup:

```bash
npm start
```

The server runs on port 5000 by default.

## API Routes

| Method | Endpoint | Use |
|---|---|---|
| GET | `/api/health` | Check if the server is working |
| GET | `/api/students` | View all students |
| GET | `/api/students/:id` | View one student |
| POST | `/api/students` | Add a student |
| PUT | `/api/students/:id` | Edit a student's information |
| DELETE | `/api/students/:id` | Delete a student |

## Sample Student Data

Use this format when adding a student:

```json
{
  "fullName": "Alex Santos",
  "course": "BSIT",
  "yearLevel": 2,
  "section": "IT-2A"
}
```

## Student Fields

- `fullName` – Student's name. Required.
- `course` – Student's course. Required.
- `yearLevel` – Year level from 1 to 4.
- `section` – Student's section. Optional.
- `createdAt` – Date when the record was created. Automatically added.

Extra spaces in text fields are removed.

## Errors

- `400` – Invalid input or incorrect student ID format.
- `404` – Student record was not found.
- `500` – Server error.

## Database

The project uses MongoDB to save student information. The database name is `lab5_students`, and the collection is `students`. Mongoose is used to connect the application to the database.

## Security

The `.env` file contains local settings, so it should not be uploaded to GitHub. The `.gitignore` file prevents it from being tracked. Use `.env.example` as a guide when creating your own `.env` file.
