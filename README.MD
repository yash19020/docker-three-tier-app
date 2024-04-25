# docker-course-three-tier-web-app
This project is a 3-tier web application built in Python using Flask, consisting of an API layer, a frontend layer, and a MySQL database layer.


## Docker Course

This is a 3-tier web app built in Python (Flask).  There are three layers to this
application; namely:

1. `API` Layer
2. `Frontend` Layer
3. `Database - MySQL` Layer

API Layer (Backend):
Dockerfile: Builds an image for the API tier based on python:3.11-slim.
Dependencies: Installs system dependencies for Python packages using apt-get, copies requirements.txt, installs Python dependencies, and copies the rest of the application code.
Exposed Port: Exposes port 5001 for the API.
Command: Specifies the command to run the API application.

Frontend Layer:
Dockerfile: Builds an image for the frontend tier also based on python:3.11-slim.
Dependencies: Copies the entire application code, installs Python dependencies.
Exposed Port: Exposes port 5002 for the frontend.
Command: Specifies the command to run the app.

Database Layer (MySQL):
Dockerfile: Builds an image for the MySQL database tier based on mysql:latest.
Configuration: Sets environment variables for MySQL database configuration.
Initialization: Copies init.sql script to the container, which executes on container start.
To run these containers using Docker Compose:

We then use Docker Compose to run all of the containers at once.

## How to run these containers (using Docker Compose)

1. Make sure you have Docker Desktop running
2. Run the `docker compose build` command to build the containers
3. Run the `docker compose up -d` command to run the containers all at once
4. Open `localhost:5001/api/quotes` to see all the pre-populated sample quotes in a JSON format (assuming this is the first time you are running this).
5. On another browser, navigate to `localhost:5002` to see the frontend layer - you can add a few quotes as well as seeing other quotes coming from the database.




