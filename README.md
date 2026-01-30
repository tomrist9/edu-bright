# EduBright Microservices Project

##  Overview
**EduBright** is a microservices-based education platform that provides course management, enrollment services, and a gateway for secure API communication. This project follows the **Spring Boot & Spring Cloud** ecosystem, utilizing **Eureka Service Discovery**, **Spring Cloud Gateway**, **Config Server**, and database persistence with **JPA & MySQL**.

## 🏗️ Architecture
EduBright is built using **microservices architecture** and includes the following services:

### **🔹 Microservices Overview**
| Service Name         | Description                                      | Port |
|---------------------|------------------------------------------------|------|
| **API Gateway**     | Handles incoming requests & routes them       | 8080 |
| **User Service**    | Manages user authentication & profile          | 8081 |
| **Course Service**  | Handles course creation & retrieval           | 8082 |
| **Enrollment Service** | Manages course enrollments & student data   | 8083 |
| **Config Server**   | Centralized configuration management          | 8888 |
| **Eureka Server**   | Service registry & discovery                  | 8761 |

## 🚀 Technologies Used
### **Backend Technologies**
- **Java 17**
- **Spring Boot 3.1** (Microservices Framework)
- **Spring Cloud** (Eureka, Gateway, Config Server)
- **Spring Data JPA** (Database ORM)
- **Spring Security** (Authentication & Authorization)
- **Hibernate** (JPA Implementation)
- **Lombok** (Reduces boilerplate code)

### **Database & Messaging**
- **MySQL** (Persistent storage for services)
- **H2 Database** (For in-memory testing)
- **Kafka/RabbitMQ** (Optional for messaging & event-driven communication)

### **DevOps & Tools**
- **Docker** (Containerization)
- **Kubernetes** (Optional for deployment)
- **Maven** (Build automation)
- **Postman** (API testing)
- **IntelliJ IDEA** (Development IDE)

## 📂 Project Structure
```
edu-bright/
│── api-gateway/             # Spring Cloud Gateway Service
│── config-server/           # Centralized Config Service
│── eureka-server/           # Service Registry
│── user-service/            # User Management Service
│── course-service/          # Course Management Service
│── enrollment-service/      # Enrollment Management Service
│── pom.xml                  # Parent Project Configuration
│── README.md                # Documentation
```

## ⚙️ Prerequisites
- **JDK 17** installed
- **Maven 3.8+** installed
- **MySQL Server running** (if using MySQL)
- **Eureka Server running**

## 📦 How to Run
### **1️⃣ Clone the Repository**
```sh
git clone https://github.com/tomrist9/edu-bright.git
cd edu-bright
```

### **2️⃣ Start Eureka Server**
```sh
cd eureka-server
mvn spring-boot:run
```

### **3️⃣ Start Config Server**
```sh
cd config-server
mvn spring-boot:run
```

### **4️⃣ Start API Gateway**
```sh
cd api-gateway
mvn spring-boot:run
```

### **5️⃣ Start Microservices**
Run each service in a separate terminal:
```sh
cd user-service
mvn spring-boot:run
```
```sh
cd course-service
mvn spring-boot:run
```
```sh
cd enrollment-service
mvn spring-boot:run
```

### **6️⃣ Access the System**
- **Eureka Dashboard** → `http://localhost:8761`
- **API Gateway** → `http://localhost:8080`
- **User Service** → `http://localhost:8081/users`
- **Course Service** → `http://localhost:8082/courses`
- **Enrollment Service** → `http://localhost:8083/enrollments`

## 🛠️ Configuration Management
All service configurations are stored in the **Config Server**.
- Configuration files should be placed in the `/config` folder.
- Example: `config/user-service.properties` for **User Service**.

## 📝 API Endpoints
### **User Service** (`http://localhost:8081`)
- `GET /users` → Retrieve all users
- `POST /users` → Create a new user

### **Course Service** (`http://localhost:8082`)
- `GET /courses` → Retrieve all courses
- `POST /courses` → Create a new course

### **Enrollment Service** (`http://localhost:8083`)
- `POST /enroll` → Enroll a student in a course
- `GET /enrollments` → Retrieve all enrollments

## 🧪 Running Tests
```sh
mvn test
```

## 🚀 Deployment (Docker)
### **Build Docker Images**
```sh
docker-compose up --build
```

## 💡 Future Enhancements
- Implement **OAuth2 / JWT Authentication**
- Add **Circuit Breaker (Resilience4J)** for fault tolerance
- Integrate **Kafka/RabbitMQ** for messaging
- Deploy using **Kubernetes (K8s)**

## 🎯 Contributors
- **Tomris (Tomrist9)** - Initial Development
- Open for Contributions!

## 📜 License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

