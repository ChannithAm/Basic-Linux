Mount share files:

* Update your `APT` database with
>sudo apt-get update

* Install the latest security updates with
>sudo apt-get upgrade

* Install `dkms`
>sudo apt-get install dkms

* From the VirtualBox VM window menu select:
>Devices->Insert Guest Additions CD image...

* Use blkid to identify the CD-ROM device
>sudo blkid

One of the lines in the outputs should looklike this:
```
/dev/sr0: LABEL="VBOXADDITIONS_5.1.26_117224" TYPE="iso9660"
```
The first part (/dev/sr0) is the name of the CD-ROM device

* Mount the CD (replace /dev/sr0 by the device name found above):
>sudo mount /dev/sr0 /media/cdrom

* Run the Guest Additions installer:
>sudo /media/cdrom/VBoxLinuxAdditions.run

* Reboot the guest...
* Create directory on Guest VM
>mkdir Web

* Mount `shares` folder to guest VM (Web directory)
>sudo mount -t vboxsf shares ~/web/
