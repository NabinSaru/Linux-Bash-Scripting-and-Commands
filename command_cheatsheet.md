
# Archieving and compressing files and folder

## GZIP

```sh
gzip <file_name> # compress the file
gunzip file.gz # extract the file
```

## P7ZIP

```sh
7z a ./file.7z file # 7z a {filename} {file-to-compress} to compress file/folder
7z e file.7z  # extracts the archive available file formats 7z,tgz,zip,gz2
```

# Hardware and System information

## dmidecode

Provides comprehensive hadware info such as bios, memory, processor.

## inix

Provides more managed hardware information.
Installation: `sudo apt install inix`
> inix
> inix -F

## ls

All available options for the ls commands apart from `ls`
> lspcu
> lsmem
> lsblk
> lsusb
> lspci

## os flavor and version

> lsb_release -a
> uname -a

## System Time

> cal
> time
> uptime
> date
> ncal

# Disks and File system permissions

## System backup and storing

```sh
sudo dd if=/dev/sda5 conv=sync,noerror bs=64k | gzip -c > /tmp/sda5.img.gz # creates a backup for the sda5 disk and store it on tmp folder
gunzip -c /tmp/sda5.img.gz | sudo dd of=/dev/sda5 # restore the backup into specified disk
```

## Swap memory usage

> To check the swap usage `free -h`
> To disable swap `sudo swapoff -a` or `sudo swapoff <disk_name>`
> To enable swap `sudo swapon <disk_name>`

## Mount disk or device

`sudo mount -t <type> <disk/device> /mnt`
where type can be iso9660, ntfs, ext64, fat32

`sudo umount -f /mnt`

## Run Level

Run level is preset os in the linux os that defines what services and programs can run after the boot.

### All available run levels:

- Runlevel 0: Shuts down the system in an orderly manner
- Runlevel 1: Single user mode
- Runlevel 2: Single user mode with networking
- Runlevel 3: Multi-user mode in text mode
- Runlevel 5: Multi-user mode in X Windows
- Runlevel 6: Reboots the system

### Check current run level

`sudo runlevel`
`sudo who -r`
`cat /etc/.init.state`

### To change run level

`sudo init <lvl_number>`
