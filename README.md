# nuttx_stm32h743
nuttx for nucleo-h743

# clone
git clone https://github.com/huanglilong/nuttx_stm32h743

# install toolchain and stlink
1. toolchain: https://nuttx.apache.org/docs/latest/quickstart/install.html
2. stlink: https://github.com/stlink-org/stlink (version >= 1.7 for st-link v3)
3. sudo apt install screen

# check stlink
# st-info --probe  
Failed to parse flash type or unrecognized flash type
Found 1 stlink programmers
  version:    V3J5
  serial:     001700264D46501120383832
  flash:      2097152 (pagesize: 131072)
  sram:       131072
  chipid:     0x450
  dev-type:   STM32H74x_H75x

# build
$ cd nuttx_stm32h743/nuttx
$ ./tools/configure.sh -l nucleo-h743zi2:nsh
$ make -j8

# stlink write flash
$ st-flash write nuttx.bin 0x8000000

# using NSH
$ screen /dev/ttyACM0 115200 8N1
![nutt nsh](https://user-images.githubusercontent.com/7278867/173167551-ce07b037-ef3c-4b6b-9723-f29d6e3fdc61.png)
