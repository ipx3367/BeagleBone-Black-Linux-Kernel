# Linux 編譯Kernel筆記

* SCP Cpoy
	``` 
	scp hellomodule.ko debian@192.168.0.109:/home/debian/
	```
	
* Load & unLoad Module

  ```
  sudo insmod hellomodule.ko
  sudo rmmod hellomodule.ko
  ```

  