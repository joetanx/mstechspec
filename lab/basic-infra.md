## 1. Create resource group

![image](https://github.com/user-attachments/assets/457723db-0e30-4245-b4ba-b6edc51af062)

![image](https://github.com/user-attachments/assets/07faad5f-c0fc-4beb-8d4b-207692a9fd53)

![image](https://github.com/user-attachments/assets/5a2af5ce-34e2-452b-bd1a-283dd1e8de7d)

![image](https://github.com/user-attachments/assets/e92c4ff1-ad68-46a9-b245-6364e2708bc6)

## 2. Create public VNet

![image](https://github.com/user-attachments/assets/7249c7d8-7e46-4994-bfe7-69fcdeb3320f)

### 2.1. VNet security settings

#### 2.1.1. Bastion

![image](https://github.com/user-attachments/assets/484542bd-f0f4-46b2-9736-1a32b0a60e02)

#### 2.1.2. Firewall

![image](https://github.com/user-attachments/assets/4f087b34-f97b-4216-80fc-414d16465ad1)

![image](https://github.com/user-attachments/assets/8e786a0a-0322-4170-aad0-c93a099e18f7)

#### 2.1.3. Review security settings

![image](https://github.com/user-attachments/assets/feb94da4-383f-4312-bee1-40d77af8ce65)

### 2.2. Configure subnets

![image](https://github.com/user-attachments/assets/beba1ddf-bf72-4428-8aa1-3f3356f2a245)

### 2.3. Configure tags

![image](https://github.com/user-attachments/assets/7f84d5e7-a912-43ca-bd2b-c715b87341a8)

### 2.4. Review + create

![image](https://github.com/user-attachments/assets/9a1cfd1c-a7c6-4ae4-b36f-2c5e922de74a)

![image](https://github.com/user-attachments/assets/b1ccdf6c-fa80-45a0-ab9d-58362cf23d4c)

![image](https://github.com/user-attachments/assets/6c61268f-fbe4-4099-85c2-0acb63e98902)

## 3. Create NAT gateway

![image](https://github.com/user-attachments/assets/5a2d4e72-3fa9-4965-a7b4-ea88d5913b2f)

### 3.1. Configure outbound IP address

![image](https://github.com/user-attachments/assets/c7cbc3b0-4ceb-4ef6-a4e0-99421fcdc9cc)

### 3.2. Associate with firewall subnet

![image](https://github.com/user-attachments/assets/7836f761-a003-459e-b345-76ce477e7079)

### 3.3. Configure tags

![image](https://github.com/user-attachments/assets/bbf26023-12df-4b5a-a48b-a41522d542f8)

### 3.4. Review + create

![image](https://github.com/user-attachments/assets/66be3f70-6fa0-4a78-aed0-893a6dd32a38)

![image](https://github.com/user-attachments/assets/57bf7c87-df35-4d9d-b4bb-a3b16a04340f)

![image](https://github.com/user-attachments/assets/2b5a386a-6042-4d47-b714-e9771e66d661)

## 4. Create private VNet

![image](https://github.com/user-attachments/assets/e5ceb9eb-0c31-4261-a370-40549a84417c)

### 4.1. VNet security settings

![image](https://github.com/user-attachments/assets/4c770891-9d12-43a0-80b2-ede2bbac4e5f)

### 4.2. Configure subnets

![image](https://github.com/user-attachments/assets/7289ca1d-88be-4424-9181-efe2c7d2ad99)

![image](https://github.com/user-attachments/assets/fc84d822-49ef-4383-bb33-88685caffe09)

### 4.3. Configure tags

![image](https://github.com/user-attachments/assets/7d027da9-001b-45b2-bd88-5b4a677f6413)

### 4.4. Review + create

![image](https://github.com/user-attachments/assets/c1632597-e730-4cc1-992e-3d685f43f159)

![image](https://github.com/user-attachments/assets/4c9c0209-6e55-4f3e-aa69-0b764c5cc28a)

![image](https://github.com/user-attachments/assets/bc76e4a0-4e84-41f4-860e-6a8b791d82bd)

## 5. Create peering between public and private VNets

![image](https://github.com/user-attachments/assets/a2163ed3-8b89-4803-8834-5891c636af4d)

### 5.1. Configure peering settings

VNet peering can be initiated from either VNet:
- Remote VNet: the VNet peer (`PrvVNet` in this example) to be initiated towards
- Local VNet the current VNet (`PubNet` in this example) that the configuration is initiated from

![image](https://github.com/user-attachments/assets/066fd3f9-8c72-4efd-b2d7-936d2bb05842)

### 5.2. Verify peering sync status and peering state

![image](https://github.com/user-attachments/assets/29ad91eb-eb9b-4175-8cc4-567e63632c67)

![image](https://github.com/user-attachments/assets/d3594a3e-16d5-49ff-97cc-5e7314f31109)

![image](https://github.com/user-attachments/assets/3924512f-2b3d-4169-9823-620ec8f7d3ed)

## 6. Configure outbound routing from private subnet to internet via firewall

### 6.1. Create route table

![image](https://github.com/user-attachments/assets/6bd3dca9-5f86-4c5c-9e57-43014ec65545)

![image](https://github.com/user-attachments/assets/1a178ce5-6331-497c-9d60-07a8ea7cd30b)

![image](https://github.com/user-attachments/assets/8cdecfc9-f8c1-4555-a2cd-4025310141a7)

![image](https://github.com/user-attachments/assets/f9898916-77b4-4c8a-8967-bc2d0388e144)

![image](https://github.com/user-attachments/assets/d6b337e7-96b6-4df9-b967-24c287e94876)

### 6.2. Create route

![image](https://github.com/user-attachments/assets/f57d288b-6b35-429d-a1a1-b2117546510b)

### 6.2.1. Check firewall IP address

![image](https://github.com/user-attachments/assets/db68cbbc-5eb1-49e8-aee7-ccf9e6119cb9)

### 6.2.2. Add route

- Default (Internet) route: `0.0.0.0/0`
- Next hop address: firewall address `10.0.1.68`

![image](https://github.com/user-attachments/assets/030fcd55-eb7f-4084-b604-391621b2d134)

![image](https://github.com/user-attachments/assets/f1f446cd-f34f-42ee-8866-1039414bfe09)

![image](https://github.com/user-attachments/assets/e7254ee0-046b-4033-8724-9b0ec0be4dc4)

### 6.3. Associate route table to private subnet

![image](https://github.com/user-attachments/assets/756dd279-f5fc-449d-af7e-a662a6d8d517)

![image](https://github.com/user-attachments/assets/16a40f72-14f7-45ba-9d41-fceb48746849)

![image](https://github.com/user-attachments/assets/9f974841-174b-455a-ad6e-c7d6ecef65f8)

![image](https://github.com/user-attachments/assets/bcb82a9e-3986-4e8d-9012-2805eae4f01d)

## 7. Create firewall policy for public VNet

![image](https://github.com/user-attachments/assets/7d7eba10-c1b9-4f81-a696-a43102c68c58)

![image](https://github.com/user-attachments/assets/d811a4de-2a0d-48e4-bf58-9b2b0448c005)

![image](https://github.com/user-attachments/assets/de4802f7-6cea-4ff6-a30d-80528c889019)

![image](https://github.com/user-attachments/assets/bfa8311c-c0d8-4be5-86c8-96a8c4c388eb)

## 8. Create virtual machines to test outbound connectivity via NAT gateway

### 8.1. Ubuntu

#### 8.1.1. Configure instance details and credentials

![image](https://github.com/user-attachments/assets/5895d68a-bc8c-4a44-9cb7-e070d71eeddf)

#### 8.1.2. Review disks details

![image](https://github.com/user-attachments/assets/991981f6-08f6-4d3d-96ec-0a0709431376)

#### 8.1.3. Configure networking

![image](https://github.com/user-attachments/assets/58978bb7-c901-4f9e-b2ac-664ed18a6543)

![image](https://github.com/user-attachments/assets/2192d148-21ec-4a89-982f-a02756cf88f9)

![image](https://github.com/user-attachments/assets/744f47ef-a782-4fd2-911d-72ce84da424e)

#### 8.1.4. Configure instance management settings

![image](https://github.com/user-attachments/assets/47dd5f2d-4e4a-42b1-8d55-0ea05c8f5900)

#### 8.1.5. Review + create

![image](https://github.com/user-attachments/assets/7a5eea8e-88e6-45cf-8429-87dc52e2cc9b)

![image](https://github.com/user-attachments/assets/a1fa2c09-597c-4a74-bd3a-5305897e92eb)

![image](https://github.com/user-attachments/assets/3749df12-8b6a-40d6-82aa-19bbca0bd9d6)

### 8.2. Windows

#### 8.2.1. Configure instance details and credentials

![image](https://github.com/user-attachments/assets/ac9f2b8e-c817-4725-b6e4-2a32996f7fc9)

#### 8.2.2. Review disks details

![image](https://github.com/user-attachments/assets/24554201-28a3-4242-9a8e-ead3c9f50949)

#### 8.2.3. Configure networking

![image](https://github.com/user-attachments/assets/905580f9-8137-49bb-bd22-0f2255a85b01)

![image](https://github.com/user-attachments/assets/79df5cf3-842b-4d0e-8eba-5d01635fff08)

![image](https://github.com/user-attachments/assets/e85cf86d-a60c-4dfe-8d5f-596f6d14c75e)

#### 8.2.4. Configure instance management settings

![image](https://github.com/user-attachments/assets/fb10afd3-f078-47dd-b93e-0f6e95a54e5b)

#### 8.2.5. Review + create

![image](https://github.com/user-attachments/assets/cd84a224-582f-40f4-8a36-e539f0c6c842)

![image](https://github.com/user-attachments/assets/9c763c7a-2ff6-485a-afb1-a73ef43454ae)

![image](https://github.com/user-attachments/assets/beeb2ac9-72fc-4a20-aac7-a892253d6101)

## 9. Test connection

### 9.1. Check NAT gateway public IP

![image](https://github.com/user-attachments/assets/bf45f47d-d21e-4326-a8ef-82521736a2fb)

### 9.2. Check bastion subnet address range

![image](https://github.com/user-attachments/assets/affae4ca-f339-4bc3-83f2-5ef34f287899)

### 9.3. Connect to VM

Verify that:
1. Outbound traffic to internet uses NAT gateway
2. SSH/RDP access to VM is established through bastion subnet address range

#### 9.3.1. Ubuntu

![image](https://github.com/user-attachments/assets/52ed9cc5-ec90-47c5-8c07-872685af040b)

![image](https://github.com/user-attachments/assets/8894ee06-b639-457e-8b1a-ba4ec6dc69f3)

#### 9.3.2. Windows

![image](https://github.com/user-attachments/assets/7b34dc08-dcac-4ad9-b841-d485ec013dc8)

![image](https://github.com/user-attachments/assets/f13f4915-430f-45ee-908a-8436f2ce0f61)
