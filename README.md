
## PROGRAM:
# SERVER
```
import socket

HOST = "127.0.0.1"  # Standard loopback interface address (localhost)
PORT = 65432  # Port to listen on (non-privileged ports are > 1023)

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    try:
        s.bind((HOST, PORT))
    except Exception as e:
        print(f"Error binding to {HOST}:{PORT}: {e}")
        exit()
    
    s.listen()
    print(f"Listening on {HOST}:{PORT}...")

    try:
        conn, addr = s.accept()
    except Exception as e:
        print(f"Error accepting connection: {e}")
        exit()

    with conn:
        print(f"Connected by {addr}")
        while True:
            try:
                data = conn.recv(1024)
                if not data:
                    break
                conn.sendall(data)
            except Exception as e:
                print(f"Error receiving/sending data: {e}")
                exit()
```
# CLIENT
```
import socket
HOST = "127.0.0.1"  # The server's hostname or IP address
PORT = 65432  # The port used by the server
with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"selva jobi 03-03-2025")
    data = s.recv(1024)

print(f"Received {data!r}")
```

## OUTPUT:
# SERVER:
![438d38d3-143f-407c-b8af-7a341a1e4d48](https://github.com/user-attachments/assets/0286ad1e-64f2-47c8-af47-d19d97292c34)


# Client:
![438d38d3-143f-407c-b8af-7a341a1e4d48](https://github.com/user-attachments/assets/0ec71b59-47cb-4090-86f3-a74d63634810)


## RESULT:
The program is executed successfully
