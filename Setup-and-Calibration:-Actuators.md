# Actuators
Actuators are generic devices you can attach to your machine to do additional tasks not covered by Nozzles and Cameras. For instance, you can use a solenoid with a pin attached to the head to drag a tape forward to feed it. You can also use Actuators to read values from sensors attached to the machine.

Some of the things OpenPnP uses Actuators for are:

* [[Nozzle valve and vacuum pump control.|Setup and Calibration: Vacuum Setup]]
* [Auto feeder triggers](https://github.com/openpnp/openpnp/wiki/ReferenceAutoFeeder).
* [[Nozzle vacuum pressure sensing|Setup and Calibration: Vacuum Sensing]].
* Drag feeder solenoid pins.
* [Camera lighting control](https://github.com/openpnp/openpnp/wiki/Camera-Lighting-Control).

Using the [[Scripting]] system you can use Actuators to extend OpenPnP to control a wide array of devices and sensors.

## Adding Actuators
1. Open the Machine Setup tab.
2. 
    * If you are adding a head mounted actuator, find the head in the tree on the left. Under the head look for Actuators and select it. Head mounted actuators are often attached to devices such as drag feed solenoids and nozzle change tools.
    * If you are adding a machine mounted actuator, find Actuators under the root of the tree and select it. Machine mounted actuators can be used for things like conveyors and lighting.
3. Add an actuator by pressing the green plus button ![](https://rawgit.com/openpnp/openpnp/develop/src/main/resources/icons/general-add.svg).  
2. Select a actuator driver from the provided list and press the "Accept" button. The newly added actuator will show up in the actuators list.
3. Click on the name of the new actuator to open it's properties.

## Assigning Commands

Once you've created an Actuator, you will generally need to assign commands to it. The most common case is using GcodeDriver and boolean actuators to control something like a switch, a solenoid, a pump, a valve, etc. 

To set the Gcode for an Actuator:
1. Go to Machine Setup -> Driver -> GcodeDriver -> Gcode. 
2. Select the Actuator from the dropdown menu.
3. Select the ACTUATE_BOOLEAN command.
4. Enter the Gcode fragment. An example would be `{True:M801}{False:M800}`. This will send M801 when the Actuator is turned on, and M800 when it is turned off.

# GcodeDriver

See [actuate-boolean-command](https://github.com/openpnp/openpnp/wiki/GcodeDriver%3A-Command-Reference#actuate_boolean_command)

See [actuate-double-command](https://github.com/openpnp/openpnp/wiki/GcodeDriver%3A-Command-Reference#actuate_double_command)

See [actuator-read-command](https://github.com/openpnp/openpnp/wiki/GcodeDriver%3A-Command-Reference#actuator_read_command)

See [actuator-read-regex](https://github.com/openpnp/openpnp/wiki/GcodeDriver#actuator_read_regex)

## Head Offsets
See [Setting Head Offsets](https://github.com/openpnp/openpnp/wiki/Setup-and-Calibration%3A-Nozzle-Setup#head-offsets) for the general process. It is basically the same for Actuators.

***

| Previous Step                 | Jump To                 | Next Step                                   |
| ----------------------------- | ----------------------- | ------------------------------------------- |
| [Nozzle Setup](https://github.com/openpnp/openpnp/wiki/Setup-and-Calibration%3A-Nozzle-Setup)  | [Table of Contents](https://github.com/openpnp/openpnp/wiki/Setup-and-Calibration) | [Vacuum Setup](https://github.com/openpnp/openpnp/wiki/Setup-and-Calibration%3A-Vacuum-Setup) |