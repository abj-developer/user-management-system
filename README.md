# user-management-system

University Management System – Microservices

A production-style backend application built using Spring Boot,
Spring Cloud, MySQL, Docker and GitHub Actions.

Architecture
────────────
            

Microservices
─────────────
1. API Gateway
   → Routes requests to backend services
   https://github.com/abj-developer/api-gateway
   
2. User Service
   → User registration,  and management
   https://github.com/abj-developer/user-service

3. Department Service
   → Department CRUD operations
   https://github.com/abj-developer/department-service

4. Email Service
   https://github.com/abj-developer/email-service   

5. Service Discovery
   → Microservice registration and discovery
   https://github.com/abj-developer/service-registry

6. Auth Service
   https://github.com/abj-developer/auth-service


Tech Stack
──────────
Java 17 | Spring Boot | Spring Cloud | MySQL
Docker | GitHub Actions | REST APIs
