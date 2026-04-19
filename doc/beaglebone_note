# BeagleBone How to Boot from

* load the linux image to the DDR memory from MMC 0 (SD Card)

  ```
  load mmc 0:2 0x82000000 /boot/uImage
  ```

* load the dtb image to the DDR memory from MMC 0 (SD Card)

  ```
  load mmc 0:2 0x88000000 /boot/am335x-boneblack.dtb
  ```

* add the bootargs on the uBoot

  ```
  setenv bootargs 'console=ttyO0,115200 root=/dev/mmcblk0p2 rw'
  ```

* boot from memory

  ```
  bootm 0x82000000 - 0x88000000
  ```



# modify uEnv.txt

* use the minicome send uEnv.txt to BBB via XMODEM

* command to import enviables from memory address

  ```
  env import -t <memory addr> <size in bytes>
  ```

  

# how to boot BeagleBone Black from Uart

* remove SD Card from BBB , press boot button(S2) , Power ON

* the console will be show "CCCC......."

* use X-MODEM send u-boot-spl.bin file to BBB

* use X-MODEM send u-boot.img to BBB  

  * and press space key into the U-BOOT interface

* send uImage file to 0x82000000 via X-MODEM

  ```
  loadx 0x82000000
  ```

* send dtb file am335x-boneblack.dtb at 0x88000000 via X-MODEM

  ```
  0x88000000
  ```

* send ram disk image file initramfs at 0x88080000 via X-MODEM

  ```
  loadx 0x88080000
  ```

* set bootargs

  ```
  setenv bootargs console=ttyO0,115200 root=/dev/ram0 rw initrd=0x88080000
  ```

* boot from DDR RAM

  ```
  bootm {kernel addr} {initramfs addr} {dtb_load_addr}
  ```
  
  
  
  ```
  bootm 0x82000000 0x88080000 0x88000000
  ```




# How to boot BBB from TFTP Server

* goto to U-Boot interface

* set the server ip

  ```
  setenv serverip 192.168.1.107
  ```

* set the client ip

  ```
  setenv ipaddr 192.168.1.109
  ```

* testing the networking connect

  ```
  ping 192.168.1.107
  ```

* load uImage from tftp

  ```
  tftpboot 0x82000000 uImage
  ```

* load am335x-boneblack.dtb from tftp

  ```
  tftpboot 0x88000000 am335x-boneblack.dtb
  ```

* load ram disk (RootFileSystem) from tftp

  ```
  tftpboot 0x88080000 initramfs
  ```

* set boot args

  ```
  setenv bootargs console=ttyO0,115200 root=/dev/ram0 rw initrd=0x88080000
  ```

* boot from DDR memory

  ```
  bootm 0x82000000 0x88080000 0x88000000
  ```

  

# LEDs

| LED  | GPIO SIGNAL | PROC PIN |
| :--: | :---------: | :------: |
| USR0 |  GPIO_1_21  |   V15    |
| USR1 |  GPIO_2_22  |   U15    |
| USR2 |  GPIO_2_23  |   T15    |
| USR3 |  GPIO_2_24  |   V16    |

