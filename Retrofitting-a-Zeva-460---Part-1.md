This page it's on his very early stages. Please come back on some time.
You will see from description that retrofit that I have realized it's on his early stages but functional. Will follow some other parts that will enhance machine functionality.
I will try to describe it as general as possible to make this page a guideline for similar machine.

1. Get documentation on your machine  
For this I have subscribed to  https://ca.groups.yahoo.com/neo/groups/zevatech/info . In section files you will find documentation for Zeva PM460.

2. Identify motion control system and transmission type/raport  
Zeva uses 5 phase stepper motors for X and Y Axis. Those have 0,72 degrees per step. I have changed the original driver with newer ones that happens to have lower micro-stepping and require supply to 220v.(to do add details on those).   
On both axis are same number of teeth at pulleys (just on Y axis pulleys are wider but same no of teeth). Small pulley that is on motor shaft has 15 teeth. Big pulley has 36 teeth  and the pulley that drives the effective transmission belt has 20 teeth.   
Making a simple calculation results an equivalent stepper motor with 0.3 degrees per step.
Machine uses transmission belt with a pitch of 3mm HTD + 0.3 degrees per step results a 0.05 mm / step.
Drivers that I have now support large microstepping but I have used only 1/8 so results the smaller step of 0.00625
mm.  


3. Decide on your motion control  
I have chosen TinyG. There are few shortcomings with it. There are a very limited number of ports output or input. Also a member from Openpnp group told me that tinyg does not report back when finises a movement instruction and therefore dwell commands are not that efficient.  
I plan for next release to move on Smoothie. In the past I have made some pcb's for this and I have developed easy modules for it.

4. Add vision camera  
In this moment OpenPnP support only uplooking camera. Following some advices from liteplacer forum I have bought an Andonstar endoscope camera.  Generally has a good quality image and has a nice focus feature , however I am fully satisfied about this : if you move the cable that gets in, image will rotate and get out of focus.   
Good thing it's that camera comes as a simple replacement for machine existent "laser pointer".

![andonstar endoscope camera adaptor](https://plus.google.com/107318571191916561952/posts/1o2khV81xyJ)

![andonstar camera mounted on placement head](https://plus.google.com/107318571191916561952/posts/fz586b5sAUt)  

4. Integrate motion control with existing machine electronics  
I am talking here about movement signals, endstop optocouplers and drive signals for penumatic valves.