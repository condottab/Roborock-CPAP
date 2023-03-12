# Roborock-CPAP
CPAP cooling system using a Roborock fan
![image](https://user-images.githubusercontent.com/121378039/209463936-7d26f6cb-ce1e-449f-b166-296438bd0f6a.png)

This repo contains all the data I have collected about wiring, controlling and powering the Roborock fan. If a connection and control method is not mentioned here, it is considered unsafe or has not been tested. As always, everything you do is at your own risk.

There are several types of these fans on the market from different manufacturers, qinatsu and nidec have been tested. At the moment only one type of fan is considered unsuitable for our purposes, the 5 pin 5.1kPA (or 5100) option from nidec, the others have been found to work. Chinese sellers often give them in terms of nominal pressure capacity, which probably has nothing to do with actual performance, but we can try to work out what to buy and what not to buy from these values. It has been found that the 2.5kPa option often means a Qinatsu fan, which heats less than a Nidec, but they both work fine. I also noticed that the high-pitched pwm noise was worse with the Qinatsu. If you're not using active fan cooling, it's a good idea to set the maximum fan speed to around 0.6-0.7 in the config. It will still provide plenty of airflow.

The connection is as follows:

PWM> HARDWARE PWM pin on a mainboard

VCC> 24v hotend output from the mainboard

GND> grounded pin of the hotend output prescribed as enable_pin: PIN in the fan config

FG> doesn't go anywhere yet, but you can tinker with it if you know what you doing

To get started you will need to make a small flyback protection board, which includes a 10k to pull down the fan's PWM pin. 

![image](https://user-images.githubusercontent.com/121378039/212881528-e3a47822-b2a8-45af-89c8-67fd5614f81f.png)
![image](https://user-images.githubusercontent.com/121378039/210138044-a70bc6b9-4392-419c-870f-718244075b98.png)
![image](https://user-images.githubusercontent.com/121378039/210138046-b8b343f4-3be0-4117-823e-cbe7fd5357e5.png)


You can also order this board to be produced for you, there is a gerber file for this.

![image](https://user-images.githubusercontent.com/121378039/210138049-28e98718-6d7b-4b56-9d2d-1a404a3319d2.png)
![image](https://user-images.githubusercontent.com/121378039/210138052-674a5870-b571-4153-86c7-2f3ba4e15904.png)


Many thanks to [stas2z](https://github.com/stas2z) for his expertise and work in researching various fans, putting together the protection schematics and providing the gerber. You are a legend and a guiding star.

BOM 

BZX55C5V1 x2

1N5819 x1 (x4 if you want to use three in parallel instead of one 1N5822)

1N5822 x1

CF2WS-1K x1

CF2WS-10K x1 (+1 if you want to use a grounded pin of the fan output for pwm)

PH 2.0 connector x1

Heat inserts m3x4.2x4 x5

M3x5 screws x5

The printed parts are in abs and tpu.

SMD BOM

MDD DSK24 x1

BZT52C5V1S x2

102 resistor x1

103 resistor x1

SS56F x 1

PH 2.0 connector x1

![image](https://user-images.githubusercontent.com/121378039/209482129-ca142f26-6aaa-42c2-b7cc-db964e90b7dd.png)
![image](https://user-images.githubusercontent.com/121378039/209482137-34fb8c10-3275-4c9c-b42b-c01cabe76723.png)
![image](https://user-images.githubusercontent.com/121378039/209482142-3b67b5ae-a99b-436a-9072-4c8cf7cfe082.png)

