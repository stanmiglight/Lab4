# To-Do API with FastAPI

## Description
This project is a simple task management API developed with **FastAPI**. It demonstrates:
- API authentication using an API key from an `.env` file.
- Two versions of task management APIs (**v1** and **v2**) with separate task databases.
- CRUD operations (Create, Read, Update, Delete) for managing tasks.

The project includes:
- **API Key Protection**: Authentication via an API key in the request header.
- Two API versions (**v1** and **v2**) with independent routes and task databases.
- Integration with FastAPI for endpoint routing and HTTP response handling.

---

## Features
- **API Authentication**: Secure access to endpoints using an API key stored in an `.env` file.
- **Task Management**: Perform CRUD operations on tasks.
- **Versioned Endpoints**: Two versions of the API for managing tasks independently.

---

## Endpoints

### General
- **Authorization Header**: All endpoints require the header:
  ```
  Authorization: Bearer <API_KEY>
  ```

### API v1
#### 1. Root Endpoint
- **GET** `/apiv1/`
  - **Response**: Welcome message for API v1.

#### 2. Task Management
- **GET** `/apiv1/tasks/`
  - Retrieves all tasks.

- **GET** `/apiv1/tasks/{task_id}`
  - Retrieves a specific task by its ID.

- **POST** `/apiv1/tasks/`
  - Creates a new task.
  - **Parameters**:
    - `task_title`: Title of the task (string).
    - `task_desc`: Description of the task (string).

- **DELETE** `/apiv1/tasks/{task_id}`
  - Deletes a task by its ID.

- **PATCH** `/apiv1/tasks/{task_id}`
  - Updates task details.
  - **Parameters**:
    - `task_title`: (Optional) Updated task title.
    - `task_desc`: (Optional) Updated task description.
    - `is_finished`: (Optional) Updated task completion status.

### API v2
#### 1. Root Endpoint
- **GET** `/apiv2/`
  - **Response**: Welcome message for API v2.

#### 2. Task Management
- **GET** `/apiv2/tasks/`
  - Retrieves all tasks.

- **GET** `/apiv2/tasks/{task_id}`
  - Retrieves a specific task by its ID.

- **POST** `/apiv2/tasks/`
  - Creates a new task.
  - **Parameters**:
    - `task_title`: Title of the task (string).
    - `task_desc`: Description of the task (string).

- **DELETE** `/apiv2/tasks/{task_id}`
  - Deletes a task by its ID.

- **PATCH** `/apiv2/tasks/{task_id}`
  - Updates task details.
  - **Parameters**:
    - `task_title`: (Optional) Updated task title.
    - `task_desc`: (Optional) Updated task description.
    - `is_finished`: (Optional) Updated task completion status.

---

## Installation

### Prerequisites
- Python 3.7+
- **FastAPI** and **Uvicorn** installed.

### Steps
1. Clone the repository.
2. Install dependencies using:
   ```bash
   pip install -r requirements.txt
   ```
3. Create a `.env` file in the root directory and add your API key:
   ```env
   API_KEY=your_api_key_here
   ```
4. Run the application using Uvicorn:
   ```bash
   uvicorn main:app --reload
   ```
5. Access the API at `http://127.0.0.1:8000`.

---

## Usage

### Testing Endpoints
- Use tools like **Postman**, **curl**, or your browser to test the API.
- Add the `Authorization` header for all requests:
  ```
  Authorization: Bearer <API_KEY>
  ```

### Example Request
- **Get All Tasks (v1)**
  ```bash
  curl -H "Authorization: Bearer your_api_key_here" http://127.0.0.1:8000/apiv1/tasks/
  ```

---

## Acknowledgments
- Developed with FastAPI for rapid and efficient API creation.
- Inspired by the need for secure and versioned API design.

