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
#### server.py
```.py
import socket
s = socket.socket()
s.bind(('localhost', 8001))
s.listen(5)
c, addr = s.accept()
print("Connected:", addr)
while True:
    i = input("Enter a data: ")
    c.send(i.encode())
    ack = c.recv(1024).decode()
    if ack:
        print(ack)
    else:
        c.close()
        break
```

### client.py
```.py
import socket
s = socket.socket()
s.connect(('localhost', 8001))
while True:
    msg = s.recv(1024).decode()
    print(msg)
    s.send("Acknowledgement Received from the server".encode())
```

## OUTPUT

<img width="1918" height="1198" alt="exp2a" src="https://github.com/user-attachments/assets/2ee5a565-d8c0-4498-a08e-b72c496bc804" />


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
