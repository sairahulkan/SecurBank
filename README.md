## Technologies Used

- **Go**: Backend programming language.
- **Gin**: Web framework.
- **PostgreSQL**: Relational database.
- **JWT/PASETO**: Secure authentication tokens.
- **Docker**: Containerization.
- **Kubernetes**: Container orchestration.
- **AWS**: Cloud services.
- **Redis**: In-memory data structure store.
- **GitHub Actions**: CI/CD.

## Getting Started

### Prerequisites

- Go 1.16+
- Docker
- Kubernetes (kubectl and a cluster)
- AWS CLI
- PostgreSQL
- Redis

### Installation

1. Clone the repository:

    ```bash
    git clone https://github.com/your-username/securbank.git
    cd securbank
    ```

2. Set up the environment variables:

    Create a `.env` file and add the necessary configuration values.

    ```plaintext
    DB_SOURCE="postgresql://user:password@localhost:5432/securbank?sslmode=disable"
    REDIS_ADDRESS="localhost:6379"
    JWT_SECRET="your_jwt_secret"
    PASETO_SECRET="your_paseto_secret"
    AWS_REGION="your_aws_region"
    ```

3. Run the application:

    ```bash
    go run src/main.go
    ```

## Deployment

### Docker

1. Build the Docker image:

    ```bash
    docker build -t securbank .
    ```

2. Run the Docker container:

    ```bash
    docker run -p 8080:8080 --env-file .env securbank
    ```

### Kubernetes

1. Apply the Kubernetes configurations:

    ```bash
    kubectl apply -f k8s/deployment.yaml
    kubectl apply -f k8s/service.yaml
    ```

2. Check the status of your pods:

    ```bash
    kubectl get pods
    ```

## CI/CD with GitHub Actions

This project uses GitHub Actions for continuous integration and continuous deployment. The configuration file is located at `.github/workflows/ci.yml`.

### Setting Up GitHub Actions

1. Create a `.github/workflows/ci.yml` file with your CI/CD pipeline configuration.
2. Ensure your repository secrets are set for AWS credentials, Docker Hub credentials, and any other required environment variables.
