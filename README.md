# AI Code Reviewer

## Description

This project is an **AI-powered Code Reviewer** developed as a full-stack web application for automated source-code analysis.

The application allows users to submit source code through the frontend, sends the code to a Node.js/Express backend, and uses the **Google Gemini API** to analyze the submitted code and generate an AI-based code review.

The complete application has been **containerized using Docker** and is managed using **Docker Compose**, with separate containers for the frontend and backend.


## Technologies Used

### Frontend

* React.js
* Vite
* JavaScript

### Backend

* Node.js
* Express.js
* REST API

### AI Integration

* Google Gemini API
* Gemini Flash Model

### DevOps / Deployment

* Docker
* Docker Compose
* Dockerfile
* Docker Containers

## Application Features

* Submit source code for review
* Send code from frontend to backend through a REST API
* AI-powered code analysis using Google Gemini
* Receive automated code-review feedback
* Separate frontend and backend services
* Dockerized application
* Docker Compose configuration for running multiple services
* Environment-based API key configuration

## Docker Implementation

The application is containerized using Docker.

Two separate Docker containers are used:

```text
Frontend Container
localhost:5173
        │
        ▼
Backend Container
localhost:3000
        │
        ▼
Google Gemini API
```

### Backend Dockerfile

The backend has its own Dockerfile that:

* Uses Node.js as the base image
* Sets the working directory
* Copies package files
* Installs dependencies
* Copies the backend source code
* Exposes port 3000
* Starts the backend application

### Frontend Dockerfile

The frontend also has its own Dockerfile that:

* Uses Node.js as the base image
* Sets the working directory
* Copies package files
* Installs dependencies
* Copies the frontend source code
* Exposes port 5173
* Starts the frontend development server

## Docker Compose

Docker Compose is used to manage both frontend and backend containers together.

The project contains:

```text
docker-compose.yml
```

The Compose configuration defines:

* Backend service
* Frontend service
* Container names
* Port mappings
* Docker build contexts
* Service dependency
* Environment file configuration
* Restart configuration

## Docker Services

### Backend

```text
Container: code-reviewer-backend
Port: 3000
```

### Frontend

```text
Container: code-reviewer-frontend
Port: 5173
```

## Docker Commands

### Build and Start the Application

From the project root:

```bash
docker compose up --build
```

### Run in Detached Mode

```bash
docker compose up --build -d
```

### Check Running Containers

```bash
docker compose ps
```

### View Backend Logs

```bash
docker compose logs backend
```

### View Frontend Logs

```bash
docker compose logs frontend
```

### View All Logs

```bash
docker compose logs
```

### Stop Containers

```bash
docker compose down
```

### Rebuild Containers

```bash
docker compose up --build
```

### Check Environment Variable Inside Backend Container

```bash
docker compose exec backend printenv GOOGLE_GEMINI_KEY
```

## How to Run

### 1. Clone the Repository

```bash
git clone <repository-url>
```

### 2. Navigate to the Project

```bash
cd code-reviewer
```

### 3. Create the Backend Environment File

Create:

```text
BackEnd/.env
```

Add the Gemini API key:

```env
GOOGLE_GEMINI_KEY=your_api_key_here
```

### 4. Start the Application

Run:

```bash
docker compose up --build
```

Or run it in detached mode:

```bash
docker compose up --build -d
```

### 5. Open the Application

Frontend:

```text
http://localhost:5173
```

Backend:

```text
http://localhost:3000
```




##

##

##
