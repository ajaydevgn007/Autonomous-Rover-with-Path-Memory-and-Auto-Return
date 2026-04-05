# Autonomous-Rover-with-Path-Memory-and-Auto-Return
OVERVIEW:
A rover that records its movement path and automatically retraces it when communication is lost.

COMPONENTS:
Arduino
L293D H-bridge Motor Driver
2 DC motors
Power supply

FEATURES:
Serial control (F, L, R, S)
Path recording
Auto return after 10 seconds of no input
Simple fail-safe system

WORKING:
1)You send commands (F, L, R, S) to move the rover
2)The rover remembers each movement step
3)If no command is received for 10 seconds, it assumes connection is lost
4)It then goes back by repeating the path in reverse:
Forward → Backward
Left → Right
Right → Left
5)Finally, it stops at the starting point

CHALLENGES FACED & SOLUTIONS
1)One challenge was controlling the motors correctly for different movements like left, right, and forward. I solved this by testing each motor connection and adjusting the logic in the code.
2)Another challenge was storing and retracing the path accurately. I solved this by using an array to store each movement and reversing it during return.
3)I also faced issues with repeated execution of the return function, which I fixed by using a flag (returning) to control the flow.
