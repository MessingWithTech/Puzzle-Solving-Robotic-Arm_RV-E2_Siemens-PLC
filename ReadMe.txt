# RV-E2_VisionSensing_Puzzle_-Robot
Communications between Programmable Logic Computer and Vision Sensors with working Robotic Arm and Human Machine Interface

Using an IFM O2D220 Object Recognition Sensor & IFM O2I100 Multicode Reader 
used along with a S7-1200 Siemens PLC and a Mitsubishi Movemaster RV-E2 and CR-E116
to complete a 16 piece puzzle.

https://projectmerseburg.wordpress.com/
See Youtube for Project Video 

https://www.youtube.com/watch?v=yjkZb0mFjC0

https://www.youtube.com/watch?v=vzlLvMzLd0M

Background Info:
In our Control and Automation project we used a Mitsubishi RV-E2 robotic arm, controlled by a CR-E116 controller box, to move sixteen different puzzle tiles. On each tile was four different pictures of either a boat, cross, tree or volcano in any order. The goal was to match each picture to the same picture on a different tile in a 4x4 sequence.  Each piece was moved within the robot’s working area to different predetermined positions. We used a ‘teach in’ function on a P6TB-TE pendant that came with the robotic arm to save these positions to the robot’s memory.

The tiles first position was held in front of an object recognition sensor, IFM O2D220, supplied to us by IFM. The tile was placed down and the arm moved out of view of the sensor. The sensor was triggered when the arm moved out of position by an output bit from the CR-E116 program. It then read the contours of the tile by matching the pictures to a previously saved application. . When triggered the sensor sent a string to a Siemens Simatic S7-1200 PLC. The string was cut down and the relevant information was converted into an integer. This integer was saved to an internal data register and the robotic arm was then signalled to move on to the next location.

The tiles next position was held in front of a multicode reader, used as a QR code scanner, also supplied to us by IFM. On the back of each puzzle tile was a different QR code numbered 01-16, representing the first tile position to the last tile position. When the tile was moved into position by the robotic arm, the sensor (IFM O2I100) was triggered by a second output bit of the program. It then sent another string to the PLC which was again cut down and converted into another integer.

The integers from both sensors were then compared and if it was a match, the tile was successfully identified. The identified tile was then picked back up by the robotic arm and moved to the correct position in the 4x4 puzzle. The robotic arm would then run this cycle another fifteen times until all the tiles were placed in the correct order and the puzzle was complete.
