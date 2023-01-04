# Roborock-CPAP
CPAP cooling system using a Roborock fan
![image](https://user-images.githubusercontent.com/121378039/209463936-7d26f6cb-ce1e-449f-b166-296438bd0f6a.png)

This repo contains all the data I have collected about the wiring, control and powering of the Roborock fan. If any connection and control method is not indicated here, it is considered unsafe or has not been tested. As always, everything you do is at your own risk.

There are several varieties of these fans on the market from different manufacturers, qinatsu and nidec have been tested. At the moment only one type of fan is considered unsuitable for our purposes, it is the 5.1kPA (or 5100) option from nidec, the others are found to be working. Chinese sellers often designate them in assumed pressure capacity, which probably has nothing to do with actual performance, but we can try to figure out what to buy and what not to from these values. It has been observed that the 2.5kPa option often means that it is a qinatsu fan, which is considered the most trouble free at the moment. The 2.0kPa version from nidec also works fine and you don't need to hunt those qinatsu. The only difference between them is nidec fails to start in the default connection and needs power switching along with the PWM supply, i.e. it needs to be powered from an extra hotend output with enable_pin prescribed in printer.cfg, while qinatsu should be powered directly from a 24V PSU. 

PWM>HARDWARE PWM pin on a mainboard
VCC>24v from psu if it's a qinatsu or 24v hotend output from the mainboard if it's a nidec
GND> psu ground if it's a qinatsu or grounded pin of the hotend output prescribed as enable_pin: PIN in the fan config if it's a nidec
FG> doesn't go anywhere yet, but you can tinker with it if you know what you doing

To get started you will need to make a small flyback protection board, which includes a 10k to pull down the fan's PWM pin. 

![image](https://user-images.githubusercontent.com/121378039/209463332-eb5e78bd-5d68-430a-9899-52e133a1f721.png)
![image](https://user-images.githubusercontent.com/121378039/210138044-a70bc6b9-4392-419c-870f-718244075b98.png)
![image](https://user-images.githubusercontent.com/121378039/210138046-b8b343f4-3be0-4117-823e-cbe7fd5357e5.png)


You can also order this board to be produced for you, there is a gerber file for this.

![image](https://user-images.githubusercontent.com/121378039/210138049-28e98718-6d7b-4b56-9d2d-1a404a3319d2.png)
![image](https://user-images.githubusercontent.com/121378039/210138052-674a5870-b571-4153-86c7-2f3ba4e15904.png)


Many thanks to [stas2z](https://github.com/stas2z) for the expertise and work done on researching different fans, for putting together the protection schematics and the gerber provided. You are a legend and a guiding star.

BOM 

BZX55C5V1 x2

1N5819 x1

CF2WS-1K x1

CF2WS-10K x1 (+1 if you want to use a grounded pin of the fan output for pwm)

PH 2.0 connector x1

Heat inserts m3x4.2x4 x5

M3x5 screws x5

The printed parts are in abs and tpu.

![image](https://user-images.githubusercontent.com/121378039/209482129-ca142f26-6aaa-42c2-b7cc-db964e90b7dd.png)
![image](https://user-images.githubusercontent.com/121378039/209482137-34fb8c10-3275-4c9c-b42b-c01cabe76723.png)
![image](https://user-images.githubusercontent.com/121378039/209482142-3b67b5ae-a99b-436a-9072-4c8cf7cfe082.png)

