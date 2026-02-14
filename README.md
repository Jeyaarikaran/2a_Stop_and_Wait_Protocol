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
s.setsockopt(socket.SOL_SOCKET, socket.SO_REUSEADDR, 1)

s.bind(('localhost', 9000))
s.listen(1)

print("Server waiting for connection...")

conn, addr = s.accept()
print("Connected by:", addr)

data = conn.recv(1024)
print("Client says:", data.decode())

conn.send(b"Hello from server")

conn.close()
s.close()
```

### client.py
```.py
import socket

c = socket.socket()
c.connect(('localhost', 9000))

c.send(b"Hello Server")

data = c.recv(1024)
print("Server says:", data.decode())

c.close()
```

## OUTPUT
### server.py
<img width="970" height="367" alt="2a server" src="https://github.com/user-attachments/assets/aea3b4e8-ad34-4775-af23-4e50496aeecf" />


### client .py
<img width="900" height="332" alt="2a client" src="https://github.com/user-attachments/assets/8166d545-977c-4ab3-9f57-0c41ee91f114" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
