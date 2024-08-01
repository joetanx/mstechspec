## 1. Initial setup

Ref:
- https://docs.fortinet.com/document/fortipam-private-cloud/latest/microsoft-hyper-v-administration-guide/55152/fortipam-vm-gui-access
- https://docs.fortinet.com/document/fortipam/latest/administration-guide/405201/fortipam-with-tpm


```sh
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

### 1.1. Interface certificate settings

![image](https://github.com/user-attachments/assets/2d649945-8b9c-4481-8008-7fabbdaef4ee)

![image](https://github.com/user-attachments/assets/90510610-2158-4d23-9bfa-fc780630e7c6)

![image](https://github.com/user-attachments/assets/3c7b2263-6a95-41fe-988f-7bcf9524cf57)

![image](https://github.com/user-attachments/assets/2ded4378-7d9b-48cc-9bf3-dba0833de816)

## 2. Email notifications

### 2.1. Email server settings

![image](https://github.com/user-attachments/assets/de86e13e-a9e0-4aad-baff-1869863e3330)

![image](https://github.com/user-attachments/assets/a3da8af5-c732-4485-b39d-53bfcadb57e5)

![image](https://github.com/user-attachments/assets/8845451f-5a47-4108-a73b-3bfe0553b74d)

### 2.2. Email alert settings

![image](https://github.com/user-attachments/assets/1a74f72e-ab68-4ffd-924f-460c4320affe)

![image](https://github.com/user-attachments/assets/1c5459eb-1e2e-4de1-98ea-0d1eeeff1c57)

![image](https://github.com/user-attachments/assets/1944d540-d766-4470-afce-ae1180e383c4)
