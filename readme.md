# Redis University Courses Repository

This repository was created to store my notes and resources related to Redis University courses.

## Getting Started

Follow these instructions to set up and explore the course notes.

### Prerequisites

Make sure you have the following items installed:

- Docker: [Installation Instructions](https://docs.docker.com/get-docker/)
- Docker Compose: [Installation Instructions](https://docs.docker.com/compose/install/)

### Starting the Environment

1. Clone this repository:
    ```bash
    git clone https://github.com/your-user/redis-university-courses.git
    cd redis-university-courses
    ```

2. Start the Docker containers for Redis:
    ```bash
    docker-compose up -d
    ```

### Accessing the Redis Client

1. Access the Redis client using the following command:
    ```bash
    docker-compose exec redis redis-cli
    ```
