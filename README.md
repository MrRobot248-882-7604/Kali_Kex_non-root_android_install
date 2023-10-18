Kali_Kex_non-root_android_install

Prerequisite:
Android Device (Stock unmodified device, no root or custom recovery required)

Installation:
Install the NetHunter-Store app from store.nethunter.com

From the NetHunter Store, install Termux, NetHunter-KeX client, and Hacker’s keyboard Note: The button “install” may not change to “installed” in the store client after installation - just ignore it. Starting termux for the first time may seem stuck while displaying “installing” on some devices - just hit enter.

Open Termux and type:



kali@kali:~$ termux-setup-storage 

kali@kali:~$ pkg install wget

kali@kali:~$ wget -O install-nethunter-termux https://offs.ec/2MceZWr 

kali@kali:~$ chmod +x install-nethunter-termux

kali@kali:~$ bash install-nethunter-termux


Usage:
Open Termux and type one of the following:

====Command	To=====

kali@kali:~$ nethunter
start Kali NetHunter command line interface

kali@kali:~$ nethunter kex passwd	
configure the KeX password (only needed before 1st use)

kali@kali:~$ nethunter kex &	
start Kali NetHunter Desktop Experience user sessions

kali@kali:~$ nethunter kex stop
stop Kali NetHunter Desktop Experience

kali@kali:~$ nethunter <command>
run in NetHunter environment
 
kali@kali:~$ nethunter -r	
start Kali NetHunter cli as root

kali@kali:~$ nethunter -r kex passwd
configure the KeX password for root

kali@kali:~$ nethunter -r kex &	
start Kali NetHunter Desktop Experience as root

kali@kali:~$ nethunter -r kex stop
Kali NetHunter Desktop Experience root sessions
 
kali@kali:~$ nethunter -r kex kill
Kill all KeX sessions

kali@kali:~$ nethunter -r <command>	
run <command> in NetHunter environment as root


Note: The command nethunter can be abbreviated to nh. Tip: If you run kex in the background (&) without having set a password, bring it back to the foreground first when prompted to enter the password, i.e. via fg <job id> - you can later send it to the background again via Ctrl + z and bg <job id>

To use KeX, start the KeX client, enter your password and click connect Tip: For a better viewing experience, enter a custom resolution under “Advanced Settings” in the KeX Client

NetHunter Editions:
Please refer to this table for a comparison of the different NetHunter editions.

Tips:
Run sudo apt update && sudo apt full-upgrade -y first thing after installation to update Kali. If you have plenty of storage space available you might want to run sudo apt install -y kali-linux-default as well.
All of the penetration testing tools should work but some might have restrictions, e.g. metasploit works but doesn’t have database support.
Some utilities like “top” won’t run on unrooted phones.
Non-root users still have root access in the chroot. That’s a proot thing. Just be aware of that.
Galaxy phone’s may prevent non-root users from using sudo. Just use “su -c” instead.
Perform regular backups of your rootfs by stopping all nethunter sessions and typing the following in a termux session: 

kali@kali:~$ tar -cJf kali-arm64.tar.xz kali-arm64 && mv kali-arm64.tar.xz storage/downloads

That will put the backup in your Android download folder. Note: on older devices, change “arm64” to “armhf”
