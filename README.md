# Stop and Wait Protocol
## AIM : 
To write a python program to perform stop and wait protocol
## ALGORITHM :
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM :
### Client Program :
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
    i=input("Enter a data: ")
    c.send(i.encode())
    ack=c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else:
        c.close()
        break
```
### Server Program :
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Received".encode())
```

## OUTPUT :
![Screenshot 2024-03-04 144611](https://github.com/22008837/2a_Stop_and_Wait_Protocol/assets/120194155/2bea280e-1af0-4c04-9799-3eb31475fb9d)

## RESULT :
Thus, python program to perform stop and wait protocol was successfully executed.
