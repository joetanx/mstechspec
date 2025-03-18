## 1. Create security resource group

![image](https://github.com/user-attachments/assets/544a3148-d9fa-409e-a4fe-42b14d9809a1)

![image](https://github.com/user-attachments/assets/a417c1f8-dcfe-41f4-92d5-6539fda000c9)

![image](https://github.com/user-attachments/assets/1f2561e5-129e-44d3-9c91-b81638b4d597)

## 2. Create Azure key vault

![image](https://github.com/user-attachments/assets/d5fc127c-2c64-47b9-9d61-cfb7fe7d4831)

![image](https://github.com/user-attachments/assets/dc500533-03ee-4215-939c-de49f2708961)

> [!Note]
>
> Secure the key vault by disabling public access or allowing only selected networks

![image](https://github.com/user-attachments/assets/e098913d-74b3-41d3-ae61-e88fca67e541)

![image](https://github.com/user-attachments/assets/3b0b1564-82b0-4cd9-82d1-a702a42af89c)

![image](https://github.com/user-attachments/assets/895e3a80-be18-4f66-9a5f-a9485fe64f1a)

![image](https://github.com/user-attachments/assets/e8b5d219-0613-4f73-80b4-133c1691f90a)

![image](https://github.com/user-attachments/assets/3b76f67d-b667-406a-979a-f9faf4cf9f06)

## 3. Configure key vault administrator access

> [!Note]
>
> The creator of the key vault is the owner, but this doesn't grant permissions on key vault contents
>
> `Key Vault XXXX` roles are required to work on key vault contents

![image](https://github.com/user-attachments/assets/f9cc4e72-5b4e-4ae4-8f49-914e0521cde7)

![image](https://github.com/user-attachments/assets/3f2c8582-4ac0-43eb-8da7-a1b69a4177bd)

![image](https://github.com/user-attachments/assets/3e48340f-9136-4723-947a-330c2453f9d2)

![image](https://github.com/user-attachments/assets/31432aab-4e8b-46f3-a7dc-c42d9ac7ddd4)

![image](https://github.com/user-attachments/assets/c9e96152-a686-4744-b8f4-9c2068ef6bcc)

## 4. Onboard secrets

### 4.1. SSH private key for Linux VM

The private key file needs to be uploaded via Azure CLI

![image](https://github.com/user-attachments/assets/2c30ee31-e132-4ad7-9a17-2331278f836c)

#### 4.1.1. Create SSH key so that it can be used to create VMs in the future

![image](https://github.com/user-attachments/assets/8559e094-ffe8-4958-8a60-5683d4ce7816)

![image](https://github.com/user-attachments/assets/fbfc1392-b80a-47d1-a3c3-b7ba81dbde3f)

![image](https://github.com/user-attachments/assets/f7964cf2-6dc3-4e3c-9fcc-d1047bde6704)

### 4.2. Windows password

![image](https://github.com/user-attachments/assets/fe8ee83b-92af-4d99-8a7b-f1ed931698f1)

![image](https://github.com/user-attachments/assets/1199f21d-4e8c-4e9d-8d11-0f55910d6ac4)

## 5. Bastion connection to VMs using key vault secrets

### 5.1. Linux

![image](https://github.com/user-attachments/assets/fa73f2a6-200e-4d4e-a30e-623e3dad538a)

### 5.2. Windows

![image](https://github.com/user-attachments/assets/ca14ac3a-9ad2-4db1-b5e3-ee93de145b8e)
