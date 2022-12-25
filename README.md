# Roborock-CPAP
CPAP cooling system using a Roborock fan
![image](https://user-images.githubusercontent.com/121378039/209463936-7d26f6cb-ce1e-449f-b166-296438bd0f6a.png)

This repo contains all the data I have collected about the wiring, control and powering of the Roborock fan. If any connection and control method is not indicated here, it is considered unsafe or has not been tested. As always, everything you do is at your own risk.

There are several varieties of these fans on the market from different manufacturers, qinatsu and nidec have been tested. At the moment only one type of fan is considered unsuitable for our purposes, it is the 51kPA (or 51000) option from nidec, the others are found to be working. Chinese sellers often designate them in assumed pressure capacity, which probably has nothing to do with actual performance, but we can try to figure out what to buy and what not to from these values. It has been observed that the 25kPa option often means that it is a qinatsu fan, which is considered the most trouble free at the moment. The 20kPa version from nidec also works fine, but needs PWM to work. A black case fan from nidec has also been tested, though it fails to start in the default connection and needs power switching along with the PWM supply, i.e. it needs to be powered from an extra hotend output with enable_pin prescribed in printer.cfg, for the rest of the fans tested it can be powered directly from a 24V PSU.

To get started you will need to make a small flyback protection board, which includes a 10k to pull down the fan's PWM pin. 

![image](https://user-images.githubusercontent.com/121378039/209463332-eb5e78bd-5d68-430a-9899-52e133a1f721.png)

You can also order this board to be produced for you, there is a gerber file for this.

Many thanks to [stas2z](https://github.com/stas2z) for the expertise and work done on researching different fans, for putting together the protection schematics and the gerber provided. You are a legend and a guiding star.
