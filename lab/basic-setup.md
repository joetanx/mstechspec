## 0. Basic environment setup

Ref: https://learn.microsoft.com/en-us/azure/nat-gateway/tutorial-hub-spoke-nat-firewall

![image](https://learn.microsoft.com/en-us/azure/nat-gateway/media/tutorial-hub-spoke-nat-firewall/resources-diagram.png)

## 1. Create resource group

![image](https://github.com/user-attachments/assets/cf6c62a4-7216-489d-b2bd-f02a2fb3fa61)

![image](https://github.com/user-attachments/assets/7062dfbc-037c-40a8-b077-6f7dbfb0d447)

![image](https://github.com/user-attachments/assets/30fccde8-1283-40c4-b722-c2be8350ad02)

## 2. Create a hub virtual network and deploy an Azure Firewall and Azure Bastion during deployment

![image](https://github.com/user-attachments/assets/54f66c04-1898-45f1-a140-08f3f14052cf)

![image](https://github.com/user-attachments/assets/f92a9c47-5453-4022-a25f-aa8d874bd952)

![image](https://github.com/user-attachments/assets/936f5fae-4745-4e2c-94af-3b848f476717)

![image](https://github.com/user-attachments/assets/65370d73-a29e-49f1-a1d0-848c0340319a)

![image](https://github.com/user-attachments/assets/0acd9608-2eb1-477d-b93f-b780c84d5984)

![image](https://github.com/user-attachments/assets/b247bda4-51f5-4b77-87b5-70f041f23459)

![image](https://github.com/user-attachments/assets/bb1afe34-cd7b-43fd-a3dd-43c60798adcc)

![image](https://github.com/user-attachments/assets/45b8e53c-223d-4adc-a2bc-fc61cfcb3d3a)

![image](https://github.com/user-attachments/assets/a255567d-4802-400d-8751-7e6814b64d27)

## 3. Create a NAT gateway and associate it with the firewall subnet in the hub virtual network

![image](https://github.com/user-attachments/assets/6bd40221-0307-431e-8d7b-3d694ef41fe1)

![image](https://github.com/user-attachments/assets/2c2c2401-5483-4f18-ab5c-38e6e2327840)

![image](https://github.com/user-attachments/assets/a41960d1-9285-4346-90ee-49445a383cad)

![image](https://github.com/user-attachments/assets/c43f8e6f-0614-4697-823d-185ab04840ba)

![image](https://github.com/user-attachments/assets/5aa03bf6-6010-4f45-a26f-049118844845)

![image](https://github.com/user-attachments/assets/e4e33d95-6936-478a-82d6-9936de7a49f7)

## 4. Create a spoke virtual network

![image](https://github.com/user-attachments/assets/f15114e0-eb71-4fd3-8a7a-05f810e6267b)

![image](https://github.com/user-attachments/assets/6b0f8df8-5a50-42ae-bccd-26593565460c)

![image](https://github.com/user-attachments/assets/d9377145-e8c4-40e4-abf2-d9e3bedc62d0)

![image](https://github.com/user-attachments/assets/df4c5da6-9172-40b1-a832-95045d061f46)

![image](https://github.com/user-attachments/assets/7f74962c-bec2-4209-a6da-760de51c590c)

![image](https://github.com/user-attachments/assets/af90307f-ea10-42f0-a7c3-c400300f398e)

## 5. Create a virtual network peering

![image](https://github.com/user-attachments/assets/33ef2e32-1045-475b-a752-f10f81bdd5b1)

![image](https://github.com/user-attachments/assets/49f366d6-8bae-468c-ab8e-ed543f287dfd)

![image](https://github.com/user-attachments/assets/c90ff932-2ffe-4a95-98ae-5de20348b749)

![image](https://github.com/user-attachments/assets/9d48ef5e-a682-4456-ab02-37b6bf98d05e)

## 6. Create a route table for the spoke virtual network

![image](https://github.com/user-attachments/assets/2d29fbcd-a9cb-484d-bb32-86edfb73a8cb)

![image](https://github.com/user-attachments/assets/d68fc89d-8784-457b-b268-9acfc6ac39b3)

![image](https://github.com/user-attachments/assets/ac75279f-3350-4946-824c-f1d499144078)

![image](https://github.com/user-attachments/assets/1a3c8f8a-074d-4922-9783-95a55f74914d)

![image](https://github.com/user-attachments/assets/85a2f546-17ff-4347-8d6f-38ec33c64152)

![image](https://github.com/user-attachments/assets/ea450282-9517-4c56-9e24-53bf286e30db)

![image](https://github.com/user-attachments/assets/b968edc7-806e-45b1-befd-2af4594f24c9)

![image](https://github.com/user-attachments/assets/8010352b-62db-4272-a8ad-e3ce01c1d9f6)

![image](https://github.com/user-attachments/assets/18cde194-6a19-4518-a882-07fa1344e39f)

![image](https://github.com/user-attachments/assets/cad696a1-6169-42db-8853-ed96b97a6cad)

![image](https://github.com/user-attachments/assets/4b9dfe7c-bfa7-4cc9-8597-69799335efad)

## 7. Create a firewall policy for the hub virtual network

![image](https://github.com/user-attachments/assets/36548fbc-fb39-42e4-82b4-2f47d5d8d4ca)

![image](https://github.com/user-attachments/assets/dbf73f6d-9df2-409f-a15f-eddd32a88f6d)

## 8. Create a virtual machine to test the outbound connectivity through the NAT gateway

![image](https://github.com/user-attachments/assets/7f5bd329-495c-41a8-a27b-105d45635376)

![image](https://github.com/user-attachments/assets/0a4d51b6-5dcd-4e4e-9a40-6306cea384d6)

![image](https://github.com/user-attachments/assets/e4920a37-34c7-4af5-9057-74d3a88a24eb)

![image](https://github.com/user-attachments/assets/0c3243a4-69a3-4837-bcd9-b0c47fc78520)

![image](https://github.com/user-attachments/assets/9f33a882-cef0-4b90-8d40-81a5b6e80259)

![image](https://github.com/user-attachments/assets/2a36c87e-0ca9-4181-97c8-3e4e6b04d04d)

![image](https://github.com/user-attachments/assets/f7bec0cb-fa86-45e5-a255-a2c16766f72a)

![image](https://github.com/user-attachments/assets/ac6eb5ca-7710-4436-930c-47e6f7441f0f)

![image](https://github.com/user-attachments/assets/3f4786ac-375c-4b41-bb3a-4307ba0f3b82)
