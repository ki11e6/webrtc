# 06. WebRTC Core Architecture

## The Central Object: `RTCPeerConnection`
-   **Native Browser Object**: Available on the `window` object.
-   **Constructor**: Must be instantiated with `new RTCPeerConnection()`.
    -   Creates a new object that manages the entire WebRTC lifecycle.
    -   Provides methods like `createOffer`, `createAnswer`, `addIceCandidate`, `close`, and `createDataChannel`.

## The Two Legs of WebRTC
To master WebRTC, you need to understand two main components: **Data** and the **Connection**.

### 1. Data (What you send)
There are two broad types of data you can transmit:

#### A. Media (Audio/Video)
-   **API**: Media Capture and Streams API.
-   **Object**: `navigator.mediaDevices`.
-   **Functions**:
    -   `getUserMedia()`: Access Camera and Microphone (requires user permission).
    -   `getDisplayMedia()`: Access Screen Sharing.

#### B. Arbitrary Data
-   **API**: `RTCDataChannel`.
-   **Method**: `peerConnection.createDataChannel()`.
-   **Supported Types**:
    -   **Text/JSON**: Sent as plain text strings.
    -   **Binary**: Blobs (file-like objects) and ArrayBuffers (raw binary data).
    -   *Note*: This allows for file transfer, gaming state sync, etc.

### 2. The Connection (How you connect)
-   **Signaling**: The process of setting up the connection (exchanging SDP offers/answers).
-   **NAT Traversal**: Using STUN/TURN servers and ICE candidates to find a path between peers.
-   **Management**: All handled by the `RTCPeerConnection` object instance.

## Summary
The `RTCPeerConnection` object is the brain. You feed it **Data** (Media streams or Data Channels) and manage the **Connection** (Signaling/ICE) to establish the P2P link.
