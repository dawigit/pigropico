# pigropico – PiGro for Raspberry Pi Pico

## Pi Pico / PicoW (rp2040)
## Pico2 (rp2350)
## Waveshare Pico-ResTouch-LCD-3.5

![pigrosm](https://user-images.githubusercontent.com/26333559/196528851-25c66190-ff87-4bd0-a2b7-fbb32330b3c8.png)
## PiGro – horticulture easy
![pigro](https://github.com/dawigit/pigropico/assets/26333559/90e35caf-ba92-40ad-8799-22c589a89b44)

### connect:
- connect the Pico to a Linux machine (USB) / serial port 
- in one terminal (ttyACM0 depending on Linux distribution)

  `minicom -o -D /dev/ttyACM0`

- in another terminal

  `pigsh 0`

- to connect via serial (/dev/ttyS0) 

  `spigsh 0` 
 
 
- to connect via web/api

  `pigroshka 192.168.171.2` 

 remember to prepend 'set' in 'pigroshka'
 
  `set pwm0 10` 
  
### news:

- PiGro for Pico2 - pico2_pigropicow.uf2 (rp2350)
- Pico2 webserver (USB)
  `http://192.168.171.2`
  
  

- (non-range) time in rules: `time8`, `time2:12PM`, `time22` 

   `addrule time5 -> pwm1 60`

  will create a rule, executed once, at 5 (AM)

  `save` your rules when done


- remember: time values never contain a ' ' space character! 

  always: 'timeHH:MMxM-HH:MMxM'

  xM is AM/PM

  now, all except the first HH value can be omitted


- new commands:

  `posixtime TIMESTRING` set the timestring ("CEST-1CET,M3.5.0/2:00:00,M10.5.0/3:00:00")

   defaults to 'Europe/Berlin'

   "EST5EDT4,M3.2.0/02:00,M11.1.0/02:00" 'America/New York'
  
  `set_country XX` set the wifi country code (to 'WORLDWIDE')

  (check the end of this document for the country codes)

  `liru` list rules (in RAM, `stat` shows the rules in 'SRAM')

  `crules` check / test all rules

  `crule 7` check / test rule number 7

  `hostname pigro` set hostname to 'pigro'

  `ssid0`/`cred0` set ssid and credentials (wifi)

  `ssid1`/`cred1` same but for second (alternate) network

  `stat_bu 3` print status for save backup slot #3 (0-31, rotating)

- wifi country code in status
- GUI reworked
- pigsh bash script added (minicom , usb)
- network memory leak fixed (http server)
- virtual keyboard improved
- sensors: aht15 / hih71
- editor fixed
- press 'Rules Selector' (text) to create a new (empty) rule


## PiGro Pico / PicoW / Pico2 gpio:

### I2C Pico/Pico_w

`I2C_SDA 0`

`I2C_SCL 1`

### I2C Pico_2

`UART TX 0`

`UART RX 1`

`I2C_SDA 26`

`I2C_SCL 27`



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

##### Raspberry Pi Pico2    'pico2_pigropicow.uf2'



## country codes (from the driver)
(from `pico/pico-sdk/lib/cyw43-driver/src/cyw43_country.h`)
####  Worldwide Locale (passive Ch12-14)
WORLDWIDE         ('XX')
AUSTRALIA         ('AU')
AUSTRIA           ('AT')
BELGIUM           ('BE')
BRAZIL            ('BR')
CANADA            ('CA')
CHILE             ('CL')
CHINA             ('CN')
COLOMBIA          ('CO')
CZECH_REPUBLIC    ('CZ')
DENMARK           ('DK')
ESTONIA           ('EE')
FINLAND           ('FI')
FRANCE            ('FR')
GERMANY           ('DE')
GREECE            ('GR')
HONG_KONG         ('HK')
HUNGARY           ('HU')
ICELAND           ('IS')
INDIA             ('IN')
ISRAEL            ('IL')
ITALY             ('IT')
JAPAN             ('JP')
KENYA             ('KE')
LATVIA            ('LV')
LIECHTENSTEIN     ('LI')
LITHUANIA         ('LT')
LUXEMBOURG        ('LU')
MALAYSIA          ('MY')
MALTA             ('MT')
MEXICO            ('MX')
NETHERLANDS       ('NL')
NEW_ZEALAND       ('NZ')
NIGERIA           ('NG')
NORWAY            ('NO')
PERU              ('PE')
PHILIPPINES       ('PH')
POLAND            ('PL')
PORTUGAL          ('PT')
SINGAPORE         ('SG')
SLOVAKIA          ('SK')
SLOVENIA          ('SI')
SOUTH_AFRICA      ('ZA')
SOUTH_KOREA       ('KR')
SPAIN             ('ES')
SWEDEN            ('SE')
SWITZERLAND       ('CH')
TAIWAN            ('TW')
THAILAND          ('TH')
TURKEY            ('TR')
UK                ('GB')
USA               ('US')

