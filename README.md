1. Development mode allows you to run the latest development version from this repository:

```
$ cd esptool
$ pip install --user -e .
```

2. If you are putting MicroPython on your board for the first time then you should first erase the entire flash using:

```
$ python3 esptool.py --chip esp32 --port /dev/ttyUSB0 erase_flash
```

3. Then, flash the firmware (.bin file) starting at address 0x1000:

```
$ python3 esptool.py --chip esp32 --port /dev/ttyUSB0 --baud 460800 write_flash -z 0x1000 esp32-idf3-20210202-v1.14.bin
```

4. Finally, we can communicate with our ESP32 board using serial connection (tio, putty, screen):
```
$ tio /dev/ttyUSB0
```
