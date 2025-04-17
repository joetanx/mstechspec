## 1. Create security resource group

![image](https://github.com/user-attachments/assets/64362c7e-f40a-453f-8e91-037aa5126982)

![image](https://github.com/user-attachments/assets/f25f1c10-7639-4c28-8044-a361a5f3dff7)

![image](https://github.com/user-attachments/assets/9b57e1fd-ec23-4ec9-8ce5-90e76d95424f)

## 2. Create Azure key vault

![image](https://github.com/user-attachments/assets/6e853b9f-e834-4644-82bc-1d7dbb47d58a)

![image](https://github.com/user-attachments/assets/47610833-5a6b-41b3-a43c-4c253f9d2e19)

> [!Note]
>
> Secure the key vault by disabling public access or allowing only selected networks

![image](https://github.com/user-attachments/assets/d8db5e3b-b786-4dd4-bc52-2d0c215bd2cf)

![image](https://github.com/user-attachments/assets/19c5df71-caae-4905-94be-2dd493cbb1e2)

![image](https://github.com/user-attachments/assets/744cbc03-a57c-4248-9241-924f9c46bf91)

![image](https://github.com/user-attachments/assets/3d935885-dfa4-4272-ad18-50e5ac06d50e)

![image](https://github.com/user-attachments/assets/b1f72c81-a38f-4dbe-b1ec-4d084878c7f9)

## 3. Configure key vault administrator access

> [!Note]
>
> The creator of the key vault is the owner, but this doesn't grant permissions on key vault contents
>
> `Key Vault XXXX` roles are required to work on key vault contents

![image](https://github.com/user-attachments/assets/335f6433-742a-4f5e-a6ad-adf213c14974)

![image](https://github.com/user-attachments/assets/4c3280b4-9872-44f8-aad1-9aaf9842f390)

![image](https://github.com/user-attachments/assets/67eb1f45-8c85-4931-8b17-471e6968e72b)

![image](https://github.com/user-attachments/assets/26b838bd-60d4-4fb3-96bd-a80e1e872542)

![image](https://github.com/user-attachments/assets/7850c57a-8fd6-426e-8ff9-8bfab88825c7)

![image](https://github.com/user-attachments/assets/74c90cc9-ec02-467d-b9d8-3daed49cb831)

![image](https://github.com/user-attachments/assets/9768b2bc-4730-4119-8c9f-d93a82490d63)

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
