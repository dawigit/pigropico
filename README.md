# pigropico
## PiGro for Raspberry Pi Pico / PicoW + Waveshare 3.5Inch Touch Display

![pigrosm](https://user-images.githubusercontent.com/26333559/196528851-25c66190-ff87-4bd0-a2b7-fbb32330b3c8.png)
## PiGro – horticulture easy

### news:
- bug with timezone/hour fixed
- shell script 'pigroshka' added so you can send commands ('set pwm1 40') via shell to the webserver [http://pigropico]
- crc for rules added
- improved save/flash handling


## PiGro Pico / PicoW gpio:

### I2C

`I2C_SDA 0`
`I2C_SCL 1`

### PWM

`PWM_0 2`
`PWM_1 3`
`PWM_2 4`
`PWM_3 6`

## flash

`sudo picotool load ./pigropicow.uf2 -x --bus 1 --address XX`


## usage
![rules24](https://user-images.githubusercontent.com/26333559/196623838-79510492-9aed-47b7-8bc6-7f2174fc1dc5.png)   RULES

![config24](https://user-images.githubusercontent.com/26333559/196618347-d1fb8203-2787-4cb0-9d42-3082fc6b0d8a.png)  CREDENTIALS WIFI (Keyboard)

![wifi24](https://user-images.githubusercontent.com/26333559/196618425-79aa8630-4e85-4013-9fb9-c2c08f3f62f6.png)    WIFI SELECT

![clock24](https://user-images.githubusercontent.com/26333559/196618606-2ed1dd2b-7a65-4846-8d4d-a4f574acbfb3.png)   TIME (Timezone, 12H/24H)

![tools24](https://user-images.githubusercontent.com/26333559/196619398-d48b66ca-5b77-4566-a103-9defaa326fe3.png)   no use atm


![config24](https://user-images.githubusercontent.com/26333559/196618347-d1fb8203-2787-4cb0-9d42-3082fc6b0d8a.png)  ROTATE180 (SCREEN)

![ok24](https://user-images.githubusercontent.com/26333559/196619621-8e86941a-4fa2-409e-bc22-eb723be753df.png)      WIFI0/WIFI1 SWITCH

![save24](https://user-images.githubusercontent.com/26333559/196619801-8ce61b2a-6ac1-454f-8bb2-6046b4706e65.png)    SAVE



- PiGro web client at 'http://pigropicow/' in your network

- Switch back to PWM control by selecting the same icon again. So from 'RULES' to 'PWM' just press 'RULES' again

## images

##### Raspberry Pi Pico/W     'pigropicow.uf2'


## 
