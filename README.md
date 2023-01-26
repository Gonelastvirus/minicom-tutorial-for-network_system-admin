# minicom-tutorial-for-network-system-admin
![cable-consola-cisco-db9-to-rj45-console-cable-serial-celeste-D_NQ_NP_691305-MPE20857480112_082016-F](https://user-images.githubusercontent.com/67478827/214913784-80807f29-9856-40f9-a4e5-eedc4c56b285.jpg)

Minicom is a terminal emulator program that is commonly used by network administrators to configure and manage network devices such as routers, switches, and servers.

**Here are some ways in which network administrators use minicom:**
- Accessing the command-line interface (CLI) of network devices: Minicom can be used to connect to the CLI of a network device through a console cable, allowing network administrators to enter commands and configure the device.

- Troubleshooting network issues: Minicom can be used to remotely access a network device and view system logs, error messages, and other diagnostic information that can be used to troubleshoot network issues.

- Upgrading firmware: Network administrators can use minicom to upload new firmware to a device and perform firmware upgrades.

- Saving and restoring configuration: Minicom can be used to save the current configuration of a network device to a file, and then restore that configuration to the device at a later time.

- Automating tasks: Network administrators can use minicom in combination with scripting languages such as Python or Bash to automate repetitive tasks, such as configuring multiple devices with the same settings.

_Note: Minicom is just one tool among many that Network administrator can use, and it might not be the best or the only option depending on the device or the task at hand._

## To use minicom to connect to the CLI of a network device through a console cable, network administrators can follow these steps:

- Connect the console cable to the serial port of the network device and the appropriate port on the computer.

- Open a terminal window on the computer and enter the command "minicom -s" to open the minicom setup menu.

![Screenshot from 2023-01-26 22-58-38](https://user-images.githubusercontent.com/67478827/214904348-1e629804-11d3-4eef-9f6f-ba49b49f0ebc.png)

- In the setup menu, go to the "Serial port setup" option and configure the serial port settings to match the settings of the network device. This may include the baud rate, data bits, stop bits, and parity. You can check the documentation of the device to see which settings are needed.

![Screenshot from 2023-01-26 22-59-13](https://user-images.githubusercontent.com/67478827/214904241-f9b39c6c-c581-43c9-8317-319cef6597ae.png)

- press A to enter into serial port option. Save the settings and exit the setup menu.

![Screenshot from 2023-01-26 23-06-00](https://user-images.githubusercontent.com/67478827/214905101-e8c47aa3-0144-4d3a-9eab-10793babcf14.png)

- You should now be in the minicom terminal window, you will be connected to the device's command-line interface. You can now enter commands to configure the device.

![Screenshot from 2023-01-26 23-07-46](https://user-images.githubusercontent.com/67478827/214905324-ab1fdb36-6933-432e-bc17-fdaa5f57572d.png)
  
## Minicom can be used to save the current configuration of a network device to a file
Minicom allows you to store and recall configuration files in a quite handy way.

When started without options then it looks for the default configuration files
```
/etc/minicom/minirc.dfl or ~/.minirc.dfl
```
These files can be easily created by starting minicom in setup mode
```
minicom -s or sudo minicom -s
```
and after having configured what you need, selecting the option “save setup as dfl”.

![minicom-save-setup](https://user-images.githubusercontent.com/67478827/214909307-b09f30bd-3549-4819-9c50-f857e960a82e.png)

If you are root then the configuration will be saved into /etc/minicom/minirc.dfl,
otherwise into your home directory into .minirc.dfl .

Interesting is the possibility to save named custom configurations.
If you are root and you select the option “save setup as..” then you will be able to save a named custom configuration

![minicom-save-setup](https://user-images.githubusercontent.com/67478827/214909578-0feb7c03-9fe9-405e-8c6c-d8c1e1363c4c.png)

The configuration file will be saved into the directory /etc/minicom as minirc.<name> (e.g.: minirc.alix) and can be easily recalled by invoking minicom followed by the name you gave the configuration

e.g:
```
minicom alix
```
will start minicom with the configuration stored into the file /etc/minicom/minirc.alix


BTW, here are the settings I’m using to connect to the alix board:
```
pu port             /dev/ttyS0
pu baudrate         38400
pu rtscts           No 
pu xonxoff          Yes
```
