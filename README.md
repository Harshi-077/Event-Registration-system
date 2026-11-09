# Event Registration System
Full-stack college hackathon project: Java 17 + Spring Boot + HTML/CSS/JavaScript + SQL (H2).

## Run
1. Install Java JDK 17+ and Maven 3.8+.
2. Extract this ZIP.
3. Open the `event-registration-system` folder in VS Code.
4. Open Terminal and run: `mvn spring-boot:run`
5. Wait for the message `Started EventRegistrationApplication`.
6. Open http://localhost:8080

No MySQL Server/Workbench installation is needed for this ready-to-run version. H2 is a relational SQL database stored locally in `./data/eventdb`, so data remains after restart.

## Features
Events CRUD, student CRUD, registration lists, event filtering, search, participant counts, capacity enforcement, duplicate prevention, over-capacity status, dashboard.
Delete archives an event/student so historical registrations remain.
The registration service locks the event row while checking capacity to protect the last seat from concurrent requests.

## SQL
Schema is in `database.sql` and `src/main/resources/schema.sql`; Spring Boot initializes it automatically.
H2 console: http://localhost:8080/h2-console
JDBC URL: `jdbc:h2:file:./data/eventdb`
User: `sa` | Password: blank

## API
GET/POST `/api/events`; PUT/DELETE `/api/events/{id}`
GET/POST `/api/students`; PUT/DELETE `/api/students/{id}`
GET `/api/registrations`; GET `/api/registrations?eventId=1`
POST `/api/registrations`; GET `/api/dashboard`

This starter has no login/authorization. Use demo data, not real personal student information, until authentication and access controls are added.
