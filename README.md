# FastAPI Task Management API

This is a FastAPI-based web service for managing tasks with API versioning. The API supports CRUD operations on tasks and requires an API key for authentication.

## Features
- **FastAPI**: High-performance web framework for building APIs with Python 3.7+.
- **API Key Authentication**: Secure endpoints with API key validation.
- **CRUD Operations**: Create, read, update, and delete tasks.
- **Environment Variables**: Uses `.env` file to store API keys securely.
- **API Versioning**: Supports `/apiv1/` and `/apiv2/` endpoints.

## Installation
### Clone the Repository
```bash
git clone https://github.com/yourusername/fastapi-task-api.git
cd fastapi-task-api
```

### Set Up a Virtual Environment (Optional but Recommended)
```bash
python -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`
```

### Install Dependencies
```bash
pip install fastapi uvicorn python-dotenv
```

### Create a `.env` File
```plaintext
API_KEY=your_secure_api_key
```

### Run the Application
```bash
uvicorn main:app --reload
```

The `--reload` flag enables auto-reloading, so the server restarts on code changes.

## Usage
Once the server is running, access the API at `http://127.0.0.1:8000`.

## API Endpoints

### Authentication
All requests must include the API key in the `Authorization` header:
```plaintext
Authorization: Bearer your_secure_api_key
```

### API v1 Endpoints

#### 1. **GET** `/apiv1/`
**Description**: Welcome message for API v1.
```json
{
  "message": "Welcome to API v1"
}
```

#### 2. **GET** `/apiv1/tasks/`
**Description**: Retrieve all tasks.
```json
{
  "status": "ok",
  "tasks": [
    {"task_id": 1, "task_title": "Test 1", "task_desc": "Complete FastAPI basics", "is_finished": false}
  ]
}
```

#### 3. **GET** `/apiv1/tasks/{task_id}`
**Description**: Retrieve a specific task by ID.

#### 4. **POST** `/apiv1/tasks/`
**Description**: Create a new task.
```json
{
  "task_title": "New Task",
  "task_desc": "Learn FastAPI authentication"
}
```

#### 5. **PATCH** `/apiv1/tasks/{task_id}`
**Description**: Update a task (title, description, completion status).

#### 6. **DELETE** `/apiv1/tasks/{task_id}`
**Description**: Delete a task.

### API v2 Endpoints
API v2 follows the same structure as v1 but has separate data storage.

## Deployment
To deploy on Render or another cloud provider:
```bash
export PORT=8000
uvicorn main:app --host 0.0.0.0 --port $PORT
```

## Contributing
Contributions are welcome! Please submit a pull request.

## Acknowledgments

- **Sir Paulo** for the idea!
- **FastAPI** for providing a modern, high-performance web framework.
- **Dotenv** for managing environment variables securely.
- **Python** for being an amazing programming language.
