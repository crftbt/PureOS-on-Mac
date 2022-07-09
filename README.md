# PureOS on Mac
Information on running PureOS on a MacBook Air, MacBook Pro, iMac, Mac mini, Mac Studio, Mac Pro

## MacBook Air 7,1
### Determine Network Device
```
lspci |grep twork
03:00.0 Network controller: Broadcom Inc. and subsidiaries BCM4360 802.11ac Wireless Network Adapter (rev 03)
```
* What we're looking for is **Broadcom BCM4360**
* Info on the Broadcom BCM4360 firmware at https://wiki.debian.org/wl
* Info on the Braodcom specific firmware https://packages.debian.org/search?keywords=broadcom-sta-dkms
### Determine version of PureOS
```
lsb_release -a
10
```
* 10 = Debian Buster
** The Debian Buster version of the broadcom firmware package https://packages.debian.org/buster-backports/broadcom-sta-dkms
*** Right Click Save As https://packages.debian.org/buster-backports/all/broadcom-sta-dkms/download 
### Install the broadcom firmware package
> sudo apt install ./broadcom*.deb

