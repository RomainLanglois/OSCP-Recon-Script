## OSCP Recon Script

### About
* This is a multi-threading enumeration script used to automated the basics steps of reconnaissance.

* This script scan the most common services
    * FTP
    * SSH
    * POP3/IMAP
    * NETBIOS/SMB
    * HTTP/HTTPS 

### How it works 
1. The script will check if a repository exits for the scanned machine, if not it will create one
2. Unicorscan is used to quickly discover the open ports
3. Nmap then used the port found by UnicornScan to scan the remote machine
4. Based on the port found, other tools will be used to discover more information like:
    * Banner grabbing
    * NMAP NSE scripts
    * Nikto HTTP scanner
    * SMBMAP
    * ETC... 
5. When a scan is finished, the output will be stored in a single template file (Except for Nikto)

### How to use it
For now, the script can only scan one IP Address.

* Help Banner
```
[user@machine]$ python3 enum_script.py 

------------------------------------------------------------
!!!!                      ENUM SCRIPT                  !!!!!
!!!!            A multi-process service scanner        !!!!!
!!!!             ftp, ssh, pop3, imap, smb, http,      !!!!!
!!!!                         https                     !!!!!
------------------------------------------------------------

Usage: python enum_script.py <ip>
Example: python enum_script.py 192.168.1.101

############################################################
```

* Scan a remote machine
```
[user@machine]$ python3 enum_script.py 192.168.1.10
```

## Thanks to
* superkojiman 
    * [onetwopunch](https://github.com/superkojiman/onetwopunch)


* xapax
    * [Reconscan.py](https://github.com/xapax/oscp)   

