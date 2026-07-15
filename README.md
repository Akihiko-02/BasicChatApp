# Real-Time Chat Application

A simple real-time chat application built with Spring Boot WebSocket, STOMP, and SockJS.

This project demonstrates how to implement real-time communication between clients using WebSocket technology.

## Features

- Real-time messaging
- Multiple users can chat simultaneously
- WebSocket communication
- STOMP messaging protocol
- SockJS support
- Message broadcasting

## Technologies Used

### Backend
- Java
- Spring Boot
- Spring WebSocket
- Spring Messaging

### Frontend
- HTML
- CSS
- JavaScript
- Bootstrap
- SockJS Client
- STOMP.js

## How It Works

The application uses WebSocket to establish a persistent connection between the client and server.

Message flow:

```
Client
   |
   | Send Message
   |
STOMP + SockJS
   |
   |
Spring Boot WebSocket Server
   |
   |
Message Broker
   |
   |
Subscribed Clients
```

When a user sends a message:

1. Client sends a message to `/app/sendMessage`
2. Spring WebSocket Controller receives the message
3. The server broadcasts the message to `/topic/messages`
4. All connected clients receive the message instantly


## Project Structure

```
src/main/java
|
├── config
|    └── WebSocketConfig.java
|
├── controller
|    └── ChatController.java
|
└── model
     └── ChatMessage.java


src/main/resources

├── templates
|    └── chat.html
|
└── static
```

## WebSocket Configuration

WebSocket Endpoint:

```
/chat
```

Client connection:

```
ws://localhost:8080/chat
```

Send destination:

```
/app/sendMessage
```

Subscribe destination:

```
/topic/messages
```

## Running the Application

Clone the project:

```bash
git clone <repository-url>
```

Go to the project folder:

```bash
cd chat-application
```

Run the Spring Boot application:

```bash
./mvnw spring-boot:run
```

Open your browser:

```
http://localhost:8080/chat
```

Open multiple browser tabs to test real-time messaging.

## Learning Purpose

This project was created to understand:

- WebSocket communication
- STOMP protocol
- SockJS integration
- Spring WebSocket configuration
- Real-time message handling

## Future Improvements

- Add user authentication
- Store chat messages in database
- Implement private messaging
- Add online/offline status
- Add message history