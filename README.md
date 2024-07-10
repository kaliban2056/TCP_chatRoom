# Simple Chat Application

This project is a basic implementation of a multi-client chat application using Python's `socket` and `threading` modules. It includes two main components:
1. `server.py`: The server script to handle multiple clients and broadcast messages.
2. `client.py`: The client script to connect to the server and send/receive messages.

## Features
- Multiple clients can connect to the server and communicate with each other.
- Each client selects a nickname upon connecting to the server.
- Messages are broadcast to all connected clients.
- Clients are notified when a user joins or leaves the chat.

## Getting Started

### Prerequisites

- Python 3.x

### Running the Server

1. Open a terminal or command prompt.
2. Navigate to the directory containing `server.py`.
3. Run the server script:
    ```sh
    python server.py
    ```

The server will start listening for incoming connections on `127.0.0.1:55555`.

### Running the Client

1. Open a terminal or command prompt.
2. Navigate to the directory containing `client.py`.
3. Run the client script:
    ```sh
    python client.py
    ```
4. Enter a nickname when prompted.

You can run multiple instances of `client.py` to simulate multiple clients connecting to the server.

## How It Works

### server.py

- The server binds to a specified host and port (`127.0.0.1:55555`).
- It listens for incoming connections and handles each client in a separate thread.
- It maintains lists of connected clients and their nicknames.
- It broadcasts messages received from any client to all other connected clients.
- If a client disconnects, it removes the client from the list and notifies the remaining clients.

### client.py

- The client connects to the server at the specified host and port.
- It prompts the user to choose a nickname.
- It starts two threads: one for receiving messages from the server and another for sending messages to the server.
- It handles receiving the initial nickname prompt from the server and sends the chosen nickname.
- It continuously reads user input and sends messages to the server.

## Example

1. Start the server:
    ```sh
    python server.py
    ```

2. Start a client:
    ```sh
    python client.py
    ```
   Choose a nickname when prompted.

3. Start additional clients in separate terminals:
    ```sh
    python client.py
    ```
   Choose different nicknames for each client.

4. Send messages from any client. All connected clients will receive the messages.

## Acknowledgements

This project was created as a simple demonstration of using sockets and threading in Python to build a basic chat application.

---

Enjoy chatting!
