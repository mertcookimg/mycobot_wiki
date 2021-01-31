# mycobot_wiki

unofficial myCobot wiki
* official repositories
    * https://github.com/elephantrobotics/myCobot
    * https://github.com/elephantrobotics/myCobotROS
    * https://github.com/elephantrobotics/pymycobot

## Set Up (Japanese)
### Qiita
https://qiita.com/MeRT/items/435385753692d0cf3250

### Install

```
sudo apt install python-pip
pip install pymycobot --user
sudo apt install ros-melodic-serial
cd ~/catkin_ws/src
git clone https://github.com/elephantrobotics/myCobotROS.git
git clone https://github.com/mertcookimg/mycobot_ros.git
cd ~/catkin_ws
catkin build
```

### M5
```
cd /myCobot/Software/myCobot固件烧录器V1.3/ino
```

#### Head
```
~/.local/bin/esptool.py --port /dev/ttyUSB0 write_flash --flash_mode dio -z 0xe000 boot_app0.bin 0x1000 bootloader_qio_80m.bin 0x10000 AtomMain2.4.ino.bin 0x8000 AtomMain2.4.ino.partitions.bin
```

#### Base
```
~/.local/bin/esptool.py --chip esp32 --port /dev/ttyUSB0 write_flash --flash_mode dio -z 0xe000 boot_app0.bin 0x1000 bootloader_qio_80m.bin 0x10000 Transponder.ino.bin 0x8000 Transponder.ino.partitions.bin
```

### Slider Control
```
sudo chmod 666 /dev/ttyUSB
roslaunch mycobot_control mycobot_slider_control.launch 
```

## License
This repository is licensed under the MIT license, see [LICENSE](./LICENSE).  
Unless attributed otherwise, everything in this repository is licensed under the MIT license.
