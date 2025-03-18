# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
CLIENT:
```py
import socket
s=socket.socket()
s.bind(('localhost', 8000))
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
```
SERVER:
```py
import socket
s = socket.socket()
s.connect(('localhost', 8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```
## OUTPUT
CLIENT:
![Screenshot 2025-03-18 205858](https://github.com/user-attachments/assets/e5baef14-111c-4ece-8378-74df67468f92)
SERVER:
![Screenshot 2025-03-18 205941](https://github.com/user-attachments/assets/f1afc058-4637-4c95-92fb-c782795deb56)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
