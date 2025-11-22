# 05. WebRTC Use Cases

## Beyond Video Calling
While originally designed for **Peer-to-Peer (P2P) video/audio calls** between two browsers, WebRTC's capabilities have expanded significantly.

## Key Use Cases

### 1. Multiplayer Gaming
-   **Low Latency**: Critical for real-time games (e.g., First Person Shooters).
-   **Technology**: Uses `RTCDataChannel` to sync game state directly between players.
-   **Example**: *Banana Bread* (FPS game running in the browser using WebRTC).

### 2. File Sharing & Arbitrary Data
-   **Direct Transfer**: Send files, images, and videos directly between users without uploading to a server first.
-   **P2P Content Delivery**:
    -   Example: **PeerCDN** (acquired by Yahoo).
    -   Users viewing the same content can share resources (images, scripts) with each other, reducing server bandwidth.

### 3. Streaming & Education
-   **Live Streaming**: Low-latency broadcasting.
-   **Video on Demand (VoD)**: Educational platforms delivering recorded lectures.
-   **Music Streaming**: P2P audio distribution.

### 4. Healthcare (Telehealth)
-   **Secure Data Transmission**: Sending medical records, lab results, and high-res X-rays.
-   **Security**: WebRTC uses **DTLS** (Datagram Transport Layer Security) by default, ensuring data is encrypted just like HTTPS.

### 5. Internet of Things (IoT)
-   **Remote Control & Monitoring**:
    -   Security cameras.
    -   Thermostats.
    -   **Drones**: Real-time video feed and control signals.

## Summary
WebRTC is a versatile technology for **any** application requiring real-time, secure, and direct data exchange, extending far beyond simple video chat apps.
