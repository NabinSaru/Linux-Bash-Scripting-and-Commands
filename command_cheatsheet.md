
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
