# Notes API

A RESTful API for managing notes with CRUD functionality built using Hapi.js framework.

## 📋 Overview

Notes API is a simple yet powerful backend service that allows users to create, read, update, and delete notes. The application follows clean architecture principles with proper error handling and validation.

## 🛠️ Technology Stack

- **Runtime**: Node.js
- **Framework**: Hapi.js
- **Validation**: Joi
- **ID Generation**: nanoid
- **Testing**: Postman Collection & Environment
- **Code Quality**: ESLint with Dicoding Academy configuration

## 🏗️ Project Structure

```
notes-api/
├── src/
│   ├── api/                # API layer (handlers, routes)
│   │   └── notes/
│   ├── exceptions/         # Custom error classes
│   ├── services/           # Business logic
│   │   └── inMemory/
│   ├── validator/          # Request payload validation
│   │   └── notes/
│   └── server.js           # Server configuration
├── .gitignore
├── eslint.config.mjs       # ESLint configuration
├── package.json
└── README.md
```

## 🚀 Features

- Create a new note with title, body, and tags
- Retrieve all notes
- Get a specific note by ID
- Update an existing note
- Delete a note
- Comprehensive error handling
- Input validation
- CORS support

## 🔄 API Endpoints

| Method | Endpoint     | Description             |
|--------|--------------|-------------------------|
| POST   | /notes       | Create a new note       |
| GET    | /notes       | Get all notes           |
| GET    | /notes/{id}  | Get a specific note     |
| PUT    | /notes/{id}  | Update a specific note  |
| DELETE | /notes/{id}  | Delete a specific note  |

## 📦 Request & Response Examples

### Create a Note

**Request:**
```json
POST /notes
{
  "title": "Sample Note",
  "body": "This is the content of the note",
  "tags": ["important", "reminder"]
}
```

**Response:**
```json
{
  "status": "success",
  "message": "Catatan berhasil ditambahkan",
  "data": {
    "noteId": "unique-note-id"
  }
}
```

### Get a Note

**Request:**
```
GET /notes/{id}
```

**Response:**
```json
{
  "status": "success",
  "data": {
    "note": {
      "id": "note-id",
      "title": "Sample Note",
      "body": "This is the content of the note",
      "tags": ["important", "reminder"],
      "createdAt": "2025-01-01T00:00:00.000Z",
      "updatedAt": "2025-01-01T00:00:00.000Z"
    }
  }
}
```

## ⚙️ Setup & Installation

1. Clone the repository
   ```bash
   git clone https://github.com/yourusername/notes-api.git
   cd notes-api
   ```

2. Install dependencies
   ```bash
   npm install
   ```

3. Start the development server
   ```bash
   npm run start:dev
   ```

4. For production
   ```bash
   npm run start:prod
   ```

## 🧪 Testing

The project includes a comprehensive Postman collection for API testing. Import both the collection and environment files into Postman to run tests:

- `Notes_API_Test.postman_collection.json`
- `Notes_API_Test.postman_environment.json`

## 🔍 Code Quality

Maintain code quality by running the linter:
```bash
npm run lint
```

## 📝 Future Improvements

- Add authentication and authorization
- Implement persistent storage (database)
- Add search functionality
- Implement pagination for the GET /notes endpoint
- Add user management features
