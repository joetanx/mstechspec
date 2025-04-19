## 1. Create resource group

![image](https://github.com/user-attachments/assets/457723db-0e30-4245-b4ba-b6edc51af062)

![image](https://github.com/user-attachments/assets/07faad5f-c0fc-4beb-8d4b-207692a9fd53)

![image](https://github.com/user-attachments/assets/5a2af5ce-34e2-452b-bd1a-283dd1e8de7d)

![image](https://github.com/user-attachments/assets/e92c4ff1-ad68-46a9-b245-6364e2708bc6)

## 2. Create public VNet

![image](https://github.com/user-attachments/assets/7249c7d8-7e46-4994-bfe7-69fcdeb3320f)

### 2.1. Configure Bastion in security settings



### 2.2. Configure Firewall in security settings



### 2.3. Configure subnets



## 3. Create NAT gateway and associate with firewall subnet



## 4. Create private VNet



### 4.1. Configure subnets



## 5. Create peering between public and private VNets



## 6. Configure outbound routing from private subnet to internet via firewall



### 6.1. Create route table



### 6.2. Create route



### 6.3. Associate route to private subnet



## 7. Create firewall policy for public VNet



## 8. Create virtual machines to test outbound connectivity via NAT gateway



### 8.1. Ubuntu



### 8.2. Windows



## 9. Test connection



### 9.1. Check NAT gateway public IP



### 9.2. Check bastion subnet address range



### 9.3. Connect to VM



#### 9.3.1. Ubuntu



#### 9.3.2. Windows





