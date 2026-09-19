# Real-Time Notification System

A real-time notification system built using **Java, Spring Boot, WebSocket, STOMP, REST APIs, and MongoDB**. The application allows clients to connect through WebSocket and receive notifications instantly without refreshing the page.

## Features

- Real-time notifications using WebSocket
- STOMP-based messaging
- REST API for publishing notification events
- Channel-based subscriber management
- MongoDB integration for data persistence
- Layered architecture using Controller, Service, DTO, and Repository
- Simple web interface for testing real-time notifications
- REST API testing using Postman or IntelliJ HTTP Client

## Tech Stack

- **Language:** Java
- **Framework:** Spring Boot
- **Communication:** REST API, WebSocket, STOMP
- **Database:** MongoDB
- **Build Tool:** Maven
- **Testing:** Postman / IntelliJ HTTP Client
- **IDE:** IntelliJ IDEA

## Project Flow

```text
Client
   |
   | POST /api/notifications/publish
   v
NotificationController
   |
   v
SubscriptionService
   |
   | Find subscribers
   v
NotificationDto
   |
   v
NotificationService
   |
   | WebSocket + STOMP
   v
Connected Subscribers
   |
   v
Real-Time Notification
```

## API Example

### Publish Notification

**POST**

```text
/api/notifications/publish
```

Request body:

```json
{
  "channelId": "channel1",
  "videoTitle": "My First Video"
}
```

Example response:

```text
Notification sent to 2 subscribers.
```

## How It Works

1. A client establishes a WebSocket connection with the Spring Boot application.
2. The client subscribes to the required notification destination.
3. A notification event is sent through the REST API.
4. The application identifies subscribers associated with the channel.
5. A notification DTO is created.
6. The notification is broadcast through WebSocket and STOMP.
7. Connected subscribers receive the notification instantly.

## Running the Project

### Prerequisites

- Java 17 or later
- Maven
- MongoDB
- IntelliJ IDEA or another Java IDE

### Steps

1. Clone the repository.
2. Configure MongoDB according to the application's configuration.
3. Open the project in IntelliJ IDEA.
4. Build the project using Maven.
5. Run `RealTimeNotificationsApplication`.
6. Open the application in the browser.
7. Establish a WebSocket connection.
8. Use Postman or `test.http` to publish a notification.

## Future Improvements

- JWT authentication and authorization
- React-based frontend
- Unit and integration testing
- Docker containerization
- Cloud deployment
- Redis/Kafka for scalable message delivery
- Offline notification persistence

## Author

Developed as a Java Spring Boot project to demonstrate REST APIs, real-time WebSocket communication, messaging, and database integration.
