# nuttx_stm32h743
nuttx for nucleo-h743

# clone
git clone https://github.com/huanglilong/nuttx_stm32h743

# install toolchain and stlink
1. toolchain: https://nuttx.apache.org/docs/latest/quickstart/install.html
2. stlink: https://github.com/stlink-org/stlink (version >= 1.7 for st-link v3)
3. sudo apt install screen

# check stlink
$ st-info --probe  
![st-info](https://user-images.githubusercontent.com/7278867/173167624-0a733c40-f3f0-47e3-a019-b4ee4bf0fa6f.png)

# build
$ cd nuttx_stm32h743/nuttx
$ ./tools/configure.sh -l nucleo-h743zi2:nsh
$ make -j8

# stlink write flash
$ st-flash write nuttx.bin 0x8000000

# using NSH
$ screen /dev/ttyACM0 115200 8N1
![nutt nsh](https://user-images.githubusercontent.com/7278867/173167551-ce07b037-ef3c-4b6b-9723-f29d6e3fdc61.png)
