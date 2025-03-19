## 1. Create resource group

![image](https://github.com/user-attachments/assets/f508562b-9e08-4a2f-ac22-32cc8946e4d5)

![image](https://github.com/user-attachments/assets/969ea176-c2ad-46f2-8841-61d57cfb3360)

![image](https://github.com/user-attachments/assets/ed4490eb-b111-490e-a11f-5c0e9f1beaa6)

![image](https://github.com/user-attachments/assets/495d665c-d91e-4317-978e-95adcf55e3c3)

## 2. Connect hybrid machines to Azure using a deployment script

![image](https://github.com/user-attachments/assets/b7259c21-4679-4c89-86a9-ff2b76a2dfec)

### 2.1. Windows

#### 2.1.1. Generate installation script

![image](https://github.com/user-attachments/assets/2602d30c-8657-4a9d-99fd-19bff389c3c1)

![image](https://github.com/user-attachments/assets/7acb6ec9-9282-4699-bfae-6a988396c262)

![image](https://github.com/user-attachments/assets/b584d4f4-2111-4d5d-b1d6-de320599217f)

#### 2.1.2. Execute installation script

Run the powershell script:

```pwsh
PS C:\Users\Administrator> .\OnboardingScript.ps1
VERBOSE: Installing Azure Connected Machine Agent
VERBOSE: PowerShell version: 5.1.26100.2161
VERBOSE: Total Physical Memory: 4096 MB
VERBOSE: .NET Framework version: 4.8.9032
VERBOSE: Checking if this is an Azure virtual machine
VERBOSE: Error The operation has timed out. checking if we are in Azure
VERBOSE: Downloading agent package from https://gbl.his.arc.azure.com/azcmagent/latest/AzureConnectedMachineAgent.msi to C:\Users\ADMINI~1\AppData\Local\Temp\2\AzureConnectedMachineAgent.msi
VERBOSE: Installing agent package
Installation of azcmagent completed successfully
INFO    Connecting machine to Azure... This might take a few minutes.
INFO    Testing connectivity to endpoints that are needed to connect to Azure... This might take a few minutes.
INFO    Please login using the pop-up browser to authenticate.
```

Login and authenticate through pop-up browser:

![image](https://github.com/user-attachments/assets/ae6160e2-6ac8-4fd5-84a6-d79820995795)

Installation proceeds automatically after authentication:

```pwsh
  20% [==>            ]
  30% [===>           ]
  INFO    Creating resource in Azure...                 Correlation ID=75c63a20-4a0f-408c-8fbe-585e34aae18a Resource ID=/subscriptions/80bf8757-394c-4ad6-95d2-101d9643ba13/resourceGroups/azcm-rg/providers/Microsoft.HybridCompute/machines/azcm-winsvr
  60% [========>      ]
  80% [===========>   ]
 100% [===============]
  INFO    Connected machine to Azure
INFO    Machine overview page: https://portal.azure.com/#@659330c7-4c00-42e9-b0d6-411ab5697f6e/resource/subscriptions/80bf8757-394c-4ad6-95d2-101d9643ba13/resourceGroups/azcm-rg/providers/Microsoft.HybridCompute/machines/azcm-winsvr/overview
```

![image](https://github.com/user-attachments/assets/190a97bd-ad32-4038-a502-b2fcf1906c40)

#### 2.1.3. Verify connection in Azure

![image](https://github.com/user-attachments/assets/7e3c05c0-02a6-450d-a69b-d2c6fbaaff2b)

### 2.2. Linux

#### 2.2.1. Generate installation script:

![image](https://github.com/user-attachments/assets/fab5cba5-73c3-429b-843e-786251ed37c2)

![image](https://github.com/user-attachments/assets/1d8d7e31-29c5-4e57-aaa8-7f2abf5428db)

![image](https://github.com/user-attachments/assets/98d44961-d938-48ed-865a-ce1d41ac9dd9)

#### 2.2.2. Execute installation script

##### 2.2.2.1. Rocky Linux

Run the bash script:

```console
[root@azcm-rocky ~]# chmod +x OnboardingScript.sh
[root@azcm-rocky ~]# ./OnboardingScript.sh
--2025-03-19 12:09:00--  https://gbl.his.arc.azure.com/azcmagent-linux
Resolving gbl.his.arc.azure.com (gbl.his.arc.azure.com)... 172.202.65.10, 172.202.64.10, 2603:1030:13:200::10, ...
Connecting to gbl.his.arc.azure.com (gbl.his.arc.azure.com)|172.202.65.10|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: unspecified [text/plain]
Saving to: ‘/tmp/install_linux_azcmagent.sh’

     0K .......... .......... .......... .                      137K=0.2s

2025-03-19 12:09:03 (137 KB/s) - ‘/tmp/install_linux_azcmagent.sh’ saved [32155]
Using 'curl' for downloads
Total physical memory: 4007416 kB
Platform type:  x86_64:Linux
Retrieving distro info from /etc/os-release...
Configuring for Rocky Linux 9...
Using 'dnf' instead of 'yum'
No match for argument: packages-microsoft-prod
No packages marked for removal.
Dependencies resolved.
Nothing to do.
Complete!
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  9450  100  9450    0     0  20498      0 --:--:-- --:--:-- --:--:-- 20498
warning: /tmp/packages-microsoft-prod.rpm: Header V4 RSA/SHA256 Signature, key ID be1229cf: NOKEY
Microsoft Production                                                                                                                            1.5 kB/s | 481  B     00:00
Microsoft Production                                                                                                                            960 kB/s | 983  B     00:00
Importing GPG key 0xBE1229CF:
 Userid     : "Microsoft (Release signing) <gpgsecurity@microsoft.com>"
 Fingerprint: BC52 8686 B50D 79E3 39D3 721C EB3E 94AD BE12 29CF
 From       : /etc/pki/rpm-gpg/RPM-GPG-KEY-Microsoft
Microsoft Production                                                                                                                             13 MB/s |  12 MB     00:00
Last metadata expiration check: 0:00:03 ago on Wed 19 Mar 2025 12:09:05 PM +08.
Dependencies resolved.
=================================================================================================================================================================================
 Package                              Architecture                      Version                                    Repository                                              Size
=================================================================================================================================================================================
Installing:
 azcmagent                            x86_64                            1.50.02986-239                             packages-microsoft-com-prod                             75 M

Transaction Summary
=================================================================================================================================================================================
Install  1 Package

Total download size: 75 M
Installed size: 212 M
Downloading Packages:
azcmagent-1.50.02986-239.x86_64.rpm                                                                                                              27 MB/s |  75 MB     00:02
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Total                                                                                                                                            27 MB/s |  75 MB     00:02
Microsoft Production                                                                                                                            960 kB/s | 983  B     00:00
Importing GPG key 0xBE1229CF:
 Userid     : "Microsoft (Release signing) <gpgsecurity@microsoft.com>"
 Fingerprint: BC52 8686 B50D 79E3 39D3 721C EB3E 94AD BE12 29CF
 From       : /etc/pki/rpm-gpg/RPM-GPG-KEY-Microsoft
Key imported successfully
Running transaction check
Transaction check succeeded.
Running transaction test
Transaction test succeeded.
Running transaction
  Preparing        :                                                                                                                                                        1/1
  Running scriptlet: azcmagent-1.50.02986-239.x86_64                                                                                                                        1/1
Pre...Install
Creating himds group ...
Creating himds account ...
Creating arcproxy account ...

  Installing       : azcmagent-1.50.02986-239.x86_64                                                                                                                        1/1
  Running scriptlet: azcmagent-1.50.02986-239.x86_64                                                                                                                        1/1
Post...Install
which: no netstat in (/sbin:/bin:/usr/sbin:/usr/bin:/usr/X11R6/bin)
Netstat not installed.  Skipping IP port checking. The services need to listen on 40342 and 40343
/var/tmp/rpm-tmp.AZxfMj: line 38:  : command not found
which: no semanage in (/sbin:/bin:/usr/sbin:/usr/bin:/usr/X11R6/bin)
Created symlink /etc/systemd/system/multi-user.target.wants/himdsd.service → /usr/lib/systemd/system/himdsd.service.
Local configuration file is found
Getting status via systemd
Arc GC service is not running.
Configuring Arc GC service ...
Found systemd service controller...for Arc GC Service
Created symlink /etc/systemd/system/multi-user.target.wants/gcad.service → /usr/lib/systemd/system/gcad.service.
Service configured through systemd service controller. Gc Service
Local configuration file is found
Checked guest config disabled: 0
Getting status via systemd
Arc GC service is not running.
STARTING Arc GC
Getting status via systemd
EXT service is not running.
Configuring EXT service ...
Found systemd service controller...for Extension Service
Created symlink /etc/systemd/system/multi-user.target.wants/extd.service → /usr/lib/systemd/system/extd.service.
Service configured through systemd service controller. Extension Service
Local configuration file is found
Checked extd disabled: 0
STARTING EXT

  Verifying        : azcmagent-1.50.02986-239.x86_64                                                                                                                        1/1

Installed:
  azcmagent-1.50.02986-239.x86_64

Complete!
Latest version of azcmagent is installed.
INFO    Connecting machine to Azure... This might take a few minutes.
INFO    Testing connectivity to endpoints that are needed to connect to Azure... This might take a few minutes.
To sign in, use a web browser to open the page https://microsoft.com/devicelogin and enter the code BEH53UMDB to authenticate.
```

Open `https://microsoft.com/devicelogin` and authenticate:

![image](https://github.com/user-attachments/assets/f2b920a5-634f-4792-9150-795453e2d088)

![image](https://github.com/user-attachments/assets/5f9232b4-0f47-469c-9bb2-c1b972178a34)

![image](https://github.com/user-attachments/assets/880a7bd8-8b2e-49e7-9b22-d5e94822c76e)

![image](https://github.com/user-attachments/assets/0e42f6fa-1e8c-435e-ace0-7001ecfbd12b)

Installation proceeds automatically after authentication:

```console
  20% [==>            ]
  30% [===>           ]
  INFO    Creating resource in Azure...                 Correlation ID=09a3985a-0853-46df-995c-2a57175f5a2f Resource ID=/subscriptions/80bf8757-394c-4ad6-95d2-101d9643ba13/resourceGroups/azcm-rg/providers/Microsoft.HybridCompute/machines/azcm-rocky
  60% [========>      ]
  80% [===========>   ]
 100% [===============]
  INFO    Connected machine to Azure
INFO    Machine overview page: https://portal.azure.com/#@659330c7-4c00-42e9-b0d6-411ab5697f6e/resource/subscriptions/80bf8757-394c-4ad6-95d2-101d9643ba13/resourceGroups/azcm-rg/providers/Microsoft.HybridCompute/machines/azcm-rocky/overview
```

![image](https://github.com/user-attachments/assets/ff8eb51d-e7c7-4abc-ba2f-aecd849f8021)

##### 2.2.2.2. Ubuntu

Run the bash script:

```console
root@azcm-ubuntu:~# chmod +x OnboardingScript.sh
root@azcm-ubuntu:~# ./OnboardingScript.sh
--2025-03-19 12:13:14--  https://gbl.his.arc.azure.com/azcmagent-linux
Resolving gbl.his.arc.azure.com (gbl.his.arc.azure.com)... 172.202.65.10, 172.202.64.10, 2603:1030:13:201::10, ...
Connecting to gbl.his.arc.azure.com (gbl.his.arc.azure.com)|172.202.65.10|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: unspecified [text/plain]
Saving to: ‘/tmp/install_linux_azcmagent.sh’

     0K .......... .......... .......... .                     8.47M=0.004s

2025-03-19 12:13:14 (8.47 MB/s) - ‘/tmp/install_linux_azcmagent.sh’ saved [32155]
Using 'curl' for downloads
Total physical memory: 4008696 kB
Platform type:  x86_64:Linux
Retrieving distro info from /etc/os-release...
Configuring for Ubuntu 24.04...
sudo: lsof: command not found
sudo: lsof: command not found
Hit:1 http://archive.ubuntu.com/ubuntu noble InRelease
Get:2 http://archive.ubuntu.com/ubuntu noble-updates InRelease [126 kB]
Get:3 http://security.ubuntu.com/ubuntu noble-security InRelease [126 kB]
Get:4 http://archive.ubuntu.com/ubuntu noble-backports InRelease [126 kB]
Get:5 http://security.ubuntu.com/ubuntu noble-security/main amd64 Packages [670 kB]
Get:6 http://archive.ubuntu.com/ubuntu noble/restricted amd64 Packages [93.9 kB]
Get:7 http://archive.ubuntu.com/ubuntu noble/restricted Translation-en [18.7 kB]
Get:8 http://archive.ubuntu.com/ubuntu noble/universe amd64 Packages [15.0 MB]
Get:9 http://security.ubuntu.com/ubuntu noble-security/main Translation-en [130 kB]
Get:10 http://security.ubuntu.com/ubuntu noble-security/main amd64 Components [8964 B]
Get:11 http://security.ubuntu.com/ubuntu noble-security/restricted amd64 Packages [726 kB]
Get:12 http://security.ubuntu.com/ubuntu noble-security/restricted Translation-en [146 kB]
Get:13 http://security.ubuntu.com/ubuntu noble-security/restricted amd64 Components [212 B]
Get:14 http://security.ubuntu.com/ubuntu noble-security/universe amd64 Packages [819 kB]
Get:15 http://security.ubuntu.com/ubuntu noble-security/universe Translation-en [177 kB]
Get:16 http://security.ubuntu.com/ubuntu noble-security/universe amd64 Components [52.0 kB]
Get:17 http://security.ubuntu.com/ubuntu noble-security/multiverse amd64 Packages [26.2 kB]
Get:18 http://security.ubuntu.com/ubuntu noble-security/multiverse Translation-en [4892 B]
Get:19 http://security.ubuntu.com/ubuntu noble-security/multiverse amd64 Components [208 B]
Get:20 http://archive.ubuntu.com/ubuntu noble/universe Translation-en [5982 kB]
Get:21 http://archive.ubuntu.com/ubuntu noble/universe amd64 Components [3871 kB]
Get:22 http://archive.ubuntu.com/ubuntu noble/multiverse amd64 Packages [269 kB]
Get:23 http://archive.ubuntu.com/ubuntu noble/multiverse Translation-en [118 kB]
Get:24 http://archive.ubuntu.com/ubuntu noble/multiverse amd64 Components [35.0 kB]
Get:25 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 Packages [921 kB]
Get:26 http://archive.ubuntu.com/ubuntu noble-updates/main Translation-en [209 kB]
Get:27 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 Components [151 kB]
Get:28 http://archive.ubuntu.com/ubuntu noble-updates/restricted amd64 Packages [759 kB]
Get:29 http://archive.ubuntu.com/ubuntu noble-updates/restricted Translation-en [153 kB]
Get:30 http://archive.ubuntu.com/ubuntu noble-updates/restricted amd64 Components [212 B]
Get:31 http://archive.ubuntu.com/ubuntu noble-updates/universe amd64 Packages [1040 kB]
Get:32 http://archive.ubuntu.com/ubuntu noble-updates/universe Translation-en [262 kB]
Get:33 http://archive.ubuntu.com/ubuntu noble-updates/universe amd64 Components [364 kB]
Get:34 http://archive.ubuntu.com/ubuntu noble-updates/multiverse amd64 Packages [30.1 kB]
Get:35 http://archive.ubuntu.com/ubuntu noble-updates/multiverse Translation-en [5884 B]
Get:36 http://archive.ubuntu.com/ubuntu noble-updates/multiverse amd64 Components [940 B]
Get:37 http://archive.ubuntu.com/ubuntu noble-backports/main amd64 Components [208 B]
Get:38 http://archive.ubuntu.com/ubuntu noble-backports/restricted amd64 Components [212 B]
Get:39 http://archive.ubuntu.com/ubuntu noble-backports/universe amd64 Packages [14.2 kB]
Get:40 http://archive.ubuntu.com/ubuntu noble-backports/universe Translation-en [12.1 kB]
Get:41 http://archive.ubuntu.com/ubuntu noble-backports/universe amd64 Components [20.0 kB]
Get:42 http://archive.ubuntu.com/ubuntu noble-backports/multiverse amd64 Components [212 B]
Fetched 32.5 MB in 7s (4967 kB/s)
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
74 packages can be upgraded. Run 'apt list --upgradable' to see them.
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
E: Unable to locate package packages-microsoft-prod
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  4298  100  4298    0     0  49730      0 --:--:-- --:--:-- --:--:-- 49976
Selecting previously unselected package packages-microsoft-prod.
(Reading database ... 72864 files and directories currently installed.)
Preparing to unpack .../packages-microsoft-prod.deb ...
Unpacking packages-microsoft-prod (1.1-ubuntu24.04) ...
Setting up packages-microsoft-prod (1.1-ubuntu24.04) ...
Get:1 https://packages.microsoft.com/ubuntu/24.04/prod noble InRelease [3599 B]
Hit:2 http://security.ubuntu.com/ubuntu noble-security InRelease
Get:3 https://packages.microsoft.com/ubuntu/24.04/prod noble/main all Packages [576 B]
Get:4 https://packages.microsoft.com/ubuntu/24.04/prod noble/main amd64 Packages [23.0 kB]
Get:5 https://packages.microsoft.com/ubuntu/24.04/prod noble/main armhf Packages [7318 B]
Hit:6 http://archive.ubuntu.com/ubuntu noble InRelease
Get:7 https://packages.microsoft.com/ubuntu/24.04/prod noble/main arm64 Packages [14.6 kB]
Hit:8 http://archive.ubuntu.com/ubuntu noble-updates InRelease
Hit:9 http://archive.ubuntu.com/ubuntu noble-backports InRelease
Fetched 49.1 kB in 2s (26.8 kB/s)
Reading package lists... Done
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following NEW packages will be installed:
  azcmagent
0 upgraded, 1 newly installed, 0 to remove and 74 not upgraded.
Need to get 72.6 MB of archives.
After this operation, 0 B of additional disk space will be used.
Get:1 https://packages.microsoft.com/ubuntu/24.04/prod noble/main amd64 azcmagent amd64 1.50.02986.239 [72.6 MB]
Fetched 72.6 MB in 3s (23.9 MB/s)
debconf: delaying package configuration, since apt-utils is not installed
Selecting previously unselected package azcmagent.
(Reading database ... 72881 files and directories currently installed.)
Preparing to unpack .../azcmagent_1.50.02986.239_amd64.deb ...
Preinstall...install
Creating himds group ...
Creating himds account ...
Creating arcproxy account ...
Unpacking azcmagent (1.50.02986.239) ...
Setting up azcmagent (1.50.02986.239) ...
Postinstall...configure
Creating new /var/opt/azcmagent/agentconfig.json
Creating new /etc/cron.d/azcmagent_autoupgrade
Netstat not installed.  Skipping IP port checking. The service needs to listen on 40342
Created symlink /etc/systemd/system/multi-user.target.wants/himdsd.service → /usr/lib/systemd/system/himdsd.service.
Checked guest config disabled:
Checked ext service disabled:
Checked arc proxy enabled: 0
Disabling arcproxyd
Getting status via systemd
Arc GC service is not running.
Configuring Arc GC service ...
Found systemd service controller...for Arc GC Service
Created symlink /etc/systemd/system/multi-user.target.wants/gcad.service → /usr/lib/systemd/system/gcad.service.
Service configured through systemd service controller. Gc Service
Enabling gcad
Getting status via systemd
Arc GC service is not running.
STARTING Arc GC
Getting status via systemd
EXT service is not running.
Configuring EXT service ...
Found systemd service controller...for Extension Service
Created symlink /etc/systemd/system/multi-user.target.wants/extd.service → /usr/lib/systemd/system/extd.service.
Service configured through systemd service controller. Extension Service
Enabling extd
STARTING EXT
Scanning processes...
Scanning linux images...

Running kernel seems to be up-to-date.

No services need to be restarted.

No containers need to be restarted.

No user sessions are running outdated binaries.

No VM guests are running outdated hypervisor (qemu) binaries on this host.
Latest version of azcmagent is installed.
INFO    Connecting machine to Azure... This might take a few minutes.
INFO    Testing connectivity to endpoints that are needed to connect to Azure... This might take a few minutes.
To sign in, use a web browser to open the page https://microsoft.com/devicelogin and enter the code B24AKJND9 to authenticate.
```

Open `https://microsoft.com/devicelogin` and authenticate:

![image](https://github.com/user-attachments/assets/b5ad26fc-4b48-48fd-94fb-8c2a896d120f)

![image](https://github.com/user-attachments/assets/5f9232b4-0f47-469c-9bb2-c1b972178a34)

![image](https://github.com/user-attachments/assets/02728dca-a623-4e61-98d2-446974ee42b3)

![image](https://github.com/user-attachments/assets/0e42f6fa-1e8c-435e-ace0-7001ecfbd12b)

Installation proceeds automatically after authentication:

```console
  20% [==>            ]
  30% [===>           ]
  INFO    Creating resource in Azure...                 Correlation ID=09a3985a-0853-46df-995c-2a57175f5a2f Resource ID=/subscriptions/80bf8757-394c-4ad6-95d2-101d9643ba13/resourceGroups/azcm-rg/providers/Microsoft.HybridCompute/machines/azcm-ubuntu
  60% [========>      ]
  80% [===========>   ]
 100% [===============]
  INFO    Connected machine to Azure
INFO    Machine overview page: https://portal.azure.com/#@659330c7-4c00-42e9-b0d6-411ab5697f6e/resource/subscriptions/80bf8757-394c-4ad6-95d2-101d9643ba13/resourceGroups/azcm-rg/providers/Microsoft.HybridCompute/machines/azcm-ubuntu/overview
```

![image](https://github.com/user-attachments/assets/71ea3c24-c9cf-4480-97fb-120d64ade5a2)

#### 2.2.3. Verify connection in Azure

![image](https://github.com/user-attachments/assets/f49bcda7-53bc-47bf-9ad1-c90b601a768e)

![image](https://github.com/user-attachments/assets/c1914aef-5e58-451b-9eaf-1b078d4caa2a)

### 2.3. Azure Arc machines

![image](https://github.com/user-attachments/assets/609b48ed-1285-4967-8302-74e5b24e5509)
