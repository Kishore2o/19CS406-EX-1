# 19CS406-EX-1 STUDY OF SOCKET PROGRAMMING WITH CLIENT-SERVER MODEL

DATE :

AIM :
To write a python program to perform stop and wait protocol

ALGORITHM :
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client otherwise it will sendNACK signal to client.
6. Stop the program



CLIENT PROGRAM :
```
## Developed By : KISHORE
## Reg No : 212222240050
import socket
s=socket.socket()
s.bind(('localhost',8080))
s.listen(5)
c,addr=s.accept()
while True:
	i=input("ENter a data:")
	c.send(i.encode())
	ack=c.recv(1024).decode()
	if ack:
		print(ack)
		continue
	else:
		c.close()
		break
```
SERVER PROGRAM :
```
import socket
s=socket.socket()
s.connect(('localhost',8080))
while True:
	print(s.recv(1024).decode())
	s.send("Recieved".encode())

```



CLIENT OUTPUT:
![1a](https://github.com/Kishore2o/19CS406-EX-1/assets/118679883/3a9528f1-b37c-460d-9188-59543794e4b8)

SERVER OUTPUT:
![1b](https://github.com/Kishore2o/19CS406-EX-1/assets/118679883/e0730821-a7b3-4615-bf06-b182df980d8c)



RESULT:

Thus, python program to perform stop and wait protocol was successfully executed.
