## 1. Setup license

![image](https://github.com/user-attachments/assets/8ad439d4-ca6b-4a17-8f8f-971faf7f4abe)

![image](https://github.com/user-attachments/assets/c9b6a3d6-6e52-46c3-8942-d0c3c88c8e5f)

![image](https://github.com/user-attachments/assets/f4cf67fc-753c-46b0-91a1-a3d2f8f5c46d)

![image](https://github.com/user-attachments/assets/1fe889ba-7ffb-4226-87b5-da479c381324)

![image](https://github.com/user-attachments/assets/3852b3ff-fe8b-400c-91d9-cf0f0e2c38e8)

## 2. Setup server certificate

### 2.1. Import server certificate

![image](https://github.com/user-attachments/assets/69158549-95ee-4e7f-b8fc-3a840fca1a7c)

![image](https://github.com/user-attachments/assets/72043460-25ec-4074-b19a-611915305446)

![image](https://github.com/user-attachments/assets/cf276e84-b70e-47d2-92da-fc550fd8b5f5)

### 2.2. Set server certificate

![image](https://github.com/user-attachments/assets/c1df823a-99f4-482f-89e2-4fd3feed256c)

![image](https://github.com/user-attachments/assets/74c051ef-d55f-471b-bdd7-11383f868a44)

### 2.3. Set device FQDN

![image](https://github.com/user-attachments/assets/0bd0734f-58ff-489b-898d-41b093170bc5)

![image](https://github.com/user-attachments/assets/a8b38d51-d087-462f-9a72-7df38711585e)

## 3. Import trusted root CA

> [!Note]
>
> Trusted root CA is needed for SMTP STARTTLS and LDAPS

![image](https://github.com/user-attachments/assets/c5e59dd2-54d6-441f-8770-b6f3e23fac91)

![image](https://github.com/user-attachments/assets/374773e6-3409-4309-bf7f-60990d1f946d)

![image](https://github.com/user-attachments/assets/333fb46f-75a9-4664-ba88-6db28bbe373f)

## 4. Setup SMTP server

![image](https://github.com/user-attachments/assets/14229a7a-b3ff-4962-887a-06de8b6fa32a)

![image](https://github.com/user-attachments/assets/375a4265-41e3-4c5b-be6f-7c28b95e2de4)

![image](https://github.com/user-attachments/assets/d7350f53-b3a7-4c2a-914c-7053b1e239ca)

![image](https://github.com/user-attachments/assets/d00bf48b-2db5-4dce-a01b-8707051eebeb)

![image](https://github.com/user-attachments/assets/1c8e4258-524b-497b-8cbd-e1b8532c34b7)

![image](https://github.com/user-attachments/assets/d3996e89-141b-44c3-a5a3-2994a0b87c30)

## 5. Setup LDAP authentication

### 5.1. Create LDAP server

![image](https://github.com/user-attachments/assets/04a752f3-8434-4276-992c-68690dd71c79)

![image](https://github.com/user-attachments/assets/64b7fc33-d383-44b0-bb26-45a2fd500ab0)

![image](https://github.com/user-attachments/assets/389f2fd9-45e6-464d-8e3f-cd6b54695ff7)

![image](https://github.com/user-attachments/assets/7f0e6e27-5542-4f44-974a-4656804f8d37)

### 5.2. Import users

![image](https://github.com/user-attachments/assets/0fe6d24a-f9ef-44ab-97dd-2246b797ddcf)

![image](https://github.com/user-attachments/assets/d4d1b4d8-e7f6-4860-9c92-b32e3d732f37)

![image](https://github.com/user-attachments/assets/5b4d8b5a-97f8-44ee-8c05-492045f19859)

![image](https://github.com/user-attachments/assets/1a0a599f-e972-4160-9615-7fdc24ac2243)

### 5.3. Configure OTP

![image](https://github.com/user-attachments/assets/e8b34f2a-3204-4839-bdcd-15bc94b4c6a1)

![image](https://github.com/user-attachments/assets/844afd08-5387-4202-8712-7f6e3be9cc16)

![image](https://github.com/user-attachments/assets/db71a47e-1057-44e0-8130-d955a674a036)

![image](https://github.com/user-attachments/assets/c5c7260b-9b37-4a0e-b969-93fab3cbbdfd)

![image](https://github.com/user-attachments/assets/8c9357d9-4d6e-4234-af91-62bf532587b5)

![image](https://github.com/user-attachments/assets/6f785351-4069-4a78-a60e-14791faec12d)

## 6. Configure SAML IdP

### 6.1. Configure realm

![image](https://github.com/user-attachments/assets/ba2cc8b3-7f84-431d-a033-fbb236e4ed0a)

![image](https://github.com/user-attachments/assets/4033674d-185a-4e8a-8bfa-b8b3142043d4)

![image](https://github.com/user-attachments/assets/9e99c694-1941-47f0-a4c0-8f63df95d49b)

### 6.2. Enable SAML IdP portal

![image](https://github.com/user-attachments/assets/96c35e93-9cb7-498c-a429-246d9b6c090f)

![image](https://github.com/user-attachments/assets/68405d03-2630-4457-b125-476db079136e)

### 6.3. Enable SAML IdP service on the network interface

![image](https://github.com/user-attachments/assets/b66635c5-1bab-4b81-9a68-7e05bf807c39)

> [!Note]
>
> Regarding 403 forbidden error on FortiAuthenticator SAML:
> 
> https://community.fortinet.com/t5/FortiAuthenticator/Troubleshooting-Tip-How-to-fix-SAML-error-403-access-to-this/ta-p/307297

# Appendix A: integration examples

## A.1. FortiClient EMS SAML authentication

### A.1.1. Create SP on FortiAuthenticator

![image](https://github.com/user-attachments/assets/8a83bff0-d693-49e1-9859-6067dd15be35)

Copy the `IdP Entity ID` and `IdP single sign-on URL` values:

![image](https://github.com/user-attachments/assets/7abfe311-e15d-4032-a007-d6b2998c77dd)

### A.1.2. Configure IdP on EMS

Use the `IdP Entity ID` and `IdP single sign-on URL` values copied from the previous SP creation step:

![image](https://github.com/user-attachments/assets/7e068d22-3201-4b92-80b7-ca79b1910973)

Copy the `SP Entity ID` and `SP ACS (login) URL` values:

![image](https://github.com/user-attachments/assets/b639b2e2-f777-441a-a409-28c8cad4103d)

### A.1.3. Complete the SP configuration on FortiAuthenticator

Use the `SP Entity ID` and `SP ACS (login) URL` values copied from the previous EMS configuration step:

![image](https://github.com/user-attachments/assets/82377e15-e9a2-4aa1-a7f7-bca1658c8230)

![image](https://github.com/user-attachments/assets/be59fee9-1ec2-4cb4-b49b-623b73051fa3)

## A.2. FortiGate Admin SAML

### A.2.1. Create SP on FortiAuthenticator

![image](https://github.com/user-attachments/assets/8a83bff0-d693-49e1-9859-6067dd15be35)

Note the `identifier` value created:

![image](https://github.com/user-attachments/assets/50726167-49f1-444b-a273-8b5e85e13395)

### A.2.2. Configure IdP on FortiGate

![image](https://github.com/user-attachments/assets/84cfc6cb-a98a-4969-8911-876178f04455)

![image](https://github.com/user-attachments/assets/d2a23fec-2bab-441d-abea-ac2a6ee81cec)

Select `Fortinet Product` and enter:
- `IdP address` - the base FQDN of FortiAuthenticator
- `Prefix` - the IdP identifier noted from the previous SP creation step
- `IdP certificate` - the SAML signing certificate (e.g. [here](https://github.com/joetanx/FortiArchitect/blob/main/lab/fac.md#62-enable-saml-idp-portal))

![image](https://github.com/user-attachments/assets/759fb6e6-2bea-435e-85ea-18323f639806)

> [!Tip]
>
> By selecting `Fortinet Product` in the IdP setting, FortiGate automatically populates the required IdP details:
>
> ![image](https://github.com/user-attachments/assets/d478b1b5-81dc-4b40-95da-3d88a166541f)

#### Optional: create SSO Admin user

The SSO Admin user can be manually pre-create or allow the user to be automatically created upon log in

![image](https://github.com/user-attachments/assets/3f6c74e3-42fd-4528-9ae0-7e2eccc69a5f)

![image](https://github.com/user-attachments/assets/22b3129e-776f-4684-8a9d-af96a1cb0bca)

![image](https://github.com/user-attachments/assets/b0d2ccbc-dae0-406f-8a3d-d802c44830dd)

### A.2.3. Complete the SP configuration on FortiAuthenticator

Use the `SP Entity ID` and `SP ACS (login) URL` values copied from the previous FortiGate configuration step:

![image](https://github.com/user-attachments/assets/c5e216df-67d2-4908-89a1-75edfa94e279)

![image](https://github.com/user-attachments/assets/89a4d81a-912f-4826-b241-64e6abb52f0a)

### A.2.4. Test login

![image](https://github.com/user-attachments/assets/60f4cfcb-4385-4610-935a-11f3122a7c73)

![image](https://github.com/user-attachments/assets/0d632b4a-8b3a-46e8-bf13-89b0d58789af)

![image](https://github.com/user-attachments/assets/1878c4c5-6dd3-40fa-b7e5-4debd20ab1f0)

![image](https://github.com/user-attachments/assets/fa8b7ec1-8421-4344-84b2-ba37fde6b644)

![image](https://github.com/user-attachments/assets/7b115fc7-765c-4e78-8003-e97635290794)

> [!Note]
>
> The SSO automatically creates the SSO Admin user if it doesn't already exist
> 
> ![image](https://github.com/user-attachments/assets/bc44360b-f2d1-4af3-acf8-1263cadcf4c0)

![image](https://github.com/user-attachments/assets/65f8a277-0622-45e7-afcf-f8270b1dc868)

### A.3. FortiGate ZTNA SAML

### A.3.1. Create SP on FortiAuthenticator

![image](https://github.com/user-attachments/assets/8a83bff0-d693-49e1-9859-6067dd15be35)

Note the `identifier` value created:

![image](https://github.com/user-attachments/assets/58efb23c-74a5-46fd-8bd3-c6f984951a91)

### A.3.2. Configure IdP on FortiGate

![image](https://github.com/user-attachments/assets/7bdb7fbd-f6d5-46bb-a61c-68df912bcbed)

Select `Fortinet Product` and enter:
- `address` - the base FQDN of FortiAuthenticator
- `Prefix` - the IdP identifier noted from the previous SP creation step
- `Certificate` - the SAML signing certificate (e.g. [here](#62-enable-saml-idp-portal))
- Also note that the `Attribute used to identify users` corresponds to the `Assertion Attributes` configured on FortiAuthenticator

![image](https://github.com/user-attachments/assets/ffb199a7-6619-4dfd-bab7-08ac578f3183)

> [!Tip]
>
> By selecting `Fortinet Product` in the IdP setting, FortiGate automatically populates the required IdP details:
>
> ![image](https://github.com/user-attachments/assets/a86dfc21-138e-4730-8416-d884945084f4)

### A.3.3. Complete the SP configuration on FortiAuthenticator

Use the `Entity ID` and `Assertion consumer service URL` values copied from the previous FortiGate configuration step:

![image](https://github.com/user-attachments/assets/ed3b2137-b107-4342-b022-be0a9db8177f)
