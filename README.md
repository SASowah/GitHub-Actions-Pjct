# Bank Application - GitHub Actions Project

A secure banking web application built with Spring Boot and deployed on Kubernetes with CI/CD pipeline using GitHub Actions.

## 🏗️ Architecture

- **Backend**: Spring Boot 3.3.3 with Java 17
- **Database**: MySQL 8.0.35
- **Security**: Spring Security with authentication
- **Frontend**: Thymeleaf templates
- **Containerization**: Docker
- **Orchestration**: Kubernetes
- **CI/CD**: GitHub Actions
- **Code Quality**: SonarQube integration

## 🚀 Features

- User registration and authentication
- Account management
- Transaction processing
- Dashboard with account overview
- Secure password handling
- Persistent data storage

## 📁 Project Structure

```
├── src/
│   ├── main/
│   │   ├── java/come/example/bankapp/
│   │   │   ├── config/SecurityConfig.java
│   │   │   ├── controller/BankController.java
│   │   │   ├── model/Account.java, Transaction.java
│   │   │   ├── repository/AccountRepository.java, TransactionRepository.java
│   │   │   ├── service/AccountService.java
│   │   │   └── BankappApplication.java
│   │   └── resources/
│   │       ├── templates/ (HTML pages)
│   │       └── application.properties
│   └── test/
├── Dockerfile
├── ds.yml (Kubernetes deployment)
├── pom.xml
└── sonar-project.properties
```

## 🛠️ Prerequisites

- Java 17
- Maven 3.6+
- Docker
- Kubernetes cluster
- MySQL 8.0+

## 🔧 Local Development

### 1. Clone the repository
```bash
git clone <repository-url>
cd GitHub-Actions-Pjct
```

### 2. Build the application
```bash
mvn clean compile
```

### 3. Run tests
```bash
mvn test
```

### 4. Package the application
```bash
mvn package
```

### 5. Run locally
```bash
java -jar target/bankapp-0.0.1-SNAPSHOT.jar
```

## 🐳 Docker Deployment

### Build Docker image
```bash
docker build -t bankapp:latest .
```

### Run with Docker
```bash
docker run -p 8080:8080 bankapp:latest
```

## ☸️ Kubernetes Deployment

The application includes production-ready Kubernetes manifests with:

- **Security**: Kubernetes Secrets for credential management
- **Storage**: Persistent volumes for MySQL data
- **Health Checks**: Liveness and readiness probes
- **Resource Management**: CPU and memory limits
- **High Availability**: Rolling updates and failure handling

### Deploy to Kubernetes
```bash
kubectl apply -f ds.yml
```

### Access the application
```bash
kubectl get services bankapp-service
```

## 🔍 Kubernetes Components

- **MySQL Secret**: Secure credential storage
- **MySQL PVC**: 1Gi persistent storage
- **MySQL Deployment**: Database with health checks and resource limits
- **MySQL Service**: Internal database connectivity
- **Bank App Deployment**: Application with init containers and probes
- **Bank App Service**: LoadBalancer for external access

## 📊 Code Quality

### SonarQube Integration
- Project Key: `GC-Bank`
- Jacoco coverage reports
- Automated code quality checks

### Run SonarQube analysis
```bash
mvn sonar:sonar
```

## 🔐 Security Features

- Spring Security authentication
- Password encryption
- Kubernetes Secrets for sensitive data
- Security headers and CSRF protection
- Input validation and sanitization

## 🌐 Application Endpoints

- `/` - Home page
- `/login` - User login
- `/register` - User registration
- `/dashboard` - Account dashboard
- `/transactions` - Transaction history
- `/actuator/health` - Health check endpoint

## 📈 Monitoring

- Health check endpoints for Kubernetes probes
- Application metrics via Spring Boot Actuator
- Resource monitoring with Kubernetes metrics

## 🚀 CI/CD Pipeline

The project is configured for GitHub Actions with:
- Automated testing
- Code quality analysis
- Docker image building
- Kubernetes deployment

🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Run tests and quality checks
5. Submit a pull request

 📝 License

This project is licensed under the MIT License.

