# 常用的Linux命令



* copy image to SD Card

  ```
  sudo dd if=~/sd-card-copy.img of=/dev/mmcblk0 bs=1M status=progress
  ```

* how to from .image.xy to SD Card

  ```
  xzcat am335x-debian-12.11-base-vscode-v6.12-armhf-2025-06-30-4gb.img.xz | sudo dd of=/dev/sdb bs=4M
  ```

* copy all file & floder to another target

  ```
  sudo cp -r . /media/alex/ROOTFS/
  ```

* mount mmc

  ```
  mount /dev/mmcblk1p1 /media/temp1 
  ```

  