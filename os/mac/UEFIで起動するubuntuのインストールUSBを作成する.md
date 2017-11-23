UEFIで起動するUbuntuのインストールUSBを作成する
===================

```
diskutil  list
diskutil eraseDisk MS-DOS UNTITLED /dev/disk2
diskutil unmountDisk /dev/disk2
sudo dd if=/Users/chiehayashida/Downloads/ubuntu-16.04.3-desktop-amd64.iso of=/dev/disk2 bs=4028
diskutil eject /dev/disk
```
