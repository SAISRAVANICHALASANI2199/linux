# CMPE 283 - VIRTUALIZATION TECHNOLOGIES
### NAME - SAI SRAVANI CHALASANI
### SJSU ID - 015911467
### ASSIGNMENT 1 
##### *STEP - 1 - Launch your VMWare virtual machine.*
##### *STEP - 2 - Build a VM and ensure the Hypervisor supports layered virtualization.*
##### *STEP - 3 - When you set up a virtual machine, you have a few options to choose from.*
##### *STEP - 4 - In the virtual machine, I used Linux 20.0.04 LTS as the operating system.*
##### *STEP - 5 - Go to this repository and fork it on your own github account once you've downloaded and launched the OS.* 
##### *STEP - 6 - Utilizing git clone, clone the forked repository in the terminal.*
##### *STEP - 7 - Grab MakeFile after the repository has been cloned.*
##### *STEP - 8 - To run the Makefile, open the terminal in the parent directory where you cloned the repository and type make.*
##### *STEP - 9 - There's a chance you'll get licensing and version-related errors. To acquire the kernel versions, go to the clones linux directory and*
                       run cp /boot/config-5.
##### *STEP - 10 - For another phases, only a few libraries and packages are necessary.*
                   sudo apt install make
                   sudo apt install gcc
                   sudo apt install dwarves
                   sudo apt install flex
                   sudo apt install bison
                   sudo apt install libssl-dev
##### *STEP - 11 - Now we need to build a.config file with the data of the relevant kernel version config file in order to perform some make instructions.*
##### *STEP - 12 - Within the linux folder, run cp /boot/config-5.13.0-39-generic.config.*
##### *STEP - 13 - Run the command "'make oldconfig"'. To enter default values in a sequence of questions, simply hit return.*
##### *STEP - 14 - Because the version we're running now differs from the one pushed out in the previous phase, the oldconfig make command will only ask for the new things that aren't in the prior version.*
##### *STEP - 15 - Now run the command Make Prepare.*
##### *STEP - 16 - Run the command make -j x modules (where x = 4).*
##### *STEP - 17 - Run sudo make INSTALL_MOD_STRIP=1 mdoules_install.*
##### *STEP - 18 - Run  the command sudo make install.*
##### *STEP - 19 - Lastly, execute sudo reboot to force the OS to load the most latest kernel module.*
##### *STEP - 20 - To acquire the.ko kernel object, execute make.*
##### *STEP - 21 - Run sudo insmod cmpe 283-1.ko to load this file.*
##### *STEP - 22 - The previous step will not provide any output on the console. Run dmesg to see the output.*
##### *STEP - 23 - The console will exhibit a variety of lines, one of which will be the Pinbased Controls MSR value,. If the number 9 appears, it means that nested virtualization hasn't been activated, and you'll have to begin over.*
##### *STEP - 24 - If you wish to make modifications to the kernel module, instead of resetting the system, you may simply delete it, apply the modifications, rebuild the module, and reinstall it.*
##### *STEP - 25 - The final step was to git commit the Makefile and cmpe283-1.*


