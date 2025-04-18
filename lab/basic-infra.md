## 1. Create resource group

![image](https://github.com/user-attachments/assets/457723db-0e30-4245-b4ba-b6edc51af062)

![image](https://github.com/user-attachments/assets/07faad5f-c0fc-4beb-8d4b-207692a9fd53)

![image](https://github.com/user-attachments/assets/5a2af5ce-34e2-452b-bd1a-283dd1e8de7d)

![image](https://github.com/user-attachments/assets/e92c4ff1-ad68-46a9-b245-6364e2708bc6)

## 2. Create Public VNet

![image](https://github.com/user-attachments/assets/7249c7d8-7e46-4994-bfe7-69fcdeb3320f)

### 2.1. Configure Bastion in security settings

![image](https://github.com/user-attachments/assets/484542bd-f0f4-46b2-9736-1a32b0a60e02)

![image](https://github.com/user-attachments/assets/f4c92cbf-9ce7-4c4f-851a-6363a89812c0)

### 2.2. Add outbound subnet for NAT Gateway

![image](https://github.com/user-attachments/assets/8e8cd071-1487-4ea2-8602-5907d60380e2)

![image](https://github.com/user-attachments/assets/a853a86e-17c9-4164-ac48-26b698c450a2)

### 2.3. Configure tags

![image](https://github.com/user-attachments/assets/db564885-4427-4dcc-b1c0-1d9bff5c30cb)

### 2.4. Review + create

![image](https://github.com/user-attachments/assets/5aa045c2-88b6-40b2-96f9-c5e07e9e6e2d)

![image](https://github.com/user-attachments/assets/1db2cbfb-9098-4169-bfa1-2617c35f62ab)

![image](https://github.com/user-attachments/assets/fd0a5861-c05e-4aa9-910e-e3ceff22eda4)

## 3. Create a NAT gateway and associate it with the public VNet outbound subnet

![image](https://github.com/user-attachments/assets/c4f3528f-326e-420f-934f-4dc89b0e18e1)

![image](https://github.com/user-attachments/assets/e67208ca-e2a7-4d77-9c71-035020df56bd)

![image](https://github.com/user-attachments/assets/bb7a9221-c7e2-4983-b484-fb6463a4c2b2)

![image](https://github.com/user-attachments/assets/4a4799ce-2f27-4dea-a5ba-10fcf62020fa)

![image](https://github.com/user-attachments/assets/e3a0e565-3c9a-4f65-a83a-611b3f71b1f2)

![image](https://github.com/user-attachments/assets/41670c15-c8c7-4fa8-b8bd-0a674965f8e2)

![image](https://github.com/user-attachments/assets/f002ed9e-48dc-4d2b-8530-d9c758b52979)

## 4. Create Private VNet

![image](https://github.com/user-attachments/assets/e5ceb9eb-0c31-4261-a370-40549a84417c)

![image](https://github.com/user-attachments/assets/4c770891-9d12-43a0-80b2-ede2bbac4e5f)

![image](https://github.com/user-attachments/assets/7289ca1d-88be-4424-9181-efe2c7d2ad99)

![image](https://github.com/user-attachments/assets/fc84d822-49ef-4383-bb33-88685caffe09)

![image](https://github.com/user-attachments/assets/7d027da9-001b-45b2-bd88-5b4a677f6413)

![image](https://github.com/user-attachments/assets/34eebb08-592a-4b60-a789-42798ad41778)

![image](https://github.com/user-attachments/assets/53d11a18-bac0-4fc8-b652-603b685b0a56)

![image](https://github.com/user-attachments/assets/00626179-e685-4573-9891-fbb1d0377967)

## 5. Create peering between public and private VNets

![image](https://github.com/user-attachments/assets/5ff1604d-b788-48a4-949a-79cec666763a)

![image](https://github.com/user-attachments/assets/13b885cf-d80b-4c18-88a9-683eaa0a0335)

![image](https://github.com/user-attachments/assets/5d2aa1ce-36a7-4406-bc70-43018245d1b8)

![image](https://github.com/user-attachments/assets/e9788dca-fcb3-408d-a237-8e2efaa2b4e4)

![image](https://github.com/user-attachments/assets/bbcb5016-f1ae-490f-8d37-aa87ae9ab676)

## 6. Configure outbound routing from private subnet to internet via NAT Gateway

### 6.1. Create route table

![image](https://github.com/user-attachments/assets/6bd3dca9-5f86-4c5c-9e57-43014ec65545)

![image](https://github.com/user-attachments/assets/1a178ce5-6331-497c-9d60-07a8ea7cd30b)

![image](https://github.com/user-attachments/assets/8cdecfc9-f8c1-4555-a2cd-4025310141a7)

![image](https://github.com/user-attachments/assets/432ba85e-8dea-4d1e-8b2d-b814c50ed50e)

![image](https://github.com/user-attachments/assets/ca203055-3b77-48db-bab5-c711fb1d317d)

### 6.2. Create route

![image](https://github.com/user-attachments/assets/f57d288b-6b35-429d-a1a1-b2117546510b)

![image](https://github.com/user-attachments/assets/a4371d8e-72af-4115-82c6-2f2dfda00c79)

![image](https://github.com/user-attachments/assets/41d94088-6f18-43a5-8495-78dea213c39b)

![image](https://github.com/user-attachments/assets/edd485e7-8390-4bef-bf7d-1fe890e430bd)

### 6.3. Associate route to subnet

![image](https://github.com/user-attachments/assets/756dd279-f5fc-449d-af7e-a662a6d8d517)

![image](https://github.com/user-attachments/assets/16a40f72-14f7-45ba-9d41-fceb48746849)

![image](https://github.com/user-attachments/assets/9f974841-174b-455a-ad6e-c7d6ecef65f8)

![image](https://github.com/user-attachments/assets/bcb82a9e-3986-4e8d-9012-2805eae4f01d)

## 8. Create a virtual machine to test the outbound connectivity through the NAT gateway

### 8.1. Ubuntu

![image](https://github.com/user-attachments/assets/5895d68a-bc8c-4a44-9cb7-e070d71eeddf)

![image](https://github.com/user-attachments/assets/991981f6-08f6-4d3d-96ec-0a0709431376)

![image](https://github.com/user-attachments/assets/58978bb7-c901-4f9e-b2ac-664ed18a6543)

![image](https://github.com/user-attachments/assets/2192d148-21ec-4a89-982f-a02756cf88f9)

![image](https://github.com/user-attachments/assets/744f47ef-a782-4fd2-911d-72ce84da424e)

![image](https://github.com/user-attachments/assets/47dd5f2d-4e4a-42b1-8d55-0ea05c8f5900)

![image](https://github.com/user-attachments/assets/e46ffc14-b3d9-4af8-a7bb-5e5055e8a10d)

![image](https://github.com/user-attachments/assets/3786d0ab-5186-4868-8b77-330236ab54f9)

![image](https://github.com/user-attachments/assets/038cee66-d313-442b-a5ac-18369ffca155)

![image](https://github.com/user-attachments/assets/bffe4345-77e7-4a3a-98dc-6a6afc36547c)

![image](https://github.com/user-attachments/assets/b21d98f7-a34d-4272-985b-af3616b3ebe4)

## 9. Test connection

### 9.1. Check NAT gateway public IP

![image](https://github.com/user-attachments/assets/ece98aec-bea2-478c-97cb-3b318be93dc6)

### 9.2. Check bastion subnet address range

![image](https://github.com/user-attachments/assets/affae4ca-f339-4bc3-83f2-5ef34f287899)

### 9.3. Connect to VM

Verify that:
1. Outbound traffic to internet uses NAT gateway
2. SSH connection is established through bastion subnet address range

#### 9.3.1. Ubuntu



<details><summary><h1>ARCHIVED WIP</h1></summary>

### 8.2. Windows

![image](https://github.com/user-attachments/assets/34fb93c4-7c3d-435a-b0c7-fc3a972ecfa9)

![image](https://github.com/user-attachments/assets/754226ec-e095-4a5c-9dda-6e66e969c782)

![image](https://github.com/user-attachments/assets/5a0d9cce-fccc-4a3c-b446-1729ede55f0b)

![image](https://github.com/user-attachments/assets/bc22a40b-2d13-448c-abf9-9513497f3805)

![image](https://github.com/user-attachments/assets/3381f0a7-fc16-4e6d-ab26-a0857b83a4bc)

![image](https://github.com/user-attachments/assets/380e3268-fb50-47c8-9d7a-bd3ba22dd544)

![image](https://github.com/user-attachments/assets/722e3867-14af-41fd-a2f6-83ed5c4e19ff)

![image](https://github.com/user-attachments/assets/b16eb765-0d57-4d26-a9a2-64c02f1d5694)

![image](https://github.com/user-attachments/assets/117e9e58-6926-4f43-a7af-e6190ca5d706)

![image](https://github.com/user-attachments/assets/fe2b69af-50bf-4cf8-bb6d-76e9ffa6562c)

### 9.3. Connect to VM

Verify that:
1. Outbound traffic to internet uses NAT gateway
2. SSH connection is established through bastion subnet address range

#### 9.3.1. Ubuntu

![image](https://github.com/user-attachments/assets/718c99c6-9986-4446-994f-b428ead492ae)

![image](https://github.com/user-attachments/assets/ee9c090e-bf6a-4a7c-ad17-a803db98e31c)

![image](https://github.com/user-attachments/assets/e3747130-43c1-497d-9c4a-30f8775dc4a3)

#### 9.3.2. Windows

![image](https://github.com/user-attachments/assets/b3bb3aca-b809-4082-86d8-6c71df88908e)

![image](https://github.com/user-attachments/assets/a451c810-201e-4770-b700-8722f8498c34)

![image](https://github.com/user-attachments/assets/1b33ee0d-cf3e-42de-9269-ba68f182908d)

</details>

<details><summary><h1>ARCHIVED DONE</h1></summary>

## 0. Basic infra setup

Ref: https://learn.microsoft.com/en-us/azure/nat-gateway/tutorial-hub-spoke-nat-firewall

![image](https://learn.microsoft.com/en-us/azure/nat-gateway/media/tutorial-hub-spoke-nat-firewall/resources-diagram.png)

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

</details>

<details><summary><h1>ARCHIVED OBSELETE</h1></summary>

### 6.4. Create network security group

![image](https://github.com/user-attachments/assets/5b4c6bb1-d811-4bcf-a632-a21cf5c73e4a)

![image](https://github.com/user-attachments/assets/8e428286-2028-4270-9b76-8653c010d13b)

![image](https://github.com/user-attachments/assets/1499d5aa-b437-4967-8a96-6d733e4d4ad0)

![image](https://github.com/user-attachments/assets/11960251-eab3-4a4f-8a8b-8465541f118a)

![image](https://github.com/user-attachments/assets/8646ccb9-3186-4982-9b31-59573b4cf774)

![image](https://github.com/user-attachments/assets/059cc144-64df-4a15-8be2-954351c8c617)

### 6.5. Associate NSG with private VNet

![image](https://github.com/user-attachments/assets/569c7e7d-e87a-4428-81d0-7e61d79820fa)

![image](https://github.com/user-attachments/assets/36a81ed1-d169-481d-bad3-46a926724ab4)

![image](https://github.com/user-attachments/assets/b28adaaf-c3c3-465e-996f-ccd39c135eb9)

![image](https://github.com/user-attachments/assets/c46f9063-8c45-44a2-ab82-0deaef5c7b57)

</details>
