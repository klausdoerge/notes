
Speech-To-Text
Typically running in online mode, as it requires an external service (provided by browser-vendors). 
It is hard to implement a custom STT module in the browser, and requires a large download of models etc. to use.
Might be possible to build a Python service that allows streaming from client to the server

### **Architecture Overview**

1. **Browser Side**
    
    - Capture microphone audio using `getUserMedia()`.
    - Stream audio to your backend via **WebSocket** or **HTTP POST**.
    - Receive transcription results in real-time or after processing.
2. **Backend (Python)**
    
    - Use an STT engine (e.g., **Vosk**, **Whisper**, **Coqui STT**, or **Picovoice Leopard**).
    - Process incoming audio chunks.
    - Return recognized text to the client.