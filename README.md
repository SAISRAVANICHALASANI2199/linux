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


### ASSIGNMENT 2
##### *1. Sravani : %eax=0x4FFFFFFF*
##### *2. Viswamithra : %eax=0x4FFFFFFE*

### *Path to assignment-2 files: linux/cmpe283/Assignment -2/*


##### *1. I have worked on CPUID leaf node %eax=0x4FFFFFFF and %eax=0x4FFFFFFE*
##### *2. Modified the code in vmx.c to get the total number of exits.*
##### *3. Modified the code in cpuid.c to to get the total number of exits.*
##### *4. Installed the nested virtual machine inside the virtual machine.*
##### *5. Ran CPUID Package with 0x4FFFFFFF in eax.*
##### *6. Total number of exits is returned to eax.*
##### *7. Modified the code in vmx.c to get the total time taken in handling the exits.*
##### *8. Modified the code in cpuid.c to to get the total time taken in handling the exits.*
##### *9. Installed CPUID Packege inside the nested VM.*
##### *10.Ran CPUID Package with 0x4FFFFFFE in eax.*
##### *11. Total time taken higher32 bits are returned to ebx and lower32 bits are returned to ecx.*

### *Commands for executing the Assignment2:*
##### *1. Modified the code in cpuid.c and vmx file.*
##### *2. make modules*
##### *3. make -j 4 modules*
##### *4. sudo bash*
##### *5. sudo make INSTALL_MOD_STRIP=1 modules_install && make install*
##### *6. lsmod | grep kvm*
##### *7. sudo rmmod kvm_intel*
##### *8. sudo rmmod kvm*
##### *9. modprobe kvm*
##### *10. modprobe kvm_intel*

### *Creating Inner Virtual Machine inside a VM using the below commands*
##### *11. sudo apt update*
##### *12. sudo apt install qemu-kvm libvirt-daemon-system libvirt-clients bridge-utils*
##### *13. sudo systemct1 status libvirtd*
##### *14. sudo systemct1 enable --now libvirtd*
##### *15. sudo apt install virt-manager*
##### *16. sudo virt-manager*
##### *17. Install ubuntu 20.4 iso image*
##### *18. Installing CPUID package*
##### *19. Download the CPUID deb package for AMD64 https://packages.ubuntu.com/bionic/admin/cpuid*
##### *110. Installed the package and execute install using sudo dpkg -i cpuid_20170122-1.deb*
##### *111. Executed the below command inside VM*
        cpuid -l 0X4fffffff -s exit_number
        cpuid -l 0X4ffffffe -s exit_number
### Assignment 3
  #### Viswamithra - %eax=0x4FFFFFFD.
  #### Sravani - %eax=0x4FFFFFFC.
  
##### *I have worked on CPUID leaf node %eax=0x4FFFFFFC and %eax=0x4FFFFFFD*
##### *2. Modified the code in vmx.c to get the total number of exits.*
##### *3. Modified the code in cpuid.c to to get the total number of exits.*
##### *4. Installed the nested virtual machine inside the virtual machine.*
##### *5. Ran CPUID Package with 0x4FFFFFFC in eax.*

### Assignment 4
##### 1.Carry on with Assignment 3's setting.
##### 2.Closed down the inside VM using the standard OS shutdown procedure.
##### 3.Remove the kvm-intel module from the outer VM with the command sudo rmmod kvm intel.
##### 4.Restart the inner VM.
##### Q3. Shadow paging has a higher exit count than nested paging because the VMM has to do more work in shadow paging.

##### Q4. When shadow paging is enabled (ept=0), the VM conducts more TLB flushes, page faults, and other operations, resulting in more exits than when ept=1.

  
 


