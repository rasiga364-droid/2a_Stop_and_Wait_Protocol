# 2a_Stop_and_Wait_Protocol
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
```
import random
import time

class StopAndWait:
    def __init__(self, frames, loss_prob=0.3, delay=1):
        self.frames = frames
        self.loss_prob = loss_prob
        self.delay = delay

    def send(self):
        for i, frame in enumerate(self.frames):
            ack_received = False
            while not ack_received:
                print(f"Sender: Sending Frame {i} -> {frame}")
                time.sleep(self.delay)

                # Simulate random loss
                if random.random() < self.loss_prob:
                    print(f"Receiver: Frame {i} received, but ACK lost!")
                    print("Sender: Timeout! Retransmitting...\n")
                else:
                    print(f"Receiver: Frame {i} received successfully.")
                    print(f"Receiver: Sending ACK {i}")
                    ack_received = True
                    print("Sender: ACK received. Moving to next frame.\n")

# Example usage
frames = ["Data1", "Data2", "Data3", "Data4"]
protocol = StopAndWait(frames)
protocol.send()
```
Name:S RASIGA
REG NO: 212225220081
## OUTPUT
<img width="1027" height="825" alt="image" src="https://github.com/user-attachments/assets/46b37bb1-ff58-46d3-b3bc-dbef1b7f341e" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
