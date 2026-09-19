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

---

# Real-Time Chat Application

**Spring Boot WebSocket、STOMP、SockJS** を使用して開発したシンプルなリアルタイムチャットアプリケーションです。

WebSocket技術を使用して、クライアント間でリアルタイムに通信する方法を実装しています。

## 機能

* リアルタイムメッセージング
* 複数ユーザーによる同時チャット
* WebSocket通信
* STOMPメッセージングプロトコル
* SockJS対応
* メッセージのブロードキャスト

## 使用技術

### Backend

* Java
* Spring Boot
* Spring WebSocket
* Spring Messaging

### Frontend

* HTML
* CSS
* JavaScript
* Bootstrap
* SockJS Client
* STOMP.js

## 仕組み

WebSocketを使用して、クライアントとサーバー間に永続的な接続を確立します。

メッセージの流れ：

```text id="m9s4p2"
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

ユーザーがメッセージを送信すると、以下の処理が行われます。

1. クライアントが `/app/sendMessage` にメッセージを送信
2. Spring WebSocket Controllerがメッセージを受信
3. サーバーが `/topic/messages` にメッセージをブロードキャスト
4. 接続中のすべてのクライアントがリアルタイムでメッセージを受信

## プロジェクト構成

```text id="g0w4ae"
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

## WebSocket設定

WebSocket Endpoint:

```text id="5k2c8f"
/chat
```

クライアント接続：

```text id="0f2b6j"
ws://localhost:8080/chat
```

送信先：

```text id="q3r7sn"
/app/sendMessage
```

購読先：

```text id="h7n5vp"
/topic/messages
```

## アプリケーションの起動

リポジトリをクローンします。

```bash id="q0r9wd"
git clone <repository-url>
```

プロジェクトフォルダへ移動します。

```bash id="z3n4kp"
cd chat-application
```

Spring Bootアプリケーションを起動します。

```bash id="a5m8xs"
./mvnw spring-boot:run
```

ブラウザで以下のURLを開きます。

```text id="c6v2kt"
http://localhost:8080/chat
```

複数のブラウザタブを開くことで、リアルタイムメッセージングをテストできます。

## 学習目的

このプロジェクトを通して、以下の内容を学習しました。

* WebSocket通信
* STOMPプロトコル
* SockJSの連携
* Spring WebSocketの設定
* リアルタイムメッセージ処理

## 今後の改善

* ユーザー認証の追加
* チャットメッセージのデータベース保存
* プライベートメッセージ機能
* オンライン・オフライン状態の表示
* メッセージ履歴機能
