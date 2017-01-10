# Install Ubuntu 16.04 on Lenovo Thinkpad T440p

Well - never managed to finish the docs as nothing particular special was
required - so here is all what i wrote during install.

Maybe a few other things. The Thinkpad T440p can be found cheap on Ebay as well
as fitting displays, backlit keyboards, touchpads and batteries. In early 2017 
i got me one and upgrade it to the high end for total around 300 EUR. 

## BIOS update

Make sure its the latest BIOS, else Linux installation can brick the board.

- http://support.lenovo.com/de/en/products/laptops-and-netbooks/thinkpad-t-series-laptops/thinkpad-t440p?TabName=Downloads&beta=false
- Download the bootable CD iso. This file does not work when dd'd to a USB pen
  drive directly. Get a tool called `geteltorito.pl` from https://userpages.uni-koblenz.de/~krienke/ftp/noarch/geteltorito
  and extract the disk image from the iso, then burn this on a pen drive.

```
perl geteltorito.pl gluj30us.iso >gluj30us.img
pv gluj30us.img |sudo dd of=/dev/sdd bs=1M
```

Deregister from ThinkVantage (if registered), charge battery and keep AC and
battery connected during BIOS update at all times.

Make sure BIOS boots UEFI mode, i suggest to use UEFI only setting. Then boot
the pen drive.

After finishing the update (means you completed step 1 and 2 of the BIOS update
utility and are at the update utility prompt again, remove the PEN drive and press
F3 (Fn+F3 actually) to exit. Then enter BIOS again to check that you have the
latest version. At time of writing this is 2.39.

## BIOS settings

- Disable Security->Anti-Theft->Computrace (potential backdoor, does not work
  with Linux in any case), also disable Intel (R) AT Module Activation.
- Disable Config->Network->Wake On LAN, UEFI IPv4 and IPv6
- Enable Config->Keyboard/Mouse->F1-F12 as Primary Function
- Disable Config->Power->Intel (R) Rapid Start
- Disable Config->Intel (R) AMT->Intel (R) AMT Control
- Enable Security->Secure Boot and make sure Secure Boot Mode is "Standard Mode"

## Summary

Well its now April 2018 and i still use that Thinkpad as my secondary laptop. It
is awesome, zero noise, great 1080p mat screen and reasonably fast quad core 
i5-4300M CPU @ 2.60GHz. Loving it.


