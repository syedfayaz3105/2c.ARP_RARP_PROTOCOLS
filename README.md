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
```
import socket
s=socket.socket()
s.bind(('localhost',8880))
s.listen(5)
c,addr=s.accept()
address={"192.168.153.137":"E0-2E-0B-3A-27-17"};
while True:
    ip=c.recv(1024).decode()
    try:
        c.send(address[ip].encode())
    except KeyError:
        c.send("Not Found".encode())
```
## OUPUT - ARP
![arp](https://github.com/user-attachments/assets/ee4fa829-9cd8-4eb7-93d1-820ae2eb8fac)

## PROGRAM - RARP
import socket
s=socket.socket()
s.connect(('localhost',8880))
while True:
    ip=input("Enter Logical Address:")
    s.send(ip.encode())
    print("MAC address",s.recv(1024).decode())

## OUPUT -RARP
![rarp](https://github.com/user-attachments/assets/0ed67cf9-aa6f-4e42-b6e8-2f4d1722b81b)

## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
