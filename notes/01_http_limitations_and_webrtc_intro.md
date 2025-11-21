# 01. HTTP Limitations & The Need for WebRTC

## The Traditional HTTP Model
- **Architecture**: Client-Server-Client.
- **Flow**:
    1. User 1 sends data (e.g., "Hi") to the Server (via AJAX/Fetch/WebSockets).
    2. Server receives the data.
    3. Server must relay this information to User 2.
    4. User 2 receives the update and updates the DOM.

## Limitations of HTTP for Real-Time Communication
HTTP was designed for a **Request-Response** model, not for real-time, bidirectional streaming.

1.  **Unidirectional Communication**:
    -   Traditionally, only the client can initiate requests.
    -   The server cannot easily "push" data to the client without workarounds.

2.  **Latency & Relay Issues**:
    -   All messages must pass through the server, introducing lag.
    -   "Real-time" is simulated, not native.

3.  **Server Dependency (Single Point of Failure)**:
    -   If the server crashes, all communication stops.
    -   Users cannot communicate directly even if they are on the same network.

4.  **Inefficient Workarounds**:
    -   **Polling**: Client repeatedly asks "Any updates?" (Resource heavy).
    -   **Long Polling**: Client holds a request open until the server has data (Still resource heavy).
    -   **Server-Sent Events (SSE)**: Allows server push, but is text-only and unidirectional (Server -> Client only).
    -   **WebSockets**: Provides bidirectional channels (and is used with WebRTC for signaling), but traditional server-based architectures still rely on the server relaying media/messages.

## Why WebRTC?
-   **Real-Time Capability**: Solves the latency and architectural limitations of HTTP.
-   **Direct Communication**: Enables peer-to-peer data/media exchange (implied context).
