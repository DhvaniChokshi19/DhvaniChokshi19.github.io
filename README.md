Three-Tier Application with Docker
This project demonstrates how to build a three-tier application using Docker. The application consists of three tiers: presentation tier (frontend), application tier (backend), and data tier (database).

Prerequisites
Before running the application, make sure you have Docker installed on your system. You can download and install Docker from the official Docker website.

Getting Started
Follow the steps below to build and run the three-tier application using Docker.

Clone the Repository:

git clone https://github.com/DhvaniChokshi19/three-tier-docker.git
cd three-tier-docker
Build Docker Images:

docker build -t presentation-tier .
docker build -t application-tier ./backend
Run Docker Containers:

docker run --name frontend-container -d -p 80:80 presentation-tier
docker run --name backend-container -d -p 3000:3000 application-tier
Accessing the Application:
Frontend: Open a web browser and navigate to http://localhost.
Backend: Access the backend API at http://localhost:3000.
Dockerfile Explanation
Presentation Tier (Frontend): The Dockerfile for the presentation tier uses the official Nginx image and copies the index.html file into the Nginx HTML directory.
Application Tier (Backend): The Dockerfile for the application tier uses the official Node.js image, sets the working directory, copies the server.js file into the working directory, exposes port 3000, and specifies the command to run the Node.js server.
Directory Structure

my-app/
├── backend/
│   ├── Dockerfile
│   └── server.js
├── Dockerfile
├── index.html
└── README.md
