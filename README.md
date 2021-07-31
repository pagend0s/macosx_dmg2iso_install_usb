https://www.youtube.com/watch?v=XmaaSK19jGQ

# mac os x installation usb under linux mint from dmg to iso
#https://support.apple.com/en-us/HT211683 - *.dmg source

######section for mounting apfs under linux mint########

#universe repositories for mint

$ sudo add-apt-repository universe

#when needed for exfat format

$ sudo apt-get install exfat-fuse exfat-utils

#libraries to mount and read apfs format

$ sudo apt-get install libfsapfs-utils

#when automatic mount of apfs failed

$ sudo fsapfsmount -f 1 /dev/sd* /media/*

$ sudo fusermount -u /mnt

##############################################

#Install dmg2img

$ sudo apt-get install dmg2img

#Convert DMG image file to ISO file

$ dmg2img -v -i /path/to/image_file.dmg -o /path/to/image_file.iso

#To identify usb partition
$ sudo LSBLK

#Copy ISO image to USB

$ sudo dd status=progress if=/path/to/image_file.iso of=/dev/sdb bs=512 && sync

#Done. Boot on mac 
