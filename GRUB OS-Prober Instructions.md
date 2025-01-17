GRUB OS-Prober Instructions

Firstly run os-prober with sudo / doas

sudo OS-Prober

There should be an output of the prober that shows what systems that are found along side the working OS

If OS-Prober is not found you will need to install it from your package manager

sudo apt install OS-Prober # Using APT as that is what my system uses

Now that OS-Prober is installed you can then check to see if OS-Prober is disabled by doing the following

```
sudo cat /etc/default/GRUB | grep 'GRUB_DISABLE_OS_PROBER'
```
If the output is

"GRUB_DISABLE_OS_PROBER=true" then the OS-Prober is disabled

If the output of the cat command is
"GRUB_DISABLE_OS_PROBER=false" then the OS-Prober is enabled

If there is no output at all from the cat command then the OS-Prober function is not in the config
you will need to add this manually by opening the GRUB config file using superuser /  root using a text editor of your choice

sudo vim /etc/default/GRUB 

At this point if you did get an output of disabled = true then you can enable the GRUB OS-Prober

If the prober line isn't there you can add it with

GRUB_DISABLE_OS_PROBER=false

Once you have done this then you will need to update GRUB using the update GRUB function

sudo update-GRUB 

From this point you can reboot your system and you will get all installed OSes shown on your GRUB menu screen.

