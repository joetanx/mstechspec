## 1. Initial login

- username: `admin`
- password: _`<blank>`_

![image](https://github.com/user-attachments/assets/0034193b-bd7e-49de-8ae9-2c037806f590)

![image](https://github.com/user-attachments/assets/3d2e4cd9-4985-4e69-807a-4d93185161b7)

## 2. Install license

![image](https://github.com/user-attachments/assets/6dcabc2b-77c0-4df6-bd17-21ff315b6c99)

![image](https://github.com/user-attachments/assets/09c8c7d1-5689-49b9-bb47-63a13559d74d)

![image](https://github.com/user-attachments/assets/a3ad8ddc-0436-4c4c-9804-75588473ff83)

## 3. Install services certificate

![image](https://github.com/user-attachments/assets/80b15ec2-c089-4616-8f1f-edea1716a29a)

![image](https://github.com/user-attachments/assets/5a3ff0c0-b8bc-4051-a25d-493a33936d52)

## 4. Configure EMS settings

|Key|Value|
|---|---|
|Hostname|`ems.net.vx`|
|Listen on IP|`All`|
|Use FQDN|`ems.net.vx`|
|Webserver certificate|`services.pem`|
|Use Webserver certificate for Endpoint Control|✅|
|FortiClient download URL|`ems.net.vx`<br>(entry will only appear in drop-down list after `Hostname` or `Use FQDN` is saved)|
|Cloud region to repackage installers|`Asia`|

![image](https://github.com/user-attachments/assets/84a2a6f9-fe64-40e6-809e-75d2cb72ce3e)

## 5. Configure SMTP server

Enter `Server` parameter and select `Auto Detect` to automatically detect the SMTP security:

![image](https://github.com/user-attachments/assets/91e8e3c3-f8ca-4c54-907d-d9d83b35a9f4)

Select `Send Test Email`:

![image](https://github.com/user-attachments/assets/2cb23658-187e-44ae-9fcc-e279d71ed6a5)

Verify test email received:

![image](https://github.com/user-attachments/assets/c19d0a57-5c78-40ad-be96-32261611d415)

Save settings:

![image](https://github.com/user-attachments/assets/f01e2fc0-19b4-4f05-94bd-8e84fe67c93e)

## 6. Configure LDAP users

### 6.1. Add ADDS authentication server

![image](https://github.com/user-attachments/assets/4d3c2030-3da8-4974-8268-555d5bf9f731)

![image](https://github.com/user-attachments/assets/aa344acc-8403-48b2-b80a-af98195899b3)

![image](https://github.com/user-attachments/assets/78bf273c-8ae5-4cc4-b76b-0b4833fdb916)

### 6.2. Add ADDS domain

![image](https://github.com/user-attachments/assets/2f61d35c-6e6f-498e-94a4-67d082f20220)

![image](https://github.com/user-attachments/assets/55c0a244-9d7a-4f85-be26-53dc7405fbec)

![image](https://github.com/user-attachments/assets/f685ff92-3409-4966-aa2a-7b167fc46409)

### 6.3. Restrict authorized user groups

Select all the groups in domain and select `Exclude`

![image](https://github.com/user-attachments/assets/a84dc3f0-f30c-467f-b4f6-0465190e36d0)

![image](https://github.com/user-attachments/assets/8f933a6d-c565-461d-a564-67631a3d8d52)

Select required groups and select `Authorize`

![image](https://github.com/user-attachments/assets/bf640f8b-e9fd-4772-bcff-854ee365bcb5)

![image](https://github.com/user-attachments/assets/3b48fbf6-0046-40d8-940d-d0cb2ed6c7a6)

![image](https://github.com/user-attachments/assets/55d5d579-fe4c-40b5-b9c3-caaee19a0d9b)

## 7. Enroll users

### 7.1. Create invitation for LDAP users

![image](https://github.com/user-attachments/assets/c95d87b9-fb12-42fc-a2da-4d7484a8ded7)

![image](https://github.com/user-attachments/assets/90996bfe-936f-4d91-8336-7b63159d7a10)

![image](https://github.com/user-attachments/assets/6997988b-1221-412c-a212-7960eab6584b)

![image](https://github.com/user-attachments/assets/fbe88f17-c47d-41a5-95f2-03fc0464d487)

![image](https://github.com/user-attachments/assets/83c6e10d-b53e-493c-ad08-78eb3a44aba2)

![image](https://github.com/user-attachments/assets/04a7e23e-f73a-44c9-b942-9d4e4f195998)

![image](https://github.com/user-attachments/assets/9fd937a1-4ef6-4e07-98e5-70587bfca8ff)

![image](https://github.com/user-attachments/assets/4624a7ee-2f56-4510-9175-8af361ae880b)

### 7.2. Create invitation for SAML users

#### 7.2.1. Configure SAML

Create SP on FortiAuthenticator:

![image](https://github.com/user-attachments/assets/17e961db-a3d5-48bc-8f9c-3f158da80bec)

![image](https://github.com/user-attachments/assets/274c9d5d-4ba5-4cac-b679-fa4be7f120bb)

Copy the `IdP Entity ID` and `IdP single sign-on URL`, use it to create IdP on EMS:

![image](https://github.com/user-attachments/assets/65d6917d-e032-4ebf-9e76-3d344f5f4f62)

![image](https://github.com/user-attachments/assets/0fed1661-10da-4c87-afe5-622613d4ef7e)

Copy the `SP Entity ID` and `SP ACS (login) URL`, complete the SP configuration on FortiAuthenticator:

![image](https://github.com/user-attachments/assets/ba7477f8-bfca-463c-acc0-396f7faa015b)

![image](https://github.com/user-attachments/assets/db71611a-d59c-4a30-9ccd-47c6d849fb9a)

### 7.2.2. Create invitation

![image](https://github.com/user-attachments/assets/d9b8cf33-8258-4937-bf8d-9353f7c6bbcc)





