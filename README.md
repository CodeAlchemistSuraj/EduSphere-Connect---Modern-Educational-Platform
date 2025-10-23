# 🎓 EduSphere Connect - Complete Educational Platform

![EduSphere Connect](https://img.shields.io/badge/Version-1.0.0-blue.svg)
![React](https://img.shields.io/badge/React-18.2.0-61dafb.svg)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.2.0-6DB33F.svg)
![Javascript](https://img.shields.io/badge/Javascript-5.0-3178c6.svg)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-15-336791.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)

## 📖 Table of Contents
- [Project Overview](#project-overview)
- [Features](#-features)
- [Architecture](#-architecture)
- [Tech Stack](#-tech-stack)
- [Quick Start](#-quick-start)
- [Installation](#-installation)
- [API Documentation](#-api-documentation)
- [Deployment](#-deployment)
- [Development](#-development)
- [Contributing](#-contributing)
- [Support](#-support)

## 🎯 Project Overview

**EduSphere Connect** is a comprehensive, modern educational platform designed to bridge the gap between traditional classroom learning and digital education. It provides a complete ecosystem for educational institutions with integrated live classes, course management, assessments, and collaborative tools.

### 🌟 Vision
To revolutionize digital education by creating an all-in-one platform that combines live instruction, collaborative learning, and comprehensive course management in an intuitive, accessible interface.

### 🎯 Mission
Empower educational institutions with a robust, scalable platform that enhances teaching effectiveness, improves student engagement, and provides actionable insights for continuous educational improvement.

## ✨ Features

### 🎓 Core Educational Features
- **🏫 Multi-role System** (Teachers, Students, Teaching Assistants, Admins)
- **📚 Comprehensive Course Management** with subjects and lessons
- **🎥 Integrated Live Classes** with Zoom API integration
- **📝 Advanced Assessment Engine** with multiple question types
- **💬 Global Collaborative Chat** with file sharing
- **📊 Real-time Analytics & Reporting** for performance tracking
- **📖 Digital Library** with study materials and resources
- **🗳️ Interactive Polling System** for live engagement
- **📅 Smart Scheduling** with calendar integration
- **🎯 Progress Tracking** for students and classes

### 🔧 Technical Features
- **Microservices Architecture** for scalability
- **Real-time Communication** with WebSocket
- **JWT Authentication** with role-based access
- **File Storage Integration** (AWS S3 compatible)
- **Email Notifications** system
- **Comprehensive API** with full documentation
- **Database Migrations** with version control
- **Docker Containerization** for easy deployment

### 🎨 User Experience
- **Responsive Design** - Works on all devices
- **Intuitive Interface** - Minimal learning curve
- **Accessibility First** - WCAG 2.1 AA compliant
- **Dark/Light Mode** support
- **Real-time Updates** and notifications

## 🏗️ Architecture

### System Architecture Overview
```
┌─────────────────┐    ┌──────────────────┐    ┌─────────────────┐
│   API Gateway   │───▶│  Service Registry │◀───│  Config Server  │
└─────────────────┘    └──────────────────┘    └─────────────────┘
         │
         ├─▶┌─────────────────┐    ┌─────────────────┐
         │  │  Auth Service   │◀──▶│   User Service  │
         │  └─────────────────┘    └─────────────────┘
         │
         ├─▶┌─────────────────┐    ┌─────────────────┐
         │  │ Course Service  │◀──▶│  Content Service│
         │  └─────────────────┘    └─────────────────┘
         │
         ├─▶┌─────────────────┐    ┌─────────────────┐
         │  │  Live Service   │◀──▶│  Zoom Service   │
         │  └─────────────────┘    └─────────────────┘
         │
         ├─▶┌─────────────────┐    ┌─────────────────┐
         │  │ Assessment Service│◀─▶│  Analytics Service│
         │  └─────────────────┘    └─────────────────┘
         │
         ├─▶┌─────────────────┐    ┌─────────────────┐
         │  │  Chat Service   │◀──▶│ Notification Service│
         │  └─────────────────┘    └─────────────────┘
```

### Database Architecture
- **PostgreSQL** - Primary relational database
- **Redis** - Caching and session storage
- **AWS S3** - File storage for materials and recordings
- **Elasticsearch** - Search and analytics (optional)

## 🛠️ Tech Stack

### Backend Services
- **Java 17** - Core programming language
- **Spring Boot 3.2** - Application framework
- **Spring Security** - Authentication and authorization
- **Spring Data JPA** - Database operations
- **Spring Cloud** - Microservices ecosystem
- **PostgreSQL** - Primary database
- **Redis** - Caching and sessions
- **JWT** - Token-based authentication
- **WebSocket** - Real-time communication
- **Zoom API** - Live video integration
- **AWS S3 SDK** - File storage
- **Maven** - Dependency management

### Frontend Application
- **React 18** - UI library
- **Javascript** - Type safety
- **Redux Toolkit** - State management
- **RTK Query** - Data fetching
- **Tailwind CSS** - Styling framework
- **React Router v6** - Routing
- **Vite** - Build tool
- **Socket.IO Client** - Real-time features
- **React Hook Form** - Form management
- **Zod** - Schema validation

### DevOps & Infrastructure
- **Docker** - Containerization
- **Docker Compose** - Local development
- **GitHub Actions** - CI/CD pipeline
- **PostgreSQL** - Database
- **Redis** - Cache
- **AWS** - Cloud deployment (optional)
- **Nginx** - Reverse proxy

## 🚀 Quick Start

### Prerequisites
- **Java 17** or higher
- **Node.js 18** or higher
- **PostgreSQL 14** or higher
- **Redis 6** or higher
- **Maven 3.6** or higher
- **Docker** and **Docker Compose** (optional)

### Quick Installation with Docker
```bash
# Clone the repository
git clone https://github.com/edusphere/connect.git
cd edusphere-connect

# Start all services with Docker Compose
docker-compose up -d

# Access the application
# Frontend: http://localhost:3000
# Backend API: http://localhost:8080
# API Docs: http://localhost:8080/swagger-ui.html
```

## 📦 Installation

### Manual Installation

#### 1. Backend Setup
```bash
# Clone the repository
git clone https://github.com/edusphere/connect.git
cd edusphere-connect/backend

# Configure database
# Create PostgreSQL database named 'edusphere'
createdb edusphere

# Configure application properties
cp src/main/resources/application.example.properties src/main/resources/application.properties

# Update application.properties with your configurations:
# - Database URL, username, password
# - Redis connection
# - JWT secret key
# - Zoom API credentials
# - AWS S3 credentials (if using cloud storage)

# Build the application
./mvnw clean install

# Run the application
./mvnw spring-boot:run
```

#### 2. Frontend Setup
```bash
# Navigate to frontend directory
cd ../frontend

# Install dependencies
pnpm install  # or npm install

# Configure environment
cp .env.example .env

# Update .env with your configurations:
VITE_API_BASE_URL=http://localhost:8080
VITE_SOCKET_URL=ws://localhost:8080
VITE_APP_NAME=EduSphere Connect

# Start development server
pnpm dev
```

#### 3. Database Initialization
The application will automatically create the necessary tables on first run. You can also run:

```bash
# Initialize with sample data (optional)
./mvnw spring-boot:run -Dspring.profiles.active=seed
```

### Configuration Files

#### Backend Configuration (`application.properties`)
```properties
# Database
spring.datasource.url=jdbc:postgresql://localhost:5432/edusphere
spring.datasource.username=postgres
spring.datasource.password=password

# JWT
jwt.secret=your-jwt-secret-key
jwt.expiration=86400000

# Redis
spring.redis.host=localhost
spring.redis.port=6379

# Zoom Integration
zoom.api.key=your-zoom-api-key
zoom.api.secret=your-zoom-api-secret

# File Storage
file.storage.type=local
file.upload.dir=./uploads

# Email
spring.mail.host=smtp.gmail.com
spring.mail.port=587
spring.mail.username=your-email@gmail.com
spring.mail.password=your-app-password
```

#### Frontend Configuration (`.env`)
```env
VITE_API_BASE_URL=http://localhost:8080
VITE_SOCKET_URL=ws://localhost:8080
VITE_APP_NAME=EduSphere Connect
VITE_UPLOAD_MAX_SIZE=10485760
VITE_DEFAULT_LANGUAGE=en
```

## 📚 API Documentation

### Base URL
```
http://localhost:8080/api
```

### Authentication Endpoints
| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/auth/login` | User authentication |
| `POST` | `/auth/register` | User registration |
| `POST` | `/auth/refresh` | Refresh JWT token |
| `POST` | `/auth/logout` | User logout |
| `POST` | `/auth/forgot-password` | Password reset request |
| `POST` | `/auth/reset-password` | Password reset |

### Course Management
| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/courses` | List all courses |
| `POST` | `/courses` | Create new course |
| `GET` | `/courses/{id}` | Get course details |
| `PUT` | `/courses/{id}` | Update course |
| `DELETE` | `/courses/{id}` | Delete course |
| `POST` | `/courses/{id}/enroll` | Enroll students |

### Live Sessions
| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/live/sessions` | Schedule live session |
| `GET` | `/live/sessions/{id}/join` | Get session join URL |
| `POST` | `/live/sessions/{id}/end` | End live session |
| `GET` | `/live/sessions/{id}/attendance` | Get attendance report |

### Assessments
| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/assessments` | Create assessment |
| `GET` | `/assessments/{id}` | Get assessment details |
| `POST` | `/assessments/{id}/attempt` | Start assessment attempt |
| `POST` | `/assessments/{id}/submit` | Submit assessment |

### Complete API Documentation
For complete API documentation, visit:
- **Swagger UI**: http://localhost:8080/swagger-ui.html
- **OpenAPI Spec**: http://localhost:8080/v3/api-docs

## 🐳 Deployment

### Docker Deployment
```bash
# Build and run all services
docker-compose up -d

# View logs
docker-compose logs -f

# Scale specific services
docker-compose up -d --scale course-service=3 --scale live-service=2

# Stop services
docker-compose down
```

### Production Deployment

#### 1. Backend Deployment
```bash
# Build JAR file
./mvnw clean package -DskipTests

# Run in production
java -jar target/edusphere-connect-1.0.0.jar --spring.profiles.active=prod
```

#### 2. Frontend Deployment
```bash
# Build for production
pnpm build

# The build output will be in 'dist' directory
# Serve with any web server (nginx, Apache, etc.)
```

#### 3. Environment Variables for Production
```bash
# Database
export DATABASE_URL=postgresql://user:pass@host:5432/edusphere
export REDIS_URL=redis://host:6379

# Security
export JWT_SECRET=your-production-jwt-secret
export ZOOM_API_KEY=your-zoom-key
export ZOOM_API_SECRET=your-zoom-secret

# Storage
export AWS_ACCESS_KEY=your-aws-key
export AWS_SECRET_KEY=your-aws-secret
export S3_BUCKET=edusphere-files
```

### Cloud Deployment (AWS Example)
```yaml
# docker-compose.prod.yml
version: '3.8'
services:
  app:
    image: edusphere/connect:latest
    environment:
      - SPRING_PROFILES_ACTIVE=prod
      - DATABASE_URL=${DATABASE_URL}
      - REDIS_URL=${REDIS_URL}
    ports:
      - "8080:8080"
    deploy:
      replicas: 3
      resources:
        limits:
          memory: 1G
        reservations:
          memory: 512M
```

## 💻 Development

### Project Structure
```
edusphere-connect/
├── backend/
│   ├── api-gateway/          # Spring Cloud Gateway
│   ├── auth-service/         # Authentication & authorization
│   ├── user-service/         # User management
│   ├── course-service/       # Course management
│   ├── live-service/         # Live sessions with Zoom
│   ├── assessment-service/   # Assessments & tests
│   ├── chat-service/         # Real-time chat
│   ├── notification-service/ # Email & push notifications
│   ├── file-service/         # File upload & management
│   └── analytics-service/    # Analytics & reporting
├── frontend/
│   ├── src/
│   │   ├── app/              # Redux store & RTK Query
│   │   ├── components/       # Reusable components
│   │   ├── features/         # Feature-based modules
│   │   ├── pages/            # Page components
│   │   ├── hooks/            # Custom React hooks
│   │   ├── utils/            # Utility functions
│   │   └── types/            # Javascript definitions
│   ├── public/               # Static assets
│   └── package.json
├── docker/
│   ├── Dockerfile.backend    # Backend Dockerfile
│   ├── Dockerfile.frontend   # Frontend Dockerfile
│   └── docker-compose.yml    # Docker composition
└── docs/                     # Documentation
```

### Running in Development Mode

#### Backend Development
```bash
cd backend

# Run with hot reload (requires IDE or maven plugin)
./mvnw spring-boot:run

# Or run specific service
cd auth-service
./mvnw spring-boot:run
```

#### Frontend Development
```bash
cd frontend

# Start development server
pnpm dev

# Run tests
pnpm test

# Build for production
pnpm build
```

### Testing
```bash
# Backend tests
./mvnw test

# Frontend tests
pnpm test

# E2E tests
pnpm test:e2e

# Coverage report
pnpm test:coverage
```

## 🤝 Contributing

We welcome contributions from the community! Please see our [Contributing Guide](CONTRIBUTING.md) for details.

### Development Setup
1. Fork the repository
2. Create a feature branch: `git checkout -b feature/amazing-feature`
3. Commit your changes: `git commit -m 'Add amazing feature'`
4. Push to the branch: `git push origin feature/amazing-feature`
5. Open a Pull Request

### Code Standards
- Follow Java and Spring Boot best practices
- Use Javascript for type safety in frontend
- Write comprehensive tests
- Update documentation for new features
- Follow commit message conventions

## 🐛 Troubleshooting

### Common Issues

**Database Connection Issues:**
```bash
# Check if PostgreSQL is running
sudo systemctl status postgresql

# Create database if it doesn't exist
createdb edusphere
```

**Zoom Integration Problems:**
- Verify Zoom JWT app credentials
- Check webhook configuration in Zoom developer portal
- Ensure proper permissions for meeting creation

**File Upload Issues:**
- Check file storage configuration
- Verify directory permissions for local storage
- Check AWS credentials for S3 storage

**Real-time Features Not Working:**
- Ensure Redis server is running
- Check WebSocket configuration
- Verify CORS settings

### Getting Help
- Check our [Troubleshooting Guide](docs/TROUBLESHOOTING.md)
- Open a [GitHub Issue](https://github.com/edusphere/connect/issues)
- Join our [Community Discord](https://discord.gg/edusphere)

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **Spring Boot** team for the excellent framework
- **React** team for the frontend library
- **Zoom** for video conferencing API
- **PostgreSQL** for reliable database
- **All contributors** who help improve EduSphere Connect

## 📞 Support

- **Documentation**: [docs.edusphere.com](https://docs.edusphere.com)
- **Community Forum**: [community.edusphere.com](https://community.edusphere.com)
- **Email Support**: [support@edusphere.com](mailto:support@edusphere.com)
- **Issue Tracker**: [GitHub Issues](https://github.com/edusphere/connect/issues)

---

<div align="center">

## 🎓 EduSphere Connect

**Transforming Education Through Technology**

[![Website](https://img.shields.io/badge/Website-edusphere.com-blue.svg)](https://edusphere.com)
[![Demo](https://img.shields.io/badge/Demo-Live%20Demo-green.svg)](https://demo.edusphere.com)
[![Documentation](https://img.shields.io/badge/Docs-Read%20Docs-orange.svg)](https://docs.edusphere.com)

*Built with ❤️ for the education community*

</div>
