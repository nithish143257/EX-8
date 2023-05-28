# EX-8 APPLICATION USING TCP SOCKETS - CREATING ECHO CLIENT-SERVER
# DATE : 27.04.2023
# AIM :
### To write a python program for creating Echo Client and Echo Server using TCP Sockets Links.
# ALGORITHM :
### 1.Start the program.
### 2.Get the frame size from the user
### 3.To create the frame based on the user request.
### 4.To send frames to server from the client side.
### 5.If your frames reach the server, it will send ACK signal to client otherwise it will send NACKsignal to client.
### 6.Stop the program.
# CLIENT PROGRAM :
```python 
import socket
s = socket.socket()
s.connect(('localhost', 8000))
while True:
    msg = input("Client > ")
    s.send(msg.encode())
    print("Server > ", s.recv(1024).decode())
```
# SERVER PROGRAM :
```py
import socket
s = socket.socket()
s.bind(('localhost', 8000))
s.listen(5)
c, addr = s.accept()
while True:
    ClientMessage = c.recv(1024).decode()
    c.send(ClientMessage.encode())
```
#  SERVER OUTPUT :
![5serout](https://github.com/MOHAMEDROSHAN5/EX-8/assets/121704588/dfc905ad-9f6f-42c0-91d4-886c42d2fe96)
# CLIENT OUTPUT :
![5cliout](https://github.com/MOHAMEDROSHAN5/EX-8/assets/121704588/01ac3b7b-0d3a-4134-8988-fe131864026c)
# RESULT :
### Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links was successfully created and executed.
