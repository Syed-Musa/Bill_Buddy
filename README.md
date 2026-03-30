# Bill Buddy

Bill Buddy is a full-stack expense sharing app with:
- React + Vite frontend
- Spring Boot + MySQL backend

## Project Structure

- bill-buddy-react-frontend: UI application (runs on http://localhost:5173)
- bill-buddy-spring-boot-backend: REST API (runs on http://localhost:8182)

## Prerequisites

Install these before running the project:
- Node.js 18+ and npm
- Java 17 (required by backend)
- Maven (optional, wrapper is included)
- MySQL 8+

Important:
- Backend uses Java 17 in pom.xml. If you have multiple JDKs installed, make sure JAVA_HOME points to JDK 17.

## 1) Database Setup (MySQL)

Create the database used by the backend:

CREATE DATABASE `pay-with-roommates`;

Default backend DB config is in bill-buddy-spring-boot-backend/src/main/resources/application.yml:
- URL: jdbc:mysql://localhost:3306/pay-with-roommates
- Username: root
- Password: root

If your MySQL credentials are different, update application.yml before starting the backend.

## 2) Run Backend (Spring Boot)

From workspace root:

cd bill-buddy-spring-boot-backend
./mvnw spring-boot:run

On Windows CMD/PowerShell, you can also use:

mvnw.cmd spring-boot:run

Backend will start at:
- http://localhost:8182

## 3) Run Frontend (React + Vite)

Open a new terminal from workspace root:

cd bill-buddy-react-frontend
npm install
npm run dev

Frontend will start at:
- http://localhost:5173

## 4) Access the App

- Open http://localhost:5173 in your browser.
- Frontend is already configured to call backend endpoints at http://localhost:8182.
- CORS is configured in backend for http://localhost:5173.

## Useful Commands

Frontend:
- npm run dev
- npm run build
- npm run lint

Backend:
- ./mvnw spring-boot:run
- ./mvnw test

## Troubleshooting

1. Backend does not start due to Java version
- Run java -version and confirm Java 17 is active.
- Update JAVA_HOME/PATH to JDK 17 if needed.

2. Database connection error
- Confirm MySQL is running on port 3306.
- Confirm database pay-with-roommates exists.
- Confirm username/password in application.yml are correct.

3. CORS errors in browser
- Confirm frontend runs on http://localhost:5173.
- Confirm backend runs on http://localhost:8182.

## API Docs

The backend includes Springdoc OpenAPI dependency. Once the backend is running, try:
- http://localhost:8182/swagger-ui/index.html
