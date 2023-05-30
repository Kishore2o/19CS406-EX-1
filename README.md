# EX-1 STUDY OF SOCKET PROGRAMMING WITH CLIENT-SERVER MODEL
# DATE : 
09-03-2023
# AIM :
To implement socket programming date and time display from client to server using TCPSockets

# ALGORITHM :
# SERVER :
1. Create a server socket and bind it to port.
2. Listen for new connection and when a connection arrives, accept it.
3. Send server‟s date and time to the client.
4. Read client‟s IP address sent by the client.
5. Display the client details.
6. Repeat steps 2-5 until the server is terminated.
7. Close all streams.
8. Close the server socket.
Stop.
# CLIENT :
1. Create a client socket and connect it to the server‟s port number.
2. Retrieve its own IP address using built-in function.
3. Send its address to the server.
4. Display the date & time sent by the server.
5. Close the input and output streams.
6. Close the client socket.
Stop.
# PROGRAM :
# CLIENT :
```
# Developed by :KISHORE.S
# Register Number : 22008388
import socket
from datetime import datetime
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
print("Client Address : ",addr)
now = datetime.now()
c.send(now.strftime("%d/%m/%Y %H:%M:%S").encode())
ack=c.recv(1024).decode()
if ack:
    print(ack)
    c.close()
```
# SERVER :
```
# Developed by :KISHORE.S
# Register Number : 22008388
import socket
s=socket.socket()
s.connect(('localhost',8000))
print(s.getsockname())
print(s.recv(1024).decode())
s.send("acknowledgement recived from the server".encode())
```
# OUTPUT :
# CLIENT :
![1a](https://github.com/Kishore2o/19CS406-EX-1/assets/118679883/f0864b2b-8a38-48e9-b609-0a71a46cd1d0)

# SERVER :
![1b](https://github.com/Kishore2o/19CS406-EX-1/assets/118679883/1cd30196-99d8-46f0-b588-e2f49380887d)

RESULT:
Thus, the program to implement socket programming date and time display from client to server using TCP Sockets was successfully executed.
