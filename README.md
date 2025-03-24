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
SERVER.PY
```
import socket

HOST = "127.0.0.1"  # Standard loopback interface address (localhost)
PORT = 65432  # Port to listen on (non-privileged ports are > 1023)


with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()
    conn, addr = s.accept()
    with conn:
        print(f"Connected by {addr}")
        while True:
            data = conn.recv(1024)
            if not data:
                break
            conn.sendall(data)

```
CLIENT.PY
```
import socket


HOST = "127.0.0.1"  # The server's hostname or IP address
PORT = 65432  # The port used by the server


with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"TRISHA R(212224100061)")
    data = s.recv(1024)


print(f"Received {data!r}")

```
## OUTPUT:
SERVER.PY
![Screenshot 2025-03-24 144040](https://github.com/user-attachments/assets/e5f8ceb5-8de0-45df-988d-a404e7077e0e)
CLIENT.PY
![Screenshot 2025-03-24 144129](https://github.com/user-attachments/assets/6acfdd54-7e06-4630-a26f-c418e96bd05c)


## RESULT:
The program is executed successfully
