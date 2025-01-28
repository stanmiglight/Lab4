# Task Management API (v1 & v2)

A FastAPI-based task management system with two API versions, featuring authentication and basic CRUD operations.

## Table of Contents
- [Features](#features)
- [Requirements](#requirements)
- [Installation](#installation)
- [Configuration](#configuration)
- [API Documentation](#api-documentation)
- [Example Requests](#example-requests)
- [Deployment](#deployment)
- [Project Structure](#project-structure)
- [Notes](#notes)

## Features
- Dual API versions (v1 & v2) with separate databases
- API key authentication
- Full CRUD operations for tasks
- Environment variable configuration
- Render.com deployment ready
- Status code handling (401, 404, 204 responses)

## Requirements
- Python 3.9+
- FastAPI
- Uvicorn
- python-dotenv

## Installation

1. Clone the repository:
```bash
git clone https://github.com/your-username/your-repo.git
cd your-repo
Install dependencies:

bash
Copy
pip install -r requirements.txt
Create .env file:

bash
Copy
echo "API_KEY=your_secret_key_here" > .env
Configuration
Add your API key to the .env file:

env
Copy
API_KEY=your_actual_secret_key
API Documentation
Authentication
Include API key in request headers:

http
Copy
Authorization: Bearer your_api_key_here
Endpoints
API v1
Method	Endpoint	Description
GET	/apiv1/	API root (requires auth)
GET	/apiv1/tasks/	List all tasks
GET	/apiv1/tasks/{task_id}	Get single task
POST	/apiv1/tasks/	Create new task
DELETE	/apiv1/tasks/{task_id}	Delete task
PATCH	/apiv1/tasks/{task_id}	Update task
API v2
Same endpoint structure under /apiv2/ path

Example Requests
Create Task (v1):

bash
Copy
curl -X POST "http://localhost:8000/apiv1/tasks/" \
     -H "Authorization: Bearer your_api_key" \
     -H "Content-Type: application/json" \
     -d '{"task_title": "New Task", "task_desc": "Task description"}'
Update Task (v2):

bash
Copy
curl -X PATCH "http://localhost:8000/apiv2/tasks/1" \
     -H "Authorization: Bearer your_api_key" \
     -H "Content-Type: application/json" \
     -d '{"is_finished": true}'
Get All Tasks (v1):

bash
Copy
curl -H "Authorization: Bearer your_api_key" http://localhost:8000/apiv1/tasks/
Deployment
Render.com Setup
Set environment variables:

API_KEY: Your secret key

PORT: 8000

Add requirements.txt with:

Copy
fastapi==0.68.0
uvicorn==0.15.0
python-dotenv==0.19.0
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
├── main.py             # Main application logic
├── .env                # Environment variables (gitignored)
├── requirements.txt    # Dependency list
└── README.md           # This documentation
Notes
⚠️ In-memory databases: Data resets on server restart

🔐 API key security: Never commit .env to version control

🌐 Default port: 8000 (customize via PORT environment variable)

🔄 API v1 and v2 maintain completely separate databases
