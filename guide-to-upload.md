## Guide for Uploading Firmware to Crypto Ticker

#### Setting Up the Environment
1. Install [Python](https://www.python.org/downloads/). To check if you already have Python type ```python --version```. Output will be ```Python 3.7.4```.
2. Install [esptool](https://pypi.org/project/esptool/) via pip.
3. Install [Coolterm](https://freeware.the-meiers.org/) for serial monitoring.

#### Firmware
* Get the required binaries.

#### Steps for Uploading the Firmware
1. Open the binaries folder into your command line.
2. Enter this command ``` esptool.py -b 115200 write_flash 0x1000 _boot_0x1000.bin 0x8000 partitions.bin 0x10000 firmware.bin ```
3. If you see ``` Connecting........_____....._____....._____....._```, then you have to make the ESP board into boot mode by holding down the ```boot``` button  then press ```reset``` button, unpress both simultaneously on the ESP board. This will start the uploading to device.
4. If everything correct you see ``` Uploading ``` otherwise start from step 2 again.
5. After uploading press ``` reset / EN ``` button on ESP32. It will reset the board.

#### Monitoring

1. Open Coolterm.
2. Go to Options, Select the correct ```COM Port``` for your serial device and set the baudrate to ``` 115200```. Apply settings.
3. Now click on Connect on the main screen of the coolterm. After connecting you will see device serial logs. If doesnt comes up try resetting the device or recheck the COM port and wiring.