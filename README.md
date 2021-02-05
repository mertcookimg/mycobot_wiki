# mycobot_wiki

unofficial myCobot wiki
* official repositories
    * https://github.com/elephantrobotics/myCobot
    * https://github.com/elephantrobotics/myCobotROS
    * https://github.com/elephantrobotics/pymycobot

## Set Up 
### Qiita(Japanese)
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
## Slider Control
![slider1](https://user-images.githubusercontent.com/58113372/106373873-31c89900-63c1-11eb-972c-ec799337b928.png)


![slider2](https://user-images.githubusercontent.com/58113372/106373884-4e64d100-63c1-11eb-8dec-faafd47d2532.png)

### Run
```
sudo chmod 666 /dev/ttyUSB
roslaunch mycobot_control mycobot_slider_control.launch 
```

## Moveit
![moveit](https://user-images.githubusercontent.com/58113372/106903946-f40b9d80-673d-11eb-9303-1e4c55f885af.png)

![rqt_](https://user-images.githubusercontent.com/58113372/106903957-f66df780-673d-11eb-9693-461db503f767.png)

### Install
```
cd your_ws/src
git clone https://github.com/mertcookimg/mycobot_ros.git
git clone https://github.com/mertcookimg/mycobot_controller.git
catkin build
```

### Run
```
sudo chmod 666 /dev/ttyUSB
roslaunch mycobot_controller demo_mycobot.launch
```

## License
This repository is licensed under the MIT license, see [LICENSE](./LICENSE).  
Unless attributed otherwise, everything in this repository is licensed under the MIT license.
