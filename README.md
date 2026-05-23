# Stick 'Em Project Specifications

## Development Platform
I am developing on a Windows laptop. But I intend for the web app to be run from my Android phone.

## Robot Idea
I want to build a two-wheeled self-balancing robot that:
1. Uses the gyroscope of my Android phone for self-balancing;
2. Uses my Android phone's accelerometer to sense direction of motion;
3. Uses my Android phone's mic and voice recognition to detect voice commands (e.g. forward, backward, turn left, turn right) that tell it which direction to move in.

## Wheel and Servo Information
* The left wheel is plugged into Servo Slot 1. The right wheel is plugged into Servo Slot 2.
* The servos are MG90S micro-servos. They take ~200 ms to swing fully and have asymmetric travel (one direction goes further than the other). Plan for jitter. Their useful PWM range is 1000 to 2000, with 1500 = neutral / centred. Real motion often only happens in `1300–1700`; the extremes can stall.

## Web App Requirements
"Done" means a web page with the following requirements:
1. Detects sensor input (e.g. beta angle, gamma angle) from my Android phone.
2. Reads my phone's tilt (beta angle and gamma angle) in real time, and logs this data.
3. Detects voice input from the mic of my Android phone.
4. Reads my voice commands (e.g. Forward, Backward, Turn Left, Turn Right) to let me steer the robot.
    * The voice command "Forward" should make the robot move forward by 10 cm for 1s.
    * The voice command "Backward" should make the robot move backward by 10 cm for 1s.
    * The voice command "Turn Left" should make the robot turn 90 degrees to its left.
    * The voice command "Turn right" should make the robot turn 90 degrees to its right.
    * All directions and motions should be based on my phone's sensor readings. 
4. Displays the voice command that is detected and recognized from my phone's mic.
5. Uses my phone's tilt (beta angle and gamma angle), and calculates the Left and Right servo adjustments to attempt to balance the robot while letting me steer it with my voice.
6. Displays a live table with headers "Run Time (s)", "Front/Back Tilt (°) " , "Left/Right Tilt (°)", "Right Servo Adjustment (us)" and "Left Servo Adjustment (us)".
7. Displays a live graph that plots "Front/Back Tilt (°) " , "Left/Right Tilt (°)", "Right Servo Adjustment (us)" and "Left Servo Adjustment (us)" as separate lines against "Run Time (s)".
8. Has a START/STOP button to start or stop the run.
9. Must be able to display live on my phone, so that I can view the live commands and data from my phone while my phone is mounted on the robot.
