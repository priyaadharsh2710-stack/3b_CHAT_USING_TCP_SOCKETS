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
Client:
```
import socket

s = socket.socket()

s.connect(('localhost', 8000))

while True:
    msg = input("Client > ")

    s.send(msg.encode())

    print("Server >", s.recv(1024).decode())

s.close()
```
Server:
```
import socket

s = socket.socket()

s.bind(('localhost', 8000))
s.listen(5)

print("Server Waiting...")

c, addr = s.accept()

print("Connected with", addr)

while True:
    clientMessage = c.recv(1024).decode()

    if not clientMessage:
        break

    print("Client >", clientMessage)

    msg = input("Server > ")

    c.send(msg.encode())

c.close()
s.close()
```

## OUPUT
<img width="904" height="264" alt="Screenshot 2026-05-26 155735" src="https://github.com/user-attachments/assets/a65eb22c-fa98-45af-b739-6b4f97ae3596" />
<img width="872" height="150" alt="Screenshot 2026-05-26 155800" src="https://github.com/user-attachments/assets/7760524d-d254-4556-a992-1f2e166c9c30" />

## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.
