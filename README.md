# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
REGISTER NO:212223240145
# AIM
To write a python program for creating Echo Client and Echo Server using TCP
Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server .
4. Send and receive the message using the send function in socket.
## PROGRAM
CLIENT:
```
import socket

HOST = '127.0.0.1'  
PORT = 65432       

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
  s.bind((HOST, PORT))
  s.listen()
  conn, addr = s.accept()
  with conn:
    print('Connected by', addr)
    while True:
      data = conn.recv(1024)
      if not data:
        break
      conn.sendall(data)
```
SERVER:
```
import socket

HOST = '127.0.0.1'  
PORT = 65432        

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
   s.connect((HOST, PORT))
   while True:
      message = input("Enter message to send to server: ")
      s.sendall(message.encode())
      data = s.recv(1024)
      print('Received', repr(data.decode()))
```
## OUPUT
![image](https://github.com/Sanafathima95773/3a.Sockets_Creation_for_Echo_Client_and_Echo_Server/assets/147084627/08ad8a5b-5881-4d14-85dc-ab2a94ea4eb3)

## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
