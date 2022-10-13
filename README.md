# kernal-cheat-sheet
This repository contains some common commands used to play around with the linux kernel

## Check Current Kernel

```bash
uname -r
```
sample output
```bash
5.15.0-33-generic
```
## List Installed Kernel on Machine

Debian Based Systems (Ubuntu/Debian/Kali/Rpi)
```bash
dpkg --list | grep linux-image
```

Sample Output
```bash
ii  linux-image-4.19.234.mptcp                    20220311125841-1                        amd64        Linux kernel, version 4.19.234.mptcp
rc  linux-image-5.15.0-23-generic                 5.15.0-23.23                            amd64        Signed kernel image generic
rc  linux-image-5.15.0-25-generic                 5.15.0-25.25                            amd64        Signed kernel image generic
ri  linux-image-5.15.0-27-generic                 5.15.0-27.28                            amd64        Signed kernel image generic
ii  linux-image-5.15.0-33-generic                 5.15.0-33.34                            amd64        Signed kernel image generic
ii  linux-image-generic-hwe-22.04                 5.15.0.33.36                            amd64        Generic Linux kernel image
ii  linux-image-unsigned-5.15.0-23-generic-dbgsym 5.15.0-23.23                            amd64        Linux kernel debug image for version 5.15.0 on 64 bit x86 SMP

```

## Latest Linux Kernel for Ubuntu (Easy Way)
 1. GOTO https://kernel.ubuntu.com/~kernel-ppa/mainline/
 2. Find Latest Kernel (6.0.1 in my case)
 3. Select your architecture (if youre not sure, then most likely you have a amd64 machine)
 4. Download all 4 .deb packages (you can also do this from the terminal as follows)
    ```bash
    mkdir -p v6.0.1 && cd v6.0.1
    wget 'https://kernel.ubuntu.com/~kernel-ppa/mainline/v6.0.1/amd64/linux-headers-6.0.1-060001-generic_6.0.1-060001.202210120833_amd64.deb'
    wget 'https://kernel.ubuntu.com/~kernel-ppa/mainline/v6.0.1/amd64/linux-headers-6.0.1-060001_6.0.1-060001.202210120833_all.deb'
    wget 'https://kernel.ubuntu.com/~kernel-ppa/mainline/v6.0.1/amd64/linux-image-unsigned-6.0.1-060001-generic_6.0.1-060001.202210120833_amd64.deb
    wget 'https://kernel.ubuntu.com/~kernel-ppa/mainline/v6.0.1/amd64/linux-modules-6.0.1-060001-generic_6.0.1-060001.202210120833_amd64.deb'
    ```
 5. Install downloaded packages
    ```bash
     # IF NO OTHER .deb files are there in your folder simply run
     sudo dpkg -i *.deb
     # ELSE dpkg -i <insert all 4 file names seperated by space> 
     ```
 6. Confim Install is complete by checking list
    ```bash
    dpkg --list | grep 6.0.1
    ``` 
