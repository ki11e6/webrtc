# 02. WebRTC Basics & Benefits

## Why WebRTC? (vs. WebSockets/SSE)
While WebSockets, AJAX, and Server-Sent Events (SSE) exist, they all rely on a **server** to relay messages.
-   **WebRTC is unique**: It enables **Peer-to-Peer (P2P)** connectivity.
-   **No Server (for data transfer)**: Once connected, data flows directly between users.
    -   Fewer hops.
    -   Lower latency.
    -   Ideal for real-time communication (video, audio, gaming).

## The `RTCPeerConnection` API
-   The core API used in the browser is `RTCPeerConnection`.
-   **Browser Context**: This API is provided by the browser.
-   **Mobile Context**: WebRTC is not limited to browsers.
    -   Android: Java APIs (official WebRTC library).
    -   iOS: Objective-C/Swift APIs (WebRTC framework).
    -   Allows access to native camera/audio streams for better performance.

## Key Characteristics of WebRTC
1.  **Direct Data Exchange**:
    -   Connects two endpoints (peers) directly.
    -   If the signaling server crashes *after* connection, the P2P stream **continues** uninterrupted.
2.  **Not HTTP**:
    -   WebRTC does **not** use HTTP/2 or HTTP/3.
    -   It uses its own set of protocols (piggybacking on UDP).
    -   Requires a secure connection (TLS), but is distinct from HTTP.
3.  **Persistent Connection**:
    -   The connection stays open; no need to re-establish for every message.

## The "No Server" Caveat
While the *media/data* flows P2P, servers are still required for **setup**:
1.  **Signaling Server**:
    -   Used to discover peers and exchange connection details (SDP, ICE candidates).
    -   Not defined by WebRTC standard; developers must build this (e.g., using Node.js, WebSockets).
2.  **External Servers (NAT Traversal)**:
    -   **STUN Servers**: To discover public IP addresses.
    -   **TURN Servers**: To relay traffic if P2P fails (e.g., strict firewalls).

## Scalability
-   Traditional WebRTC is Mesh (P2P).
-   To scale beyond two users (e.g., conferencing), architectures often use **SFU** (Selective Forwarding Unit) or **MCU** (Multipoint Control Unit) servers to route streams, rather than pure full-mesh P2P.
