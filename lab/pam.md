## 0. Initial Setup

Ref:
- https://docs.fortinet.com/document/fortipam-private-cloud/latest/microsoft-hyper-v-administration-guide/55152/fortipam-vm-gui-access
- https://docs.fortinet.com/document/fortipam/latest/administration-guide/405201/fortipam-with-tpm


```console
FortiPAM-HyperV # config system interface

FortiPAM-HyperV (interface) # edit port2

FortiPAM-HyperV (port2) # set ip 10.0.30.28/24

FortiPAM-HyperV (port2) # set type physical

FortiPAM-HyperV (port2) # set snmp-index 2

FortiPAM-HyperV (port2) # next

FortiPAM-HyperV (interface) # end

FortiPAM-HyperV # config router static

device pFortiPAM-HyperV (static) # edit 1

new entry '1' added

FortiPAM-HyperV (1) # set device port1

FortiPAM-HyperV (1) # set gateway 192.168.17.1

FortiPAM-HyperV (1) # next

FortiPAM-HyperV (static) # end

FortiPAM-HyperV # config system dns

FortiPAM-HyperV (dns) # set primary 192.168.17.1

FortiPAM-HyperV (dns) # unset secondary

FortiPAM-HyperV (dns) # end

FortiPAM-HyperV # config system global

FortiPAM-HyperV (global) # set timezone 57

FortiPAM-HyperV (global) # end

FortiPAM-HyperV # config system admin

FortiPAM-HyperV (admin) # edit admin

FortiPAM-HyperV (admin) # set ssh-public-key1 "<ssh public key>"
SSH key is good.

FortiPAM-HyperV (admin) # end

FortiPAM-HyperV # diagnose tpm selftest

Successfully tested. Works as expected.



FortiPAM-HyperV # config system global

FortiPAM-HyperV (global) # set v-tpm enable

FortiPAM-HyperV (global) # end

FortiPAM-HyperV # config system maintenance

FortiPAM-HyperV (maintenance) # set mode enable

FortiPAM-HyperV (maintenance) # end

FortiPAM-HyperV # config system global

FortiPAM-HyperV (global) # set private-data-encryption enable

FortiPAM-HyperV (global) # end
Be carefull!!!This operation will refresh all ciphered data!
Backup the current configuration file at first!
Do you want to continue? (y/n)y

Please type your private data encryption key (32 hexadecimal numbers):
0123456789abcdef0123456789abcdef
Please re-enter your private data encryption key (32 hexadecimal numbers) again:
0123456789abcdef0123456789abcdef
Your private data encryption key is accepted.

FortiPAM-HyperV # execute disk encryption enable
Change disk encryption setting will erase all data in log and video disk.
And system will reboot!
Do you want to continue? (y/n)y

Connection to pam.net.vx closed by remote host.
Connection to pam.net.vx closed.
```
