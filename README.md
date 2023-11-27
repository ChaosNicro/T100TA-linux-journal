# T100TA-linux-journal
## Purpose
This is a place to track my efforts to run Linux on my Transformer-book and collect info and scripts from different places, while doing my best to properly credit any work I take. 

## Starting Point

The tablet spend quite some time in a drawer, but thanks to the screen-protector it only took some dust-cleaning to make it and the dock look good again. The battery is still in surprisingly good shape as far as I can tell.

To start, I updated the BIOS-firmware. It's no longer being developed of course, The "latest" version for me was 314, note that this may differ dependig on skew. The boot-menu key to use is esc just after pressing the power button, make sure to use simple partition setups for reading the BIOS-file even if the included m-flash utility did not give me any problems.

I disabled Bitlocker in the pre-installed Windows and disabled secure boot. it should be able to enroll keys, but I wanted as few obsticles as possible for this.

I then used a Win10-installer to create a new partition table and dedicate 15GB to Win10, since I was aiming for dual-boot. This also provided me with a 100MB EFI-System-Partition. If you don't want Windows, make sure to create one here or during the Linux install.

## OS Installation

I chose BunsenLabs Beryllium for my system, it comes with the bare minimum and I expected it to run smoothly. With Ubuntu killing 32-bit support, Debian and it's derivitives are really your only options. If you want to try PuppyLinux, you can refer to the HOWTO-guide by axcxl. Though try without any exotic fixes first, since things may have gotten easier with time.

I simply flashed the BunsenLabs image to a flashdrive connected it to the Dock and booted from it. Note that I did not modify the image in any way. The install did ask to load an additional wifi-driver, but wifi worked fine after declining the prompt. I just allocated the other 15GB to the system-root on an ext4 partition. Grub installed just fine into the already present EFI-partition (no freezes) and the tablet restarted into the new Grub and then BunsenLabs. Note that Grub is currently planning to disable the os-prober by default, if you installed Windows and it does not show up in Grub, there should be a line to add to the config available on line to re-enable it.