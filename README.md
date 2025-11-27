# CS361RandomASCIIGenerator
This program allows the user to print a piece of ASCII art from a random bank. See code below for example implementation:
Note: make sure you install zmq, or this program will not run. You can change the port as needed, just be sure to change in both files. 
```
import zmq
import time
context = zmq.Context()
socket = context.socket(zmq.REQ)
socket.connect('tcp://localhost:5577')
print('Client is running on port 5577...')
socket.send_string('ascii')
time.sleep(10) # change at will, this ensures the program has time to load.
ascii_art = socket.recv_string()
print(ascii_art)
```
