# pigropico – PiGro for Raspberry Pi Pico

## Pico / PicoW (rp2040)
## Pico 2 (rp2350)
## Waveshare Pico-ResTouch-LCD-3.5

![pigrosm](https://user-images.githubusercontent.com/26333559/196528851-25c66190-ff87-4bd0-a2b7-fbb32330b3c8.png)
## PiGro – horticulture easy
![pigro](https://github.com/dawigit/pigropico/assets/26333559/90e35caf-ba92-40ad-8799-22c589a89b44)

### (Pico 2 only!)
![PiGro_pico2_https](https://github.com/user-attachments/assets/e29e8056-54bd-452e-b514-05cbfa885bdd)

### (Pico_w)
![PiGro_pico2_http](https://github.com/user-attachments/assets/1b9e97d7-aa93-4f07-9d29-a84e96e3db92)


### connect:
- connect the Pico to a Linux machine (USB) / serial port 
- in one terminal (ttyACM0 depending on Linux distribution)

  `minicom -o -D /dev/ttyACM0`

- in another terminal

  `pigsh 0`

- to connect via serial (/dev/ttyS0) 

  `spigsh 0` 
 
 
- to connect via web/api 

  `pigroshka 192.168.171.2` (Pico 2)

  `pigroshka YOUR-PIGRO-IP` (Pico W)


 remember to prepend 'set' in 'pigroshka'
 
  `set pwm0 10` 


  
### news:

- new icons in web ui from https://www.svgrepo.com/
- PiGro for Pico2 - pico2_pigropicow.uf2 (rp2350)
- Pico2 webserver (USB)
  `http://192.168.171.2`
  or
  `https://192.168.171.2`

- PiGro Pico2 no syslog, only fixed POSIX time string
  
- (non-range) time in rules: `time8`, `time2:12PM`, `time22` 

   `addrule time5 -> pwm1 60`

  will create a rule, executed once, at 5 (AM)

  `save` your rules when done

- remember: time values never contain a ' ' space character! 

  always: 'timeHH:MMxM-HH:MMxM'

  xM is AM/PM

  now, all except the first HH value can be omitted

- WiFi country code in status
- GUI reworked
- pigsh bash script added (minicom , usb)
- network memory leak fixed (http server)
- virtual keyboard improved
- sensors: aht15 / hih71
- editor fixed
- press 'Rules Selector' (text) to create a new (empty) rule

### new commands:

  `posixtime CEST-1CET,M3.5.0/2:00:00,M10.5.0/3:00:00` set the timestring (Pico2)

   defaults to 'Europe/Berlin'

   'tz_list' contains a list of names / posix time strings (pcodes)

    `grep Shanghai tz_list` -> `"Asia/Shanghai","CST-8"`

    `grep Belgrade tz_list` -> `"Europe/Belgrade","CET-1CEST,M3.5.0,M10.5.0/3"`

    `grep New_York tz_list` -> `"America/New_York","EST5EDT,M3.2.0,M11.1.0"`

    `grep Kamchatka tz_list` -> `"Asia/Kamchatka","<+12>-12"`

    to adjust your time to New York (in pigsh/spigsh) 

    `posixtime EST5EDT,M3.2.0,M11.1.0`

    then -> `save` to reset and save

  tz_list was generated with https://github.com/nayarsystems/posix_tz_db

  `syslog LALA` to write 'LALA' to the syslog server

  `set_country XX` set the wifi country code (to 'WORLDWIDE')

  (check the end of this document for the country codes)

  `liru` list rules (in RAM, `stat` shows the rules in 'SRAM')

  `crules` check / test all rules

  `crule 7` check / test rule number 7

  `hostname pigro` set hostname to 'pigro'

  `ssid0`/`cred0` set ssid and credentials (wifi)

  `ssid1`/`cred1` same but for second (alternate) network

  `stat_bu 3` print status for save backup slot #3 (0-31, rotating)



## PiGro Pico / PicoW / Pico2 gpio:

### I2C Pico / PicoW

`I2C_SDA 0`

`I2C_SCL 1`

### I2C Pico_2

`I2C_SDA 26`

`I2C_SCL 27`

### UART Pico_2

`UART TX 0`

`UART RX 1`

### PWM

`PWM_0 2`

`PWM_1 3`

`PWM_2 4`

`PWM_3 6`


to see the variant (rp2350/rp2040) and the pins you can use 'picotool'

`picotool info pigropicow.uf2` 



## flash

`sudo picotool load ./pigropicow.uf2 -x --bus 1 --address XX`

Or: just drag'n'drop pigropicow.uf2 / pico2_pigropicow.uf2 to your drive


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

##### Raspberry Pi Pico 2    'pico2_pigropicow.uf2'



## country codes (from the driver)
(from `pico/pico-sdk/lib/cyw43-driver/src/cyw43_country.h`)

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


## configure syslog remote logging:

-  create dir '/var/log/remote'and set owner/rights so it's accessible by syslog
-  ubuntu:
  ```
  sudo mkdir /var/log/remote
  sudo chown -R syslog:adm /var/log/remote
  sudo chmod 755 /var/log/remote
  ```
- install rsyslog `sudo apt install rsyslog`
  
- edit '/etc/rsyslog.conf' `sudo nano /etc/rsyslog.conf`

- enable tcp/udp logging by removing the prepending hashes '#' at module and input
```
# provides UDP syslog reception
module(load="imudp")
input(type="imudp" port="514")

# provides TCP syslog reception
module(load="imtcp")
input(type="imtcp" port="514")
```
-  copy this snippet to the end of your '/etc/rsyslog.conf'
  
  ```
  $template remote, "/var/log/remote/%HOSTNAME%.log"
  if ($fromhost-ip != "127.0.0.1" ) then -?remote\n
  & stop
  ```

- restart rsyslog `sudo systemctl restart rsyslog`
- and do a status check `sudo systemctl status rsyslog`
- in a terminal `tail -n50 -F /var/log/remote/pigropicow.log` (or whatever your hostname is)
  
