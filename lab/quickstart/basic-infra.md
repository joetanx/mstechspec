## 0. Basic infra setup

Ref: https://learn.microsoft.com/en-us/azure/nat-gateway/tutorial-hub-spoke-nat-firewall

![image](https://learn.microsoft.com/en-us/azure/nat-gateway/media/tutorial-hub-spoke-nat-firewall/resources-diagram.png)

## 1. Create resource group

![image](https://github.com/user-attachments/assets/3702d970-aad1-423e-8e07-8f35c75181fa)

![image](https://github.com/user-attachments/assets/3b02f8c5-c3e5-4988-a7f9-b062039dd568)

![image](https://github.com/user-attachments/assets/9f54fcbb-850a-4426-83c9-0522392c70ec)

![image](https://github.com/user-attachments/assets/3c248714-d08b-470d-8f64-124ab496fe6c)

## 2. Create a hub virtual network and deploy an Azure Firewall and Azure Bastion during deployment

![image](https://github.com/user-attachments/assets/64db4c98-9103-4960-bd47-b8a1d1c9be8a)

### 2.1. Virtual network security settings

![image](https://github.com/user-attachments/assets/77d2b2c6-2710-4187-9116-a136cad7347d)

#### 2.1.1. Create bastion public IP

![image](https://github.com/user-attachments/assets/6cda43a6-1ec4-4786-9f87-a41271268079)

#### 2.1.2. Create firewall policy

![image](https://github.com/user-attachments/assets/9cd9c003-9f84-4c4c-b56a-2e93463bd822)

#### 2.1.3. Create firewall public IP

![image](https://github.com/user-attachments/assets/2268c9e8-52ac-4be2-bfbd-458437621cce)

### 2.2. Virtual network IP addresses settings

![image](https://github.com/user-attachments/assets/dcde1ca0-43b4-4e50-8376-50d9abd39a7d)

### 2.3. Virtual network tags

![image](https://github.com/user-attachments/assets/458bc488-382c-4d36-ac19-ca4c96bff38e)

### 2.4. Virtual network review + create

![image](https://github.com/user-attachments/assets/6c698f08-1f73-420a-99a1-5c34c24cb4c2)

![image](https://github.com/user-attachments/assets/675e6220-621e-4a0d-97f3-f8ce038bd492)

![image](https://github.com/user-attachments/assets/00028e41-ce83-47dc-ad5d-0a1436771adb)

## 3. Create a NAT gateway and associate it with the firewall subnet in the hub virtual network

![image](https://github.com/user-attachments/assets/ff77fd61-6130-4121-be23-4ab970e7b391)

![image](https://github.com/user-attachments/assets/66b83133-aa77-4edc-a534-4d437abfc735)

![image](https://github.com/user-attachments/assets/173284a2-c433-4edc-ba63-0dcffa97e77f)

![image](https://github.com/user-attachments/assets/46dcd971-e468-43b6-8343-c0b0f9a543f1)

![image](https://github.com/user-attachments/assets/d9be1aac-cd23-4694-9724-39719b491af4)

![image](https://github.com/user-attachments/assets/891a5159-8fc8-4ffc-ac99-71fc5bb1f90e)

![image](https://github.com/user-attachments/assets/9368840e-381f-4960-9d30-120b273eb807)

## 4. Create a spoke virtual network

![image](https://github.com/user-attachments/assets/0175a1cc-1e37-4dfe-9575-57befe9f2c8e)

![image](https://github.com/user-attachments/assets/f5c473ec-2d1b-4ef8-a3e3-04c670cc6fe7)

![image](https://github.com/user-attachments/assets/58cb84ea-b83c-4172-9435-7e0e04dd908e)

![image](https://github.com/user-attachments/assets/f664cea9-b1f9-462b-ac3a-18368f85ff52)

![image](https://github.com/user-attachments/assets/c9fcb83b-e87e-4530-8ef9-471aae3f5c41)

![image](https://github.com/user-attachments/assets/2e3822c6-1b88-4ec0-aa7e-85c3dad4ffff)

![image](https://github.com/user-attachments/assets/532498c9-5ca6-42d7-94d4-9f360ce48ff3)

![image](https://github.com/user-attachments/assets/4fa532f0-75be-4f0e-9646-f1a5c9cf3250)

## 5. Create a virtual network peering

![image](https://github.com/user-attachments/assets/a2163ed3-8b89-4803-8834-5891c636af4d)

![image](https://github.com/user-attachments/assets/cf990ee6-c828-44c9-95c2-f2643081604b)

![image](https://github.com/user-attachments/assets/ffb84aad-5118-4c97-b732-4be259960368)

![image](https://github.com/user-attachments/assets/d9ebd3a0-d319-4ce3-a193-2962949bcdbe)

![image](https://github.com/user-attachments/assets/150e66d8-15cf-4d09-b8a2-c9cfaf08cd50)

## 6. Create a route table for the spoke virtual network

### 6.1. Create route table

![image](https://github.com/user-attachments/assets/bb2aaa16-7165-4d02-bc7c-c5343aedcc6a)

![image](https://github.com/user-attachments/assets/940632e8-789c-4c90-97aa-021adb7a2460)

![image](https://github.com/user-attachments/assets/014314c6-6a89-4afb-92e1-48c62e9e4abb)

![image](https://github.com/user-attachments/assets/3433da85-3575-4ca5-a9a6-ca94368b5b8b)

![image](https://github.com/user-attachments/assets/43c1ad70-a4d2-445d-a6b9-d86d80a5de90)

### 6.2. Create route

![image](https://github.com/user-attachments/assets/a4099be5-9132-477d-b536-e0f4fb66f9c8)

Check firewall private IP:

![image](https://github.com/user-attachments/assets/7599b518-0cdb-45be-8fa3-36f3150ab08c)

![image](https://github.com/user-attachments/assets/57d15dad-648d-4cbe-9cbc-ac1e26859609)

![image](https://github.com/user-attachments/assets/8e393fea-65fb-4b33-a1aa-2f6743c8b4f2)

![image](https://github.com/user-attachments/assets/9353bf24-54b0-46b5-9d20-919b3b15fae1)

### 6.3. Associate route to subnet

![image](https://github.com/user-attachments/assets/96c77692-e954-4e20-9978-bec553092527)

![image](https://github.com/user-attachments/assets/c5e54cf6-0b75-4dfa-9b85-7fc7c922fa5b)

![image](https://github.com/user-attachments/assets/d788f038-58e3-40f6-9a3c-67cb739b2a32)

![image](https://github.com/user-attachments/assets/4db46c0e-1f26-43c3-91a1-5c682c9fa6ba)

## 7. Create a firewall policy for the hub virtual network

![image](https://github.com/user-attachments/assets/31b46cfe-2078-4f4c-b279-13c065406dac)

![image](https://github.com/user-attachments/assets/0d2d1e41-4e34-440a-bdd0-357c45786aa4)

![image](https://github.com/user-attachments/assets/f8fe0705-cc84-44d8-b9ac-9df24f410152)

![image](https://github.com/user-attachments/assets/03555033-fc94-4866-8a0e-aa8af81f8758)

## 8. Create a virtual machine to test the outbound connectivity through the NAT gateway

![image](https://github.com/user-attachments/assets/3b6a23bb-b66f-4f25-842a-867bfe271b49)

![image](https://github.com/user-attachments/assets/269c2039-a9cb-4f36-9709-510003314b0c)

![image](https://github.com/user-attachments/assets/b7c1fcfb-523a-4199-af6e-8e2cdfad2442)

![image](https://github.com/user-attachments/assets/affe16be-005a-42dc-9008-ee7732243938)

![image](https://github.com/user-attachments/assets/1e409912-345e-4db2-9eb4-cb798c24612f)

![image](https://github.com/user-attachments/assets/737118c8-6b7b-45be-9a6e-1e49599be549)

![image](https://github.com/user-attachments/assets/26bccf34-d31f-4058-b81c-431dd6b942f9)

![image](https://github.com/user-attachments/assets/038cee66-d313-442b-a5ac-18369ffca155)

![image](https://github.com/user-attachments/assets/dfc47477-ad9b-436a-81aa-bf4bb298f362)

![image](https://github.com/user-attachments/assets/f81178c4-9a33-41b5-9eb2-bdf538645495)

## 9. Test connection

### 9.1. Check NAT gateway public IP

![image](https://github.com/user-attachments/assets/412b18e2-a086-4a83-ba7d-23b7897c0d0f)

### 9.2. Check bastion subnet address range

![image](https://github.com/user-attachments/assets/7bb6d541-8a04-4d77-8adc-e234dd56f522)

### 9.3. Connect to VM

![image](https://github.com/user-attachments/assets/718c99c6-9986-4446-994f-b428ead492ae)

![image](https://github.com/user-attachments/assets/ee9c090e-bf6a-4a7c-ad17-a803db98e31c)

Verify that:
1. Outbound traffic to internet uses NAT gateway
2. SSH connection is established through bastion subnet address range

![image](https://github.com/user-attachments/assets/e3747130-43c1-497d-9c4a-30f8775dc4a3)
