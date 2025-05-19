# 4.Execution_of_NetworkCommands
## Name: HASMITHA V NANCY
## Reg No: 212224040111
## AIM :Use of Network commands in Real Time environment
## Software : Command Prompt And Network Protocol Analyzer
## Procedure: To do this EXPERIMENT- follows these steps:
<BR>
In this EXPERIMENT- students have to understand basic networking commands e.g cpdump, netstat, ifconfig, nslookup ,traceroute and also Capture ping and traceroute PDUs using a network protocol analyzer 
<BR>
All commands related to Network configuration which includes how to switch to privilege mode
<BR>
and normal mode and how to configure router interface and how to save this configuration to
<BR>
flash memory or permanent memory.
<BR>
This commands includes
<BR>
• Configuring the Router commands
<BR>
• General Commands to configure network
<BR>
• Privileged Mode commands of a router 
<BR>
• Router Processes & Statistics
<BR>
• IP Commands
<BR>
• Other IP Commands e.g. show ip route etc.
<BR>

## Program
Client:
~~~
import socket

s = socket.socket()
s.connect(('localhost', 8000))

while True:
    ip = input("Enter the website you want to ping (or type 'exit' to quit): ")
    s.send(ip.encode('utf-8'))
    if ip.lower() == 'exit':
        break
    print(s.recv(4096).decode('utf-8'))

s.close()
~~~
Server:
~~~
import socket
from pythonping import ping

s = socket.socket()
s.bind(('localhost', 8000))
s.listen(5)
print("Server listening on port 8000...")
c, addr = s.accept()
print(f"Connection from {addr}")

while True:
    try:
        hostname = c.recv(1024).decode('utf-8')
        if not hostname or hostname.lower() == 'exit':
            print("Client disconnected.")
            break
        response = ping(hostname, verbose=False, count=4)
        c.send(str(response).encode('utf-8'))
    except Exception as e:
        c.send(f"Ping failed: {e}".encode('utf-8'))

c.close()
~~~
## Output
### netstat

![image](https://github.com/user-attachments/assets/7c2c4f93-e264-45e0-81c5-abe78b47c57a)

### ipconfig

![image](https://github.com/user-attachments/assets/98dde725-3643-4e53-b2ae-7e2e0123d7ca)


### arp

![image](https://github.com/user-attachments/assets/12f0733d-972f-4a44-a788-fad0ba0254a3)

### getmac

![image](https://github.com/user-attachments/assets/df34880c-079c-4763-96e8-021825a0106f)
### hostname

![image](https://github.com/user-attachments/assets/f09f82f8-0663-474d-b3c1-dea7667df9f8)
### netstat

![image](https://github.com/user-attachments/assets/3a4a95cd-a65c-418d-94ec-f759867c3ad7)
### nslookup

![image](https://github.com/user-attachments/assets/cb655db1-b31d-4d55-aa48-e9f8be6661af)
### png

![image](https://github.com/user-attachments/assets/af9b653b-827a-4a31-8bad-89bb5cb64d8b)
### system info

![image](https://github.com/user-attachments/assets/0c1cab9a-9565-49e8-a436-11402804e044)
### traceert

![image](https://github.com/user-attachments/assets/5a3b6ed8-acba-4d9f-af9f-5baf1c8ec316)
### Program output

![image](https://github.com/user-attachments/assets/9a33dd5e-e03c-4278-8ac0-fcaaed5b702a)


## Result
Thus Execution of Network commands Performed 
