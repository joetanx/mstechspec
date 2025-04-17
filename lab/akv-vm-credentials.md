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

![image](https://github.com/user-attachments/assets/97996f7d-d9a6-459c-a7a5-11eba532d97f)

#### 4.1.1. Create SSH key so that it can be used to create VMs in the future

![image](https://github.com/user-attachments/assets/a1742745-f436-4122-a7b5-628a6270e818)

![image](https://github.com/user-attachments/assets/c1f224ee-ba0c-4496-8464-c8cf9f886708)

![image](https://github.com/user-attachments/assets/8ec8897d-ca74-4f27-89eb-d8a5c92c6e5e)

### 4.2. Windows password

![image](https://github.com/user-attachments/assets/2f5f92d2-271b-4a16-b2b5-992163374317)

![image](https://github.com/user-attachments/assets/68cd8ea7-4742-4716-8096-98d939f80aa3)

## 5. Bastion connection to VMs using key vault secrets

### 5.1. Linux

![image](https://github.com/user-attachments/assets/c31823e8-51e0-4d60-a290-7cfaa4e168bf)

### 5.2. Windows

![image](https://github.com/user-attachments/assets/ca14ac3a-9ad2-4db1-b5e3-ee93de145b8e)
