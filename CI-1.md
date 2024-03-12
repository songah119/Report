## D-Link DIR-845L OS Command Injection Vulnerability

**Credit** : 주송아 (syscall@korea.ac.kr) 

**Vendor** : D-Link

**Product** : DIR-845L Router 

**Firmware Link** : Firmware file is attached. Or you can download firmware at (https://www.mydlink.co.kr/2013/beta_board/product_detail.php?no=146&model=DIR-845L)
![poc_dir845L](https://github.com/songah119/Report/assets/69359991/ea33375f-7e53-4cdf-8283-43a4d4405fdb)


## Detailed Description

**Vulnerability Type** : OS Command Injection  

**Affected Version** : Firmware version <= v1.01KRb03  

**Description** : Unauthenticated remote code execution vulnerability exists in **cgibin** binary in **DIR-845L** router firmware **version ≤ v1.01KRb03**. In **soapcgi_main** function, variable **pcVar3** is the contents behind **‘?service=’** in the **REQUEST_URI** environment variable. Format **pcVar3** to **DAT_00434bb0**, and execute system, resulting in command execution.
![poc_code](https://github.com/songah119/Report/assets/69359991/f84cc19c-c896-4980-9cf6-bb5438feb887)


## PoC
PoC code is attached.  
To reproduce this vulnerability, you can emulate firmware by using FirmAE(https://github.com/pr0v3rbs/FirmAE)
![poc_runemul](https://github.com/songah119/Report/assets/69359991/a4880c0d-6a5c-449b-b11a-c6a24c93cf96)


If emulation is success, you can access web interface  
![poc_admin](https://github.com/songah119/Report/assets/69359991/d1389506-c62b-415d-9e54-c17bc6204466)


Finally, run the PoC code.  
![poc](https://github.com/songah119/Report/assets/69359991/2d3de47f-14f1-4497-bd70-d5040306f8ce)


