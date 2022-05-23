## Customised Fan Controller for Thinkbook 16p

**Huge thanks to markgoo for the original project [markgoo/Thinkbook14PAutoFanController](https://github.com/markgoo/Thinkbook14PAutoFanController)!**

All configurations which could be changed are stored in the file `FanViewSetting.cfg`.

To set the temperature of the sensor of which the fan is assigned to.

```
$9_A FAN1= #7	  	# Temperature of Sensor7, DTS_GPU
$9_B FAN2= #6	  	# Temperature of Sensor6, DTS_CPU
```

All lines beginning with $0 are for FAN1 (DTS_GPU), $2 for FAN2 (DTS_CPU).

Three parameters to prevent possible damages

```
$0_X AUTOCONTROL_CYCLE= #40;        		# An interval of 40 cycles (4 seconds) to detect current temperature
$0_Y SUDDENRAISE_Counter_CYCLE= #10;		# A temperature raise lasting for 10 cycles would trigger the switch to change the fan speed
$0_Z TEMPDIFF= #5;	                  	# A drop of 5 degrees would trigger the switch to change the fan speed
```

To assign exact fan speed for different temperatures
```
$0_5 MAX70= #0; 
$0_6 MAX65= #0;	  	# 65 degrees < temperature < 70 degrees, use original EC settings
$0_7 MAX60= #20;		# 60 degrees < temperature < 65 degrees, set speed as 2000 rpm
$0_8 MAX55= #15; 		
```

Press `Esc` to exit Fan Control.

[AlwaysUp](https://www.coretechnologies.com/products/AlwaysUp/) is recommended to run FanController as a Windows Service.
