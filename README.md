# pigropico
## PiGro for Raspberry Pi Pico / PicoW + Waveshare 3.5Inch Touch Display

![pigrosm](https://user-images.githubusercontent.com/26333559/196528851-25c66190-ff87-4bd0-a2b7-fbb32330b3c8.png)
## PiGro – horticulture easy

### news:
- GUI reworked
- pigsh bash script added (minicom , usb)
- network memory leak fixed (http server)
- virtual keyboard improved
- sensors: aht15 / hih71
- bug saving/loading rules

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
![edit48x48](https://github.com/dawigit/pigropico/assets/26333559/99a31cb2-b893-4f6f-82ef-8f8601b44901)   Rules

![wifidis48x48](https://github.com/dawigit/pigropico/assets/26333559/4d874c6d-2ed0-4b96-b20e-08a684f10ddc) ![wificon48x48](https://github.com/dawigit/pigropico/assets/26333559/a518f5b7-ea87-4a4e-8be6-e934ab4daa40) WiFi (not) connected


![configure48x48](https://github.com/dawigit/pigropico/assets/26333559/e3a5aab7-13dc-49c4-929a-2df01c2369fa) Configure

![rotate48x48](https://github.com/dawigit/pigropico/assets/26333559/0b4ef583-791b-4141-9388-43e726555af3) Rotate display

![save48x48](https://github.com/dawigit/pigropico/assets/26333559/7e8cbac0-a86e-43cb-8be9-88e274ca58e7) Save



PicoW:
- select WiFi network, enter credentials, CONNECT0, wait...
- after a successfull connection a 'SAVE0' button appears
- press it to save and restart PiGro
- PiGro web client should be available at 'http://pigropicow/' in your network


## images

##### Raspberry Pi Pico/PicoW    'pigropicow.uf2'


## 
