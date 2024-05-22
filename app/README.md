# Local Load Balancer Implementation using Nginx

## Project Overview

This project demonstrates the implementation of a local load balancer using Nginx. It features a setup that includes dummy backend servers, which are used to route requests based on a weighted round-robin algorithm. The aim is to provide a practical example of how Nginx can be configured as a load balancer to distribute network or application traffic across multiple servers.

## Getting Started

### Prerequisites

- Docker
- Docker Compose
- Conda (optional, for creating virtual environments)

### Installation

1. **Clone the Repository**
    ```bash
    git clone ...
    cd load-balancer
    ```

2. **Create a Virtual Environment (Optional)**
    ```bash
    conda create -n lb
    conda activate lb
    ```

3. **Install Dependencies**
    ```bash
    pip install --upgrade pip
    pip install fastapi uvicorn requests
    ```

4. **Freeze Dependencies**
    ```bash
    pip freeze > requirements.txt
    ```

5. **Set Up FastAPI Application**
- Create a new FastAPI app by editing `main.py`.

6. **Run Locally**
- Start the FastAPI app locally for development:
  ```bash
  uvicorn main:app --host 0.0.0.0 --port 8000 --reload
  ```

7. **Containerize the Application**
- Prepare Docker-related files:
  - `Dockerfile`: Instructions for building the Docker image.
  - `.dockerignore`: Specifies files to ignore during Docker build.
  - `docker-compose.yaml`: Configures services, networks, and volumes.

8. **Run Using Docker Compose**
    ```bash
    docker compose up --build
    ```

9. **Configure Nginx**
- Edit `nginx/nginx.conf` to set up Nginx as a load balancer.

10. **Testing**
 - Create and run tests using `test/test.py` to validate the load distribution.

## Usage

To test the distribution of requests across your backend servers, run the test script:

```bash
python test/test.py
```

## Contributions

Contributions to this project are welcome! Feel free to fork the repository, make improvements, and submit pull requests.
