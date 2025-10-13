# Ex.No:1a  			Study of Socket Programming
## NAME: VISHAL.C
## REG NO : 212224100062


## Aim: 
To write a python program to perform sliding window protocol
## ALGORITHM:
ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
otherwise it will sendNACK signal to client.
6. Stop the program
PROGRAM:

SERVER

import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())

CLIENT

import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
 i=input("Enter a data: ")
 c.send(i.encode())
 ack=c.recv(1024).decode()
 if ack:
 print(ack)
 continue
 else:
 c.close()
 break

## OUTPUT:

## server.py

<img width="409" height="156" alt="Screenshot 2025-10-13 153523" src="https://github.com/user-attachments/assets/98d30ad3-8aa4-44ee-b192-0dcf3eed3e95" />


## client.py

<img width="398" height="214" alt="Screenshot 2025-10-13 153510" src="https://github.com/user-attachments/assets/2a841641-80a0-4612-b8f9-8a9853d9c701" />


 
## Result:
Thus the study of Socket Programming Completed Successfully
