In this DevOps task, you need to build and deploy a full-stack CRUD application using the MEAN stack (MongoDB, Express, Angular 15, and Node.js). The backend will be developed with Node.js and Express to provide REST APIs, connecting to a MongoDB database. The frontend will be an Angular application utilizing HTTPClient for communication.  

The application will manage a collection of tutorials, where each tutorial includes an ID, title, description, and published status. Users will be able to create, retrieve, update, and delete tutorials. Additionally, a search box will allow users to find tutorials by title.

## Project setup

### Node.js Server

cd backend

npm install

You can update the MongoDB credentials by modifying the `db.config.js` file located in `app/config/`.

Run `node server.js`

### Angular Client

cd frontend

npm install

Run `ng serve --port 8081`

You can modify the `src/app/services/tutorial.service.ts` file to adjust how the frontend interacts with the backend.

Navigate to `http://localhost:8081/`


# 🚀 MEAN Stack Application Deployment with Docker & CI/CD

This repository contains a **MEAN Stack application** (MongoDB, Express.js, Angular, Node.js) deployed using **Docker, Docker Compose, Nginx reverse proxy**, and **GitHub Actions CI/CD pipeline**.

The project demonstrates **end-to-end production-style deployment** with automated builds and server deployment.

---

## 📌 Tech Stack

- **Frontend**: Angular 15  
- **Backend**: Node.js + Express.js  
- **Database**: MongoDB  
- **Containerization**: Docker, Docker Compose  
- **Reverse Proxy**: Nginx  
- **CI/CD**: GitHub Actions  
- **Server**: Ubuntu (AWS EC2)

---

## 📂 Project Structure

```
discover_dollar/
│
├── backend/
│   ├── Dockerfile
│   ├── server.js
│   └── package.json
│
├── frontend/
│   ├── Dockerfile
│   ├── angular.json
│   └── src/
│
├── nginx/
│   └── default.conf
│
├── docker-compose.yml
├── .github/workflows/deploy.yml
└── README.md
```

##  Docker Configuration

  ## Backend Dockerfile

  Builds Node.js + Express backend
  Exposes API on port 8080

  ## Frontend Dockerfile

  Builds Angular production files
  Serves them using Nginx
  Exposes frontend on port 80

  ## Docker Compose
  Runs the following services:

  MongoDB
  Backend
  Frontend
  Nginx (reverse proxy)

## Nginx Reverse Proxy

  Nginx routes incoming traffic as follows:

  / → Angular Frontend
  /api → Node.js Backend
  Only port 80 is exposed publicly.


## CI/CD Pipeline (GitHub Actions)

  The CI/CD pipeline is triggered on every push to the main branch.

  ## Pipeline Flow

  1. Checkout source code

  2. Login to Docker Hub

  3. Build backend Docker image

  4. Build frontend Docker image

  5. Push images to Docker Hub

  6. SSH into server

  7. Pull latest images

  8. Restart containers using Docker Compose

  This enables automatic deployment without manual intervention.

## GitHub Secrets Configuration

  The following secrets are configured in GitHub:

  DOCKER_USERNAME
  DOCKER_PASSWORD
  SERVER_IP
  SSH_KEY

  These secrets securely store sensitive credentials used by the CI/CD pipeline.

## Deployment Steps (Server Setup)

  ## 1. Clone the Repository

    git clone <your-github-repo-url>
    cd discover_dollar

  ## 2. Install Docker (One-Time)

    sudo apt update
    sudo apt install docker.io -y

  ## 3. Start Application

    docker compose up -d

  ## 4. Access Application

    http://<SERVER_PUBLIC_IP>  
  
    MINE PUBLIC IP URL IS: http://13.51.206.54/

## Verification Commands

  ## Check Running Containers

    docker ps 

  ## Check Frontend Files

    docker exec -it frontend ls /usr/share/nginx/html

  ## View Logs

    docker logs nginx
    docker logs backend

## Screenshots Included

  1. The repository includes screenshots showing:

  2. GitHub Actions CI/CD workflow configuration

  3. Successful CI/CD pipeline execution

  4. Docker image build & push on Docker Hub

  5. Running containers on the server

  6. Application UI running in browser


## Key Learnings

  1. Containerized a full-stack MEAN application

  2. Implemented automated CI/CD with GitHub Actions

  3. Used Docker Compose for service orchestration

  4. Configured Nginx as a reverse proxy

  5. Deployed application on cloud server using best practices 


## Conclusion

  This project demonstrates a complete real-world deployment workflow, from development to production, using modern DevOps tools.

## GitHub Repository

  https://github.com/akashh1011/discover_dollar.git

