# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
# AIM
To write a python program for creating Echo Client and Echo Server using TCP
Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server .
4. Send and receive the message using the send function in socket.
## PROGRAM:
NAME: SHYAM S
REG.NO: 212223240156

## CLIENT:
```
import socket
client = socket.socket()
client.connect(('localhost', 8000))
print("Connected to server.")

while True:
    msg = input("You: ")
    if msg.lower() == 'exit':
        break
    client.send(msg.encode())
    reply = client.recv(1024).decode()
    print("Server:", reply)

client.close()
print("Disconnected.")
```

## SERVER:
```
import socket
server = socket.socket()
server.bind(('localhost', 8000))
server.listen(1)

print("Server is ready and waiting...")
client, address = server.accept()
print("Connected to:", address)

while True:
    message = client.recv(1024).decode()
    if not message:
        break
    print("Client:", message)
    client.send(message.encode())

client.close()
server.close()
print("Server stopped.")
```

## OUTPUT:
## CLIENT:
![image](https://github.com/user-attachments/assets/a737d24b-bbd6-4fe3-9e3c-e4b5c85fdb39)

## SERVER:
![image](https://github.com/user-attachments/assets/354e0b77-5b2c-4166-ae11-dcafa04af6e5)

## RESULT:
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
