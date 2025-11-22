# 04. WebRTC Standards & Protocols

## Timeline of Evolution
-   **Oct 27, 2011**: First Working Draft introduced.
-   **Feb 2013**: First cross-browser video call (Firefox <-> Chrome).
-   **Feb 2014**: **Data Channels** introduced (sending arbitrary data beyond just audio/video).
-   **2017**: Moved to Candidate Recommendation.
-   **Jan 26, 2021**: Became a formal **W3C Recommendation**.
    -   "Recommendation" in W3C terms means a finalized, stable, and formally endorsed standard for real-world application development.

## What is WebRTC? (Technically)
-   **Name**: **Web** (intended for browsers) + **RTC** (Real-Time Communication).
-   **Structure**: unlike HTTP/2 or WebSockets which have a single protocol document, WebRTC is an **amalgamation** of many standards.

### The Governing Bodies
1.  **W3C (World Wide Web Consortium)**:
    -   Defines the **APIs** (ECMAScript/JavaScript) used in the browser (e.g., `RTCPeerConnection`).
    -   Main Specification: Defines the set of APIs to allow media and generic application data to be sent/received.
2.  **IETF (Internet Engineering Task Force)**:
    -   Defines the underlying **Protocols** (the "plumbing").
    -   Published as **RFCs** (Request for Comments).
    -   Examples:
        -   RFC 8832 (WebRTC Data Channels).
        -   Protocols for security, transport, NAT traversal, etc.

## Key Takeaway
WebRTC is not just one thing; it is a collection of **APIs (W3C)** and **Protocols (IETF)** working together to enable real-time, peer-to-peer communication for audio, video, and arbitrary data.
