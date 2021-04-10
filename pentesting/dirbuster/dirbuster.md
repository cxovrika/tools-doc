# Dirbuster

### Packages
* [AUR package](https://aur.archlinux.org/packages/dirbuster/)

### Usage
```
DirBuster - 1.0-RC1
Usage: java -jar DirBuster-1.0-RC1 -u <URL http://example.com/> [Options]

        Options:
         -h : Display this help message
         -H : Start DirBuster in headless mode (no gui), report will be auto saved on exit
         -l <Word list to use> : The Word list to use for the list based brute force. Default: /tmp/dirbuster/directory-list-2.3-small.txt
         -g : Only use GET requests. Default Not Set
         -e <File Extention list> : File Extention list eg asp,aspx. Default: php
         -t <Number of Threads> : Number of connection threads to use. Default: 10
         -s <Start point> : Start point of the scan. Default: /
         -v : Verbose output, Default: Not set
         -P : Don't Parse html, Default: Not Set
         -R : Don't be recursive, Default: Not Set
         -r <location> : File to save report to. Default: /tmp/dirbuster/DirBuster-Report-[hostname]-[port].txt

Examples:

Run DirBuster in headless mode
java -jar DirBuster-1.0-RC1.jar -H -u https://www.target.com/

Start GUI with target prepopulated
java -jar DirBuster-1.0-RC1.jar -u https://www.target.com/
```
