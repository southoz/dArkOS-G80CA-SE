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
- Select/Start are slightly swapped in the assignment (back vs start)
- Axes are inverted in labeling: G80CA uses Axis 2/3 for left stick, Axis 0/1 for right — GO-Super uses the more common Axis 0/1 left, Axis 2/3 right

The kernel is ignoring any changes to amux-channel-mapping and appears to have hardcoded values in the driver.

```
ark@rg351mp:~$ dmesg | grep -i joypad
[    3.339205] odroidgo3_joypad odroidgo3-joypad: joypad_dt_parse : invert-absx = 1, inveret-absy = 1, invert-absrx = 0, inveret-absry = 0, turn-absr = 0
[    3.339292] of_get_named_gpiod_flags: parsed 'amux-a-gpios' property of node '/odroidgo3-joypad[0]' - status (0)
[    3.339335] of_get_named_gpiod_flags: parsed 'amux-b-gpios' property of node '/odroidgo3-joypad[0]' - status (0)
[    3.339365] of_get_named_gpiod_flags: parsed 'amux-en-gpios' property of node '/odroidgo3-joypad[0]' - status (0)
[    3.339397] of_get_named_gpiod_flags: parsed 'gpios' property of node '/odroidgo3-joypad/sw1[0]' - status (0)
[    3.339428] of_get_named_gpiod_flags: parsed 'gpios' property of node '/odroidgo3-joypad/sw2[0]' - status (0)
[    3.339456] of_get_named_gpiod_flags: parsed 'gpios' property of node '/odroidgo3-joypad/sw3[0]' - status (0)
[    3.339484] of_get_named_gpiod_flags: parsed 'gpios' property of node '/odroidgo3-joypad/sw4[0]' - status (0)
[    3.339511] of_get_named_gpiod_flags: parsed 'gpios' property of node '/odroidgo3-joypad/sw5[0]' - status (0)
[    3.339538] of_get_named_gpiod_flags: parsed 'gpios' property of node '/odroidgo3-joypad/sw6[0]' - status (0)
[    3.339565] of_get_named_gpiod_flags: parsed 'gpios' property of node '/odroidgo3-joypad/sw7[0]' - status (0)
[    3.339593] of_get_named_gpiod_flags: parsed 'gpios' property of node '/odroidgo3-joypad/sw8[0]' - status (0)
[    3.339620] of_get_named_gpiod_flags: parsed 'gpios' property of node '/odroidgo3-joypad/sw11[0]' - status (0)
[    3.339647] of_get_named_gpiod_flags: parsed 'gpios' property of node '/odroidgo3-joypad/sw12[0]' - status (0)
[    3.339674] of_get_named_gpiod_flags: parsed 'gpios' property of node '/odroidgo3-joypad/sw13[0]' - status (0)
[    3.339702] of_get_named_gpiod_flags: parsed 'gpios' property of node '/odroidgo3-joypad/sw15[0]' - status (0)
[    3.339730] of_get_named_gpiod_flags: parsed 'gpios' property of node '/odroidgo3-joypad/sw16[0]' - status (0)
[    3.339758] of_get_named_gpiod_flags: parsed 'gpios' property of node '/odroidgo3-joypad/sw19[0]' - status (0)
[    3.339785] of_get_named_gpiod_flags: parsed 'gpios' property of node '/odroidgo3-joypad/sw20[0]' - status (0)
[    3.339812] of_get_named_gpiod_flags: parsed 'gpios' property of node '/odroidgo3-joypad/sw21[0]' - status (0)
[    3.339840] of_get_named_gpiod_flags: parsed 'gpios' property of node '/odroidgo3-joypad/sw22[0]' - status (0)
[    3.339861] odroidgo3_joypad odroidgo3-joypad: joypad_dt_parse : adc key cnt = 4, gpio key cnt = 17
[    3.339924] odroidgo3_joypad odroidgo3-joypad: joypad_input_setup : SCALE = 2, ABS min = -1800, max = 1800, fuzz = 32, flat = 32, deadzone = 64
[    3.339936] odroidgo3_joypad odroidgo3-joypad: joypad_input_setup : adc tuning_p = 200, adc_tuning_n = 200
[    3.339949] odroidgo3_joypad odroidgo3-joypad: joypad_input_setup : SCALE = 2, ABS min = -1800, max = 1800, fuzz = 32, flat = 32, deadzone = 64
[    3.339959] odroidgo3_joypad odroidgo3-joypad: joypad_input_setup : adc tuning_p = 200, adc_tuning_n = 200
[    3.339973] odroidgo3_joypad odroidgo3-joypad: joypad_input_setup : SCALE = 2, ABS min = -1800, max = 1800, fuzz = 32, flat = 32, deadzone = 64
[    3.339983] odroidgo3_joypad odroidgo3-joypad: joypad_input_setup : adc tuning_p = 200, adc_tuning_n = 200
[    3.339996] odroidgo3_joypad odroidgo3-joypad: joypad_input_setup : SCALE = 2, ABS min = -1800, max = 1800, fuzz = 32, flat = 32, deadzone = 64
[    3.340007] odroidgo3_joypad odroidgo3-joypad: joypad_input_setup : adc tuning_p = 200, adc_tuning_n = 200
[    3.340019] odroidgo3_joypad odroidgo3-joypad: Boost = 0, 0
[    3.340231] input: GO-Super Gamepad as /devices/platform/odroidgo3-joypad/input/input2
[    3.340793] odroidgo3_joypad odroidgo3-joypad: joypad_open : adc[0] adc->cal = 1810
[    3.340927] odroidgo3_joypad odroidgo3-joypad: joypad_open : adc[1] adc->cal = 1782
[    3.341043] odroidgo3_joypad odroidgo3-joypad: joypad_open : adc[2] adc->cal = 1788
[    3.341160] odroidgo3_joypad odroidgo3-joypad: joypad_open : adc[3] adc->cal = 1802
[    3.341741] odroidgo3_joypad odroidgo3-joypad: joypad_open : opened
[    3.342150] odroidgo3_joypad odroidgo3-joypad: rumble setup success!
[    3.342162] odroidgo3_joypad odroidgo3-joypad: joypad_probe : probe success
ark@rg351mp:~$ dmesg | grep -i adc
[    2.704125] rockchip-thermal ff280000.tsadc: Missing tshut mode property, using default (cru)
[    2.704158] rockchip-thermal ff280000.tsadc: Missing tshut-polarity property, using default (low)
[    2.704325] rk_tsadcv2_temp_to_code: Invalid conversion table: code=4095, temperature=2147483647
[    2.704850] rockchip-thermal ff280000.tsadc: tsadc is probed successfully!
[    2.802357] rockchip-saradc ff288000.saradc: Looking up vref-supply from device tree
[    3.339861] odroidgo3_joypad odroidgo3-joypad: joypad_dt_parse : adc key cnt = 4, gpio key cnt = 17
[    3.339936] odroidgo3_joypad odroidgo3-joypad: joypad_input_setup : adc tuning_p = 200, adc_tuning_n = 200
[    3.339959] odroidgo3_joypad odroidgo3-joypad: joypad_input_setup : adc tuning_p = 200, adc_tuning_n = 200
[    3.339983] odroidgo3_joypad odroidgo3-joypad: joypad_input_setup : adc tuning_p = 200, adc_tuning_n = 200
[    3.340007] odroidgo3_joypad odroidgo3-joypad: joypad_input_setup : adc tuning_p = 200, adc_tuning_n = 200
[    3.340793] odroidgo3_joypad odroidgo3-joypad: joypad_open : adc[0] adc->cal = 1810
[    3.340927] odroidgo3_joypad odroidgo3-joypad: joypad_open : adc[1] adc->cal = 1782
[    3.341043] odroidgo3_joypad odroidgo3-joypad: joypad_open : adc[2] adc->cal = 1788
[    3.341160] odroidgo3_joypad odroidgo3-joypad: joypad_open : adc[3] adc->cal = 1802
ark@rg351mp:~$ dmesg | grep -i amux
[    3.339292] of_get_named_gpiod_flags: parsed 'amux-a-gpios' property of node '/odroidgo3-joypad[0]' - status (0)
[    3.339335] of_get_named_gpiod_flags: parsed 'amux-b-gpios' property of node '/odroidgo3-joypad[0]' - status (0)
[    3.339365] of_get_named_gpiod_flags: parsed 'amux-en-gpios' property of node '/odroidgo3-joypad[0]' - status (0)
```

