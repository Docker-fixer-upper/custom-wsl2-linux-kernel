# Custom WSL2 Linux Kernel

This repository is forked from 
[ custom-wsl2-linux-kernel](https://github.com/LGUG2Z/custom-wsl2-linux-kernel/tree/linux-msft-wsl-5.15.133.1)

# Usage
1. Go to releases and download the latest kernal release, vmlinux, and store it at C:\Users\YourUsernameHere\WSL2\vmlinux (replacing YourUsernameHere with your user information, e.g. C:\Users\Jacob\WSL2, the final path should be C:  \Users\YourUsernameHere\WSL2\vmlinux)
2. Download .wslconfig from the main page, or extract it from the source code zip, and edit the file in Notepad as noted below:      
   Replace `YourUsernameHere` at line 3 in kernel=C:\\Users\\YourUsernameHere\\WSL2\\vmlinux  
   Replace `YourUsernameHere` at line 11 in swapFile=C:\\Users\\YourUsernameHere\\AppData\\Local\\Temp\\swap.vhdx   
4. Move vmlinux to C:\Users\YourUsernameHere\WSL2\vmlinux and move .wslconfig to C:\Users\YourUsernameHere\  
5. Make sure you have saved all your work in all WSL2 instances, then open your terminal/cmd in Windows and run the command: `wsl --shutdown`  
6. Restart wsl by running the command: `wsl`  
7. From inside wsl (it will open after running "wsl", it takes a moment), run the command: `uname -sr` confirming that the command returns as below:  
```
Linux 5.15.123.1-lgug2z-custom-WSL2-DockerWiregaurdFix"
```  
7. Restart Docker Desktop  
8. In Docker Desktop settings, go to Resources > WSL Integration, and check "Enable integration with my default WSL distro" and under "Enable integration with additional distros:" enable "Ubuntu". If it is missing, click "Refresh"  
9. Apply and restart  
10. Rebuild your containers, the CONMARK and Wireguard issues should be gone  
