# EX-4 IMPLEMENTATION OF ADDRESS RESOLUTION PROTOCOL (ARP)
DATE : 27.03.2023

## AIM :
To write a python program for simulating ARP protocols using TCP

## ALGORITHM :
## CLIENT:

1.Start the program

2.Using socket connection is established between client and server.

3.Get the IP address to be converted into MAC address.

4.Send this IP address to server.

5.Server returns the MAC address to client.

## SERVER:

1.Start the program

2.Accept the socket which is created by the client.

3.Server maintains the table in which IP and corresponding MAC addresses are stored.

4.Read the IP address which is send by the client.

5.Map the IP address with its MAC address and return the MAC address to client.

## CLIENT PROGRAM :
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
## SERVER PROGRAM :
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    ip=input("Enter logical Address : ")
    s.send(ip.encode())
    print("MAC Address",s.recv(1024).decode())
 `````   
## CLIENT OUTPUT :

![3aclient](https://github.com/yogeshrao05/EX-4/assets/122008288/db3f39c1-1198-474b-beeb-6fc2165a1051)

## SERVER OUTPUT :

![3asever](https://github.com/yogeshrao05/EX-4/assets/122008288/5b3e8cbf-7fca-4ed6-97a2-ed1fc0bd5e20)

## RESULT:
Thus, the python program for simulating ARP protocols using TCP was successfully executed.
