# Echoserver
Echo server and client using python socket

# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

Design of echo server and client using python socket

### Step 2:

Implementation using Python code

### Step 3:

Testing the server and client 

## PROGRAM:
## CLIENT:
```
import socket
HOST, PORT = '127.0.0.1', 65432
with socket.create_connection((HOST, PORT)) as s:
    s.sendall(b'Suriya Pravin M, 2122223230223')
    print(f'Received: {s.recv(1024)!r}')
```

## SERVER:
```
import socket
host,port='127.0.0.1',65432
with socket.create_server((host,port))as s:
    conn,addr=s.accept()
    with conn:
        print(f'connected by {addr}')
        while data :=conn.recv(1024):
            conn.sendall(data)
```

## OUTPUT:
## CLIENT:
![image](https://github.com/user-attachments/assets/e4ccb114-529f-4ba3-95c3-c31737b53ba1)
## SERVER:
![image](https://github.com/user-attachments/assets/00d44627-571f-4f7d-b9bc-b339a1f43463)


## RESULT:
The program is executed successfully
