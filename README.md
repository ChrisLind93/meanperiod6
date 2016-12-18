### Name some of the attributes of the HTTP protocol which makes it difficult to use for real time systems.

A hard real-time system is hardware or software that must operate within the confines of a stringent deadline.

Examples of attributes:
- Cache-control
  - This instructs the user agent that the content is stale and should be validated before use.
- If-modified-since
  - Allows a 304 Not Modified to be returned if content is unchanged.
- If-unmodified-since
  - Only send the response if the entity has not been modified since a specific time.
- If-match
  - Only perform the action if the client supplied entity matches the same entity on the server.
- If-none-match
  - Allows a 304 Not Modified to be returned if content is unchanged.

--------------------------------------------------------------------------------------------------------------------

### Explain polling and long-polling strategies, their pros and cons

- Polling is the process where the computer or controlling device waits for an external device to check for its readiness or state, often with low-level hardware. 
  
  For example, when a printer is connected via a parallel port, the computer waits until the printer has received the next character.
  
  In networks, polling is used to determine which nodes want to access the network. It is also used by routing protocols to retrieve routing information, as is the case with EGP (Exerior Gateway Protocol).
  - Pros:
    - The main advantage of polling is that the CPU determines how often it needs to poll.
    - If the CPU can be late handling the device, then polling prevents the CPU from being interrupted.
  - Cons:
    - The problem with polling is that the CPU operates at a much faster speed than most I/O devices. Thus, a CPU can get into a busy wait, checking the device many times, even though the device is very slow.
    - Polling to though require the devices to be quick.
- Long polling is a variation of the traditional polling technique. 
  
  With long polling, the client requests information from the server exactly as in normal polling, but with the expectation of the server not possibly responding immediately.
  
  If the server has no new information for the client when the poll is received, instead of sending an empty response, the server holds the request open and waits for the response information to become available. 
  - Pros:
    - Long polling allows emulating a push mechanism under circumstances where a real push is no possible, such as sites with security policies that require rejection of incoming HTTP/s requests.
  - Cons:
    - The server does not immediately respond but waits until there is new information available.
    
--------------------------------------------------------------------------------------------------------------------

### What is the WebSocket protocol, how is it different from HTTP communication, what advantages it has over HTTP?

WebSocket is a protocol providing full-duplex communication channels over a single TCP connection.

WebSocket is designed to be implemented in web browsers and web servers, but it can be used by any client or server application.

The WebSocket protocol is currently supported in most major browsers including Chrome, IE, Firefox, Safari and Opera.
One difference is that WebSocket provides perform bi-directional, full-duplex communication unlike HTTP. 

This means that WebSockets allows communication in both directions, and unlike half-duplex, allows this to happen simultaneously.

Another difference is that WebSockets require full-duplex connections and new WebSocket servers to handle the protocol. 

--------------------------------------------------------------------------------------------------------------------

### Explain what the WebSocket Protocol brings to the Web-world.

What WebSocket brings to the web-world is that it provides full-duplex communication unlike HTTP.

Additionally, WebSocket enables streams of messages on top of TCP. TCP alone deals with streams of bytes with no inherent concept of a message.

--------------------------------------------------------------------------------------------------------------------

### What's the advantage of using libraries like Socket.IO, Sock.JS, WS, over pure WebSocket libraries in the backend and standard APIs on frontend? Which problems do they solve?

- Socket.io can be used as a wrapper for WebSocket but provides many more features, including broadcasting to multiple sockets, storing data associated with each client, and asynchronous I/O. 
  
  It allows you to send/emit messages by specifying an event name,

- SockJS is a JavaScript library (for browsers) that provides a WebSocket-like object. 
  SockJS gives you a coherent, cross-browser, JavaScript API which creates a low latency, full duplex, cross-domain communication channel between the browser and the web server, with WebSockets or without.
