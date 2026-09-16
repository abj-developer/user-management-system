
# user-management-system

@@ University Management System – Microservices APIs
**Description**

A production-style backend application designed to showcase the following features.
1. Designed 1 microservice **serve-registry** as Discovery-server registered as Eureka server. All other services will register with it.
2. Designed 3 Microservices (**user-service**, **department-service** ) registered as Eureka Client and **email-service**.
3. Designed 1  microservice **Auth-service** having the JWT authentication part for token generation enabling API Security. Auth-Service is also registered as Eureka Client.
4. Designed 1 microservice **api-aateway**. All Other Services will be behind the api-gateway making it as single entry point. It would be used for cross-cutting concerns. Currently **JWT** authentication and verification is happening here through auth-service. A **Central Swagger** is enabled here to list down all the Apis.
5. user-service is sending User Registration Notification to a Kafka Topic and email-service is sending this notification to the email of the user through Brevo SMTP Server.
6. All the Microservices are containerized using Docker and Docker Compose.
7. CI/CD Pipeline is configured using GitHub Actions. Docker images are getting build and stored in GitHub Container Registry (GHCR). 
8. Deployed all the Microservices on the Oracle Cloud VM. All the images stored in GHCR are getting deployed in a Docker Network inside the VM.
9. CI/CD is working, as soon as we do a git push, cycle will trigger , a fresh build will be generated and deployement will happen on the VM.
10. Configured a reverse proxy NGINX Server for doing certain tasks listed below->
    a. TLS Termination (SSL/TLS) and exposing the public port 80/443 and hiding the private ports behind.
    b. Enabling HTTPS through Lets' Encrypt Certificate Mechanism.
    c. Routing traffic to api-gateway coming to provided Domain-name.
11. Services are exposed on a public URL->
    Swagger Endpoints-> [https://abjms.duckdns.org/swagger-ui/index.html]
    

@@ <ins>Architecture Diagram</ins> @@

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/9a5a1846-f0fe-4ff6-9d82-4909b31cda61" />


@@ <ins>Microservices Diagram-></ins> @@

1. API Gateway
   → Routes requests to backend services
   https://github.com/abj-developer/api-gateway
   
2. User Service
   → User registration and management
   https://github.com/abj-developer/user-service

3. Department Service
   → Department CRUD operations
   https://github.com/abj-developer/department-service

4. Email Service
   -> sends email notifications to the users
   https://github.com/abj-developer/email-service   

5. Service Discovery
   → Microservice registration and discovery
   https://github.com/abj-developer/service-registry

6. Auth Service
   Handling API Security.
   https://github.com/abj-developer/auth-service


@@ Tech Stack -> @@
Java 17 | Spring Boot | Spring Cloud | MySQL | Docker | GitHub Actions | REST APIs | Eureka | API Gateway| Rest API | Swagger | NGINX
