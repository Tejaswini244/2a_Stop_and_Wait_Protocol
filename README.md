# 2a_Stop_and_Wait_Protocol
```
Name:R.TEJASWINI
Reg no:212224230218
```
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
## SENDER(SERVER)

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

## OUTPUT
<img width="276" height="94" alt="Screenshot 2025-09-03 113954" src="https://github.com/user-attachments/assets/32a90260-1c45-4a9d-b80f-e93e5fabe608" />

## PROGRAM
## RECEIVER(CLIENT)

import socket

s=socket.socket()

s.connect(('localhost',8000))

while True:

    print(s.recv(1024).decode())
    
    s.send("Acknowledgement Received".encode())
    
## OUTPUT
<img width="178" height="71" alt="Screenshot 2025-09-03 114004" src="https://github.com/user-attachments/assets/da6414a9-582e-471c-b495-6e45582f80cb" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
