# Healthcare Patient Service

Microservice responsible for managing patient registrations and profiles.
Part of the Healthcare Appointment System built for SEZG583 - Scalable Services assignment.

## Tech Stack
- Java 17
- Spring Boot 3.5.13
- Spring Data JPA
- MySQL 8.0
- Maven

## Port
Runs on **port 8081**

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/patients` | Register a new patient |
| GET | `/api/patients` | Get all patients |
| GET | `/api/patients/{id}` | Get patient by ID |
| GET | `/api/patients/{id}/exists` | Check if patient exists (used by Appointment Service) |
| PUT | `/api/patients/{id}` | Update patient details |
| DELETE | `/api/patients/{id}` | Delete patient |

## Sample Request

### Register Patient
```json
POST /api/patients
{
    "name": "Vinay Alapaty",
    "email": "vinay@example.com",
    "phone": "9876543210"
}
```

### Sample Response
```json
{
    "id": 1,
    "name": "Vinay Alapaty",
    "email": "vinay@example.com",
    "phone": "9876543210",
    "registeredAt": "2026-04-01T10:15:00"
}
```

## Running Locally

### Prerequisites
- Java 17
- Maven 3.9+
- MySQL 8.0 (via Docker)

### Start MySQL
```bash
docker run --name patient-db \
  -e MYSQL_ROOT_PASSWORD=root \
  -e MYSQL_DATABASE=patientdb \
  -p 3306:3306 -d mysql:8.0
```

### Run the service
```bash
mvn clean package -DskipTests
java -jar target/patient-service-0.0.1-SNAPSHOT.jar
```

## Running via Docker
```bash
docker build -t patient-service:1.0 .
docker run -p 8081:8081 patient-service:1.0
```

## Database Schema
Table: `patients`
| Column | Type | Constraint |
|--------|------|------------|
| id | BIGINT | PRIMARY KEY, AUTO INCREMENT |
| name | VARCHAR | NOT NULL |
| email | VARCHAR | UNIQUE, NOT NULL |
| phone | VARCHAR | |
| registered_at | DATETIME | |

## Project Structure
```
src/main/java/com/healthcare/patient/
├── Patient.java                  # Entity model
├── PatientRepository.java        # JPA repository
├── PatientService.java           # Business logic
├── PatientController.java        # REST endpoints
└── PatientServiceApplication.java
```

## Group Members
| Name | ID |
|------|----|
| Member 1 | ID |
| Member 2 | ID |
| Member 3 | ID |
| Member 4 | ID |
