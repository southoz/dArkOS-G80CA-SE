# dArkOS-G80CA

## Working 
- Screen
- Wifi to Mobile
- Wifi to Infrastructure (Says it's failed, but has an IP when enabling remote services).
- Joystick 


## Issues - 
- No Sound
- LED when on Battery.
- Battery Indicator in Emulation Station
- Joystick Axis Mapping



## Keys

| SDL Index / Axis     | G80CA-MB Mapping            | GO-Super Gamepad Mapping     |
|----------------------|-----------------------------|------------------------------|
| 1                    | A Button (Right)            | a:b1                         |
| 0                    | B Button (Bottom)           | b:b0                         |
| 2                    | X Button (Top)              | x:b2                         |
| 3                    | Y Button (Left)             | y:b3                         |
| 4                    | L1 Button                   | leftshoulder:b4              |
| 5                    | R1 Button                   | rightshoulder:b5             |
| 6                    | L2 Button                   | lefttrigger:b6               |
| 7                    | R2 Button                   | righttrigger:b7              |
| 14                   | L3 Button                   | leftstick:b14                |
| 15                   | R3 Button                   | rightstick:b17               |
| 8                    | D-Pad Up                    | dpup:b8                      |
| 9                    | D-Pad Down                  | dpdown:b9                    |
| 10                   | D-Pad Left                  | dpleft:b10                   |
| 11                   | D-Pad Right                 | dpright:b11                  |
| 12                   | Start Button                | start:b13                    |
| 13                   | Select Button               | back:b12                     |
| 16                   | Function Button             | guide:b16                    |
| Axis 2+              | Left Analogue Up            | lefty:a1  (negative = up)    |
| Axis 2-              | Left Analogue Down          | lefty:a1  (positive = down)  |
| Axis 3+              | Left Analogue Left          | leftx:a0  (negative = left)  |
| Axis 3-              | Left Analogue Right         | leftx:a0  (positive = right) |
| Axis 0+              | Right Analogue Up           | righty:a3 (negative = up)    |
| Axis 0-              | Right Analogue Down         | righty:a3 (positive = down)  |
| Axis 1-              | Right Analogue Left         | rightx:a2 (negative = left)  |
| Axis 1-              | Right Analogue Right        | rightx:a2 (positive = right) |


Key Differences Summary:

- Face buttons are swapped in order (typical Japanese vs. Western/Xbox layout):
   - G80CA-MB: 1=A(Circle), 0=B(Cross), 2=X, 3=Y
   - GO-Super: 2=X, 1=A, 0=B, 3=Y

- Right stick click → G80CA uses 15 (standard R3), GO-Super uses 17 (uncommon)
- Select/Start are slightly swapped in assignment (back vs start)
- Axes are inverted in labeling: G80CA uses Axis 2/3 for left stick, Axis 0/1 for right — GO-Super uses the more common Axis 0/1 left, Axis 2/3 right

