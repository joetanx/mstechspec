## 1. Initial Setup

> [!Note]
>
> Default password for first login to FortiSOAR using `csadmin` is `changeme`.
>
> After first login, a password change is mandated
> 
> ![image](https://github.com/user-attachments/assets/145bd9fe-9802-48d5-a487-692f77c0f426)


![image](https://github.com/user-attachments/assets/cfd1832c-a780-4b31-85c9-071fa882a7ae)

### 1.1. Setup SMTP connector

![image](https://github.com/user-attachments/assets/a1c79c43-1864-498e-b83d-23827a034ca8)

![image](https://github.com/user-attachments/assets/71151aa2-1add-42db-b9ec-a031baa32b38)

![image](https://github.com/user-attachments/assets/5fe217af-b5e7-4e98-97af-bd9726bcab02)

![image](https://github.com/user-attachments/assets/d25838bf-26b8-418b-883d-d8f82a24ac60)

### 1.2. Setup email notifications

![image](https://github.com/user-attachments/assets/ec43c1fd-8afe-4f24-ba0d-56324b6fe518)

![image](https://github.com/user-attachments/assets/3cc3d1ea-c0a3-4a88-86df-a3b968e80d12)

![image](https://github.com/user-attachments/assets/4b35295e-dd99-419c-bfb1-7eec647f452b)

![image](https://github.com/user-attachments/assets/75e199f9-8d1a-402f-afb4-21c256a20ae3)

![image](https://github.com/user-attachments/assets/bee14ac1-3812-4352-9df7-fb66c528a70b)

![image](https://github.com/user-attachments/assets/fc002b9d-c9e1-4c3a-88e8-60f2c1763244)

![image](https://github.com/user-attachments/assets/5a137fba-68b1-47c2-b0b3-2ae17f04ffad)

#### 1.2.1. Test email notification by assigning a task

![image](https://github.com/user-attachments/assets/a334b012-7b34-4aa8-9bf8-e153e2ecd506)

![image](https://github.com/user-attachments/assets/65f239a5-6974-44d3-9c3c-b06f798639a1)

![image](https://github.com/user-attachments/assets/0eca1f89-bed5-48e3-9bbf-1423674e36b3)

### 1.3. Setup IMAP connector

![image](https://github.com/user-attachments/assets/730317ff-927d-4e54-b878-63c9717531df)

![image](https://github.com/user-attachments/assets/de6af67b-07c3-4aa9-976e-f480c8604c30)

> [!Note]
>
> The `Use TLS` and `Verify SSL` options in the IMAP connector is meant for IMAP with SSL (port 993)
>
> For IMAP with TLS (port 143), just leave these options unchecked

![image](https://github.com/user-attachments/assets/dd372ec1-3855-490a-8bb1-e5d504a42b15)

![image](https://github.com/user-attachments/assets/b059131a-28f6-41dc-9f4d-1cdc9297133e)

#### 1.3.1. Data ingestion from IMAP to retrieve emails

![image](https://github.com/user-attachments/assets/fb032966-fa2f-45bf-8966-d8247d6d99cc)

![image](https://github.com/user-attachments/assets/70fd929d-d204-4dd6-a4d6-881ce528c675)

![image](https://github.com/user-attachments/assets/857d43b6-d4e8-403e-99f8-ec8335e127f6)

> [!Note]
>
> The IMAP connector processes emails in `Inbox` and move them to `PROCESSED` according to the `Source` and `Destination` configured in the connector
>
> ![image](https://github.com/user-attachments/assets/e63bee38-4f68-4a23-b138-4ecdfea9a9e6)

![image](https://github.com/user-attachments/assets/e5061ddd-afb6-4f3c-96d7-81a79d0221ef)

![image](https://github.com/user-attachments/assets/537ee3aa-084b-4732-9265-cd6c1ca0c474)
