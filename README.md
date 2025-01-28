# Task Management API (v1 & v2)

A FastAPI-based task management system with two API versions, featuring authentication and basic CRUD operations.

## Features
- Dual API versions (v1 & v2) with separate databases
- API key authentication
- CRUD operations for tasks
- Environment variable configuration
- Render.com deployment ready

## Requirements
- Python 3.9+
- FastAPI
- Uvicorn
- python-dotenv

## Installation

1. Clone the repository:
```bash
git clone [your-repo-url]
cd [repo-directory]
Install dependencies:

bash
Copy
pip install -r requirements.txt
Create .env file:

env
Copy
API_KEY=your_secret_key_here
API Documentation
Authentication
Add API key to request headers:

http
Copy
Authorization: Bearer your_api_key_here
API Endpoints
API v1
Method	Endpoint	Description
GET	/apiv1/	API root (requires auth)
GET	/apiv1/tasks/	List all tasks
GET	/apiv1/tasks/{task_id}	Get single task
POST	/apiv1/tasks/	Create new task
DELETE	/apiv1/tasks/{task_id}	Delete task
PATCH	/apiv1/tasks/{task_id}	Update task
API v2
Same endpoints structure under /apiv2/ path

Example Requests
Create Task (v1):

bash
Copy
curl -X POST "http://localhost:8000/apiv1/tasks/" \
     -H "Content-Type: application/json" \
     -d '{"task_title": "New Task", "task_desc": "Task description"}'
Update Task (v2):

bash
Copy
curl -X PATCH "http://localhost:8000/apiv2/tasks/1" \
     -H "Content-Type: application/json" \
     -d '{"is_finished": true}'
Deployment (Render.com)
Set environment variables:

API_KEY: Your secret key

PORT: 8000

Add requirements.txt with:

Copy
fastapi
uvicorn
python-dotenv
Configure build command:

bash
Copy
pip install -r requirements.txt
Set start command:

bash
Copy
python main.py
Project Structure
Copy
.
├── main.py         # Main application code
├── .env            # Environment variables
├── requirements.txt# Dependencies
└── README.md       # Documentation
Notes
Databases are in-memory (data resets on server restart)

API v1 and v2 maintain separate task databases

Default port: 8000 (configurable via PORT environment variable)
