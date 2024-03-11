## D-Link DIR-845L OS Command Injection Vulnerability

**Credit** : 주송아 (syscall@korea.ac.kr) 

**Vendor** : D-Link

**Product** : DIR-845L Router 

**Firmware Link** : Firmware file is attached. Or you can download firmware at (https://www.mydlink.co.kr/2013/beta_board/product_detail.php?no=146&model=DIR-845L)



## Detailed Description

 
**Vulnerability Type** : OS Command Injection  

**Affected Version** : Firmware version <= v1.01KRb03  

**Description** : Unauthenticated remote code execution vulnerability exists in **cgibin** binary in **DIR-845L** router firmware **version ≤ v1.01KRb03**. In **soapcgi_main** function, variable **v19** is the contents behind **‘service=’** in the **REQUEST_URI** environment variable. Format **v19** to **byte_434BB0**, and execute system, resulting in command execution.


## PoC
PoC code is attached.  
To reproduce this vulnerability, you can emulate firmware by using FirmAE(https://github.com/pr0v3rbs/FirmAE)


If emulation is success, you can access web interface  


Finally, run the PoC code.  

