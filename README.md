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
### Client-side:
```
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
```

### Server side:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```
## OUTPUT
Client:
<img width="1193" height="301" alt="Screenshot 2025-09-17 103326" src="https://github.com/user-attachments/assets/8c4bc812-f9d0-4f4c-96e9-191eb917f0aa" />

Server:
<img width="1203" height="175" alt="Screenshot 2025-09-17 103336" src="https://github.com/user-attachments/assets/3acafeb9-f853-4237-a92b-a4a4b3f5cd30" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
