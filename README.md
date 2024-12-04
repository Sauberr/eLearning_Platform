# eLearning Platform

This project delivers a mini eLearning platform like Udemy, built with Django 4.2 and Django Channels, empowering users to create, enroll in, and manage online courses.  Leveraging technologies like Docker for easy deployment and scalability, PostgreSQL for robust data management, Redis for enhanced performance through caching, and Django Channels for real-time interactivity, including a chat feature for course participants to engage in discussions, this platform provides a foundation for building interactive and engaging learning experiences.  Nginx is also utilized as a reverse proxy to handle static files efficiently and improve overall performance.

#### Stack:

- [Python](https://www.python.org/downloads/)
- [PostgreSQL](https://www.postgresql.org/)
- [Redis](https://redis.io/)
- [Docker](https://www.docker.com/)

## Local Developing

All actions should be executed from the source directory of the project and only after installing all requirements.

1. Firstly, create and activate a new virtual environment:
   ```bash
   python3.11 -m venv ../venv
   source ../venv/bin/activate
   ```
   
2. Install packages:
   ```bash
   pip install --upgrade pip
   pip install -r requirements.txt
   ```
## Run application
The uvicorn web server is used to run Django. The command to run looks like this:
```
py manage.py runserver
```
It must be run on the command line, always being in the root directory of the project.


###Dockerfile
To run a web server (Django) inside a container, you need to uncomment the code inside the Dockerfile and have an already running PostgreSQL instance on your machine.
Code to run Dockerfile:
```
docker build .
```

The command is also run from the root directory where the Dockerfile resides.

### Docker compose
To start all services (DB, Redis, web server (Django), Celery, Flower, Grafana, Prometheus), you need to use the docker-compose.yml file and the commands
```
docker compose build
docker compose up
```
Moreover, the `build` command needs to be run only if you changed something inside the Dockerfile, that is, you changed the logic for compiling the image.
