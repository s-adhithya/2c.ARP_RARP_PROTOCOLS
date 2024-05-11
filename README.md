# 2c.SIMULATING ARP /RARP PROTOCOLS
## AIM
To write a python program for simulating ARP protocols using TCP.
## ALGORITHM:
## Client:
1. Start the program
2. Using socket connection is established between client and server.
3. Get the IP address to be converted into MAC address.
4. Send this IP address to server.
5. Server returns the MAC address to client.
## Server:
1. Start the program
2. Accept the socket which is created by the client.
3. Server maintains the table in which IP and corresponding MAC addresses are
stored.
4. Read the IP address which is send by the client.
5. Map the IP address with its MAC address and return the MAC address to client.
P
## PROGRAM - ARP
### Client
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
address={"165.165.80.80":"6A:08:AA:C2","165.165.79.1":"8A:BC:E3:FA"};
while True:
 ip=c.recv(1024).decode()
 try:
 c.send(address[ip].encode())
 except KeyError:
 c.send("Not Found".encode())
```
### Server
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
REG NO:
 ip=input("Enter logical Address : ")
 s.send(ip.encode())
 print("MAC Address",s.recv(1024).decode()
```
## OUPUT - ARP
### Client
![310866912-eb148f0f-9fcc-4639-80a7-2f360798bf39](https://github.com/s-adhithya/2c.ARP_RARP_PROTOCOLS/assets/113497423/38dcf1d6-97b1-400a-80fe-a450a09cad8a)
### Server
![310866949-a5f5e179-cf14-466b-93ca-f487b23a05f4](https://github.com/s-adhithya/2c.ARP_RARP_PROTOCOLS/assets/113497423/875f620d-32a1-4a43-9796-68ca48f47a45)

## PROGRAM - RARP
### Client
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
### Server
```
import socket
s=socket.socket()
s.connect(('localhost',9000))
while True:
 ip=input("Enter MAC Address : ")
 s.send(ip.encode())
 print("Logical Address",s.recv(1024).decode())
```
## OUPUT -RARP
### Client
![310867312-16b04d72-d7e3-433f-9732-502459dc0d11](https://github.com/s-adhithya/2c.ARP_RARP_PROTOCOLS/assets/113497423/5591d203-5b43-493d-8880-79fd8d7cef72)
### Server
![310867328-7532a3bf-66ce-4540-b892-24fa8ca1e841](https://github.com/s-adhithya/2c.ARP_RARP_PROTOCOLS/assets/113497423/8edc4107-fe3e-4837-b5ce-784d87659b75)

## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
