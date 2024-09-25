---

# Three-Tier Application with Docker Swarm

This project demonstrates a simple three-tier architecture using Docker Swarm. The architecture consists of a frontend, backend, and database service. Each component is containerized using Docker, and Docker Swarm is used to orchestrate the services.

## Project Structure

```
three-tier-app/
│
├── backend/
│   ├── Dockerfile       # Dockerfile for building the backend service
│   ├── app.js           # Node.js application code for the backend
│   ├── package.json     # NPM configuration file for the backend
│   
├── db/
│   ├── init.sql         # SQL script to initialize the database
│
├── frontend/
│   ├── Dockerfile       # Dockerfile for building the frontend service
│   ├── register.html    # HTML page for user registration
│   └── users.html       # HTML page for viewing, updating, and deleting user details
│
├── docker-compose.yml   # Docker Compose file for local development
```

## Prerequisites

- Docker and Docker Compose installed on your machine
- Docker Swarm initialized

## Setup Instructions

Follow these steps to set up and run the application:

### 1. Clone the Repository

```bash
git clone https://github.com/surajmundhe30/three-tier-app.git
cd three-tier-app
```

### 2. Initialize Docker Swarm

If you haven't initialized Docker Swarm, you can do so with:

```bash
docker swarm init
```

### 3. Build and Start Services

Use Docker Compose to build and start the services locally:

```bash
docker-compose up --build
```

### 4. Access the Application

- **Frontend**: Open your browser and navigate to `http://localhost:8080/register.html` for user registration and `http://localhost:8080/users.html` for viewing and managing user details.
- **Backend**: The backend service will be running on port `3000`.
- **Database**: The MySQL database service will be accessible internally within the Docker network.

### 5. Database Initialization

The `db/init.sql` script is automatically executed to set up the database when the MySQL container is first started. Ensure your database service in the `docker-compose.yml` or `stack.yml` uses this script for initialization.

## Project Components

### Backend

- **Language**: Node.js
- **Framework**: Express
- **Database**: MySQL
- **Dockerfile**: Defines the Docker image for the backend service. It sets up the environment, installs dependencies, and runs the `app.js` file.

### Frontend

- **HTML/CSS/JavaScript**: Simple static pages for user registration and management.
- **Dockerfile**: Uses Nginx to serve static files.

### Database

- **MySQL**: Used as the relational database to store user data.
- **Initialization Script**: `init.sql` sets up the initial schema and tables required by the application.

## Customization

You can customize this project by:

- Modifying the frontend pages in the `frontend/` directory.
- Adding more routes or functionality to the `backend/app.js`.
- Changing the database schema or initial data in the `db/init.sql`.

## Troubleshooting

- **404 Errors**: Ensure the frontend files are correctly copied to the Nginx container's root directory (`/usr/share/nginx/html`).
- **Database Connection Issues**: Verify the backend service environment variables and check network configurations.
- **Logs**: Use `docker logs <container_id>` to view logs for debugging.

## License

This project is open-source and available under the [Apache2 License](LICENSE).

## Acknowledgements

- Docker and Docker Swarm documentation
- Node.js and Express documentation
- MySQL documentation
