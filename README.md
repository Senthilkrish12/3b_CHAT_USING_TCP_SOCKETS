# Ex.No:3(B) PROGRAM FOR REVERSE ADDRESS RESOLUTION PROTOCOL 
(RARP) USING UDP
## NAME: SENTHIL RAJ G
## REG NO : 212224100054


## Aim: 
To write a python program for simulating RARP protocols using UDP

## ALGORITHM:

## Server:
1. Start the program.
2. Server maintains the table in which IP and corresponding MAC addresses are stored.
3. Read the MAC address which is send by the client.
4. Map the IP address with its MAC address and return the IP address to client
   
## Client:
1. Start the program
2. Using datagram sockets UDP function is established.
3. Get the MAC address to be converted into IP address.
4. Send this MAC address to server.
5. Server returns the IP address to client.
PROGRAM:

## SERVER
```
import socket
s=socket.socket()
s.connect(('localhost',9000))
while True:
 ip=input("Enter MAC Address : ")
 s.send(ip.encode())
 print("Logical Address",s.recv(1024).decode())
```
## CLIENT
```
import socket
s=socket.socket()
s.bind(('localhost',9000))
s.listen(5)
c,addr=s.accept()
address={"6A:08:AA:C2":"192.168.1.100","8A:BC:E3:FA":"192.168.1.99"};
while True:
 ip=c.recv(1024).decode()
 try:
 c.send(address[ip].encode())
 except KeyError:
 c.send("Not Found".encode())
```
## OUTPUT:

## server.py

<img width="716" height="408" alt="image" src="https://github.com/user-attachments/assets/e01693e2-a3e9-4845-adea-ac305739dfcc" />


## client.py

<img width="671" height="221" alt="image" src="https://github.com/user-attachments/assets/69d1a99a-a00d-4445-9c6a-05a95e908557" />



## Result:
Thus the study of Socket Programming Completed Successfully
