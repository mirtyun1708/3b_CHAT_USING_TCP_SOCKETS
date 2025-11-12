# 3b.CREATION FOR CHAT USING TCP SOCKETS
## AIM
To write a python program for creating Chat using TCP Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server
4. Send and receive the message using the send function in socket.
## PROGRAM
### Client
```python
import socket
s = socket.socket()
s.connect(('localhost', 8000))
while True:
    msg = input("Client > ")
    if msg.lower() == "exit":
        s.close()
        break
    s.send(msg.encode())
    print("Server >", s.recv(1024).decode())
```
### Server
```python
import socket
s = socket.socket()
s.bind(('localhost', 8000))
s.listen(1)
c, addr = s.accept()
while True:
    ClientMessage = c.recv(1024).decode()
    if not ClientMessage:
        break
    print("Client >", ClientMessage)
    msg = input("Server > ")
    c.send(msg.encode())
```
## OUPUT
### Client
![WhatsApp Image 2025-11-10 at 10 42 26_c94db3c2](https://github.com/user-attachments/assets/a5638c2b-4c90-4bf5-9276-46d7c63ac145)
### Server
![WhatsApp Image 2025-11-10 at 10 42 26_55302c21](https://github.com/user-attachments/assets/a116bea0-da96-41f3-8a4c-03da0c212080)



## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.
