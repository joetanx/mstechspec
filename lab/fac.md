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

![image](https://github.com/user-attachments/assets/e2fd3409-0d70-405b-808f-085d4b3067ec)

![image](https://github.com/user-attachments/assets/9e55d361-1248-4416-94ac-8ce89277e5a6)

### 5.3. Configure OTP

![image](https://github.com/user-attachments/assets/aba2790a-3650-4df9-acc3-ed127ea992b0)

![image](https://github.com/user-attachments/assets/c4381906-5283-4c02-b996-8ed862f7b6ba)

![image](https://github.com/user-attachments/assets/85bf0380-d9a3-4f8a-97ac-981f542103ff)

![image](https://github.com/user-attachments/assets/9940a285-900b-4bbd-af83-11a87eb485da)

![image](https://github.com/user-attachments/assets/a632e4f9-dfbd-4d67-9b0e-0f162f14824a)

![image](https://github.com/user-attachments/assets/ff3764d1-b6c4-4e8a-ab47-b6475e85f160)

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

Copy the `IdP Entity ID` and `IdP single sign-on URL` values:

![image](https://github.com/user-attachments/assets/2d6312f5-121b-46c6-8bc0-6fc42ef3aefa)

### A.1.2. Configure IdP on EMS

Use the `IdP Entity ID` and `IdP single sign-on URL` values copied from the previous SP creation step:

![image](https://github.com/user-attachments/assets/e1269f29-962d-4552-afb3-757e1d0ef70b)

Copy the `SP Entity ID` and `SP ACS (login) URL` values:

![image](https://github.com/user-attachments/assets/5545831d-e1af-4e0f-8544-5ff736b1de20)

### A.1.3. Complete the SP configuration on FortiAuthenticator

Use the `SP Entity ID` and `SP ACS (login) URL` values copied from the previous EMS configuration step:

![image](https://github.com/user-attachments/assets/ef55c27f-d9a6-4345-a550-3e47532088d6)

![image](https://github.com/user-attachments/assets/7c970a1d-210f-4476-b603-9ed2f9295737)

## A.2. FortiGate Admin SAML

### A.2.1. Create SP on FortiAuthenticator

Note the `identifier` value created:

![image](https://github.com/user-attachments/assets/1025edb0-433e-46ac-a896-a2cb07fed3d4)

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

![image](https://github.com/user-attachments/assets/8169f7a9-58a0-456e-b2d0-ec7b26552d83)

![image](https://github.com/user-attachments/assets/e2ed4abb-34db-4f70-8164-97bd5c6db61d)

### A.2.4. Test login

![image](https://github.com/user-attachments/assets/60f4cfcb-4385-4610-935a-11f3122a7c73)

![image](https://github.com/user-attachments/assets/b04149b2-4f46-4760-8449-042d349969f2)

![image](https://github.com/user-attachments/assets/5ae5beec-e7d2-462e-87b1-d7e4cb6df1bc)

![image](https://github.com/user-attachments/assets/db1c585d-a947-4907-afdd-b2a963d90180)

![image](https://github.com/user-attachments/assets/725c261e-1330-4836-87d1-70e0e6dfbc14)

> [!Note]
>
> The SSO automatically creates the SSO Admin user if it doesn't already exist
> 
> ![image](https://github.com/user-attachments/assets/5a324a65-5b26-4067-8969-ea9cf057eda8)

![image](https://github.com/user-attachments/assets/6d0e313e-2610-463c-9e5d-e24c05b79739)

## A.3. FortiGate ZTNA SAML

### A.3.1. Create SP on FortiAuthenticator

Note the `identifier` value created:

![image](https://github.com/user-attachments/assets/b7007ada-d8af-4c55-9272-db4dd0125d05)

### A.3.2. Configure IdP on FortiGate

![image](https://github.com/user-attachments/assets/7bdb7fbd-f6d5-46bb-a61c-68df912bcbed)

Select `Fortinet Product` and enter:
- `address` - the base FQDN of FortiAuthenticator
- `Prefix` - the IdP identifier noted from the previous SP creation step
- `Certificate` - the SAML signing certificate (e.g. [here](#62-enable-saml-idp-portal))
- Also note that the `Attribute used to identify users` corresponds to the `Assertion Attributes` configured on FortiAuthenticator

![image](https://github.com/user-attachments/assets/6f979b7b-fd32-47dd-be0f-03c5a04c1438)

> [!Tip]
>
> By selecting `Fortinet Product` in the IdP setting, FortiGate automatically populates the required IdP details:
>
> ![image](https://github.com/user-attachments/assets/a86dfc21-138e-4730-8416-d884945084f4)

### A.3.3. Complete the SP configuration on FortiAuthenticator

Use the `Entity ID`, `Assertion consumer service URL` and `Single logout service URL` values copied from the previous FortiGate configuration step:

![image](https://github.com/user-attachments/assets/ed3b2137-b107-4342-b022-be0a9db8177f)

## A.4. FortiPAM

### A.4.1. Create SP on FortiAuthenticator

Note the `identifier` value created:

![image](https://github.com/user-attachments/assets/7872c55a-81e6-40d9-bdcc-af066e89e405)

### A.4.2. Configure IdP on FortiPAM

![image](https://github.com/user-attachments/assets/63ef5591-040d-42e2-a46f-9b6f3601c682)

![image](https://github.com/user-attachments/assets/b3cbbf7a-063b-4bd4-b265-59b88436b465)

![image](https://github.com/user-attachments/assets/27162010-9999-4684-a38c-48cc3aa4d957)

![image](https://github.com/user-attachments/assets/26fe7efd-8fae-4811-9475-5507be94216e)

> [!Tip]
>
> By selecting `Fortinet Product` in the IdP setting, FortiGate automatically populates the required IdP details:
>
> ![image](https://github.com/user-attachments/assets/6b9b6b09-0918-4a9a-8d81-cef193ed3e60)

### A.4.3. Complete the SP configuration on FortiAuthenticator

Use the `Entity ID`, `Portal (Sign On) URL` and `Single Logout Service (SLS) URL` values copied from the previous FortiPAM configuration step:

![image](https://github.com/user-attachments/assets/b7b19c5b-46f9-4b38-a729-f4d90de040ff)

### A.4.4. Create user group

![image](https://github.com/user-attachments/assets/bc68437a-3fee-4ac7-ab14-3f0aed0dc20a)

### A.4.6. Configure auto-provision rule

![image](https://github.com/user-attachments/assets/da68b2a3-e375-4349-a212-fa03ce843e4f)

### A.4.6. Test login

![image](https://github.com/user-attachments/assets/3d1e48e2-2c18-40aa-960d-1cac82a8d01b)

![image](https://github.com/user-attachments/assets/25168377-db37-4ead-8629-c45bf1743a49)

![image](https://github.com/user-attachments/assets/df0a77a2-1c46-47e0-8025-b67877af79f5)

![image](https://github.com/user-attachments/assets/bcd4314b-f5b1-4fd4-9c3b-7f0911008bd8)

![image](https://github.com/user-attachments/assets/188393b4-6f94-47c5-8005-ef1ccde092e8)

![image](https://github.com/user-attachments/assets/e6716f14-fd14-4720-833e-1e3a6f9b2698)

> [!Note]
>
> The auto-provision rule automatically creates the SSO user if it doesn't already exist
> 
> ![image](https://github.com/user-attachments/assets/b1e1026f-ee93-4594-92b6-70318a96cd9d)

> [!Note]
>
> A username can only use one authentication method. If a user is already provisioned under another authentication method (e.g. LDAP), login is not allowed using other methods
> 
> ![image](https://github.com/user-attachments/assets/487e4553-0b88-462d-a67f-18d9abd69c19)

## A.5. GitLab

### A.5.1. Create SP on FortiAuthenticator

GitLab supports IdP initiated login. The relay state URL is the same as the assertion consumer service (ACS) URL: `https://<gitlab-fqdn>/users/auth/saml/callback`

SAML claim mapping (assertion attributes):

|SAML attribute|User attribute|
|---|---|
|`email`|`Email`|
|`name`|`displayName`|
|`first_name`|`First Name`|
|`last_name`|`Last Name`|

Note the `IdP single sign-on URL` value, which is based on the `identifier` created:

![image](https://github.com/user-attachments/assets/0dcb143c-f884-41c7-94a6-a3f5a15ab8a2)

### A.5.2. Configure IdP on GitLab

Ref: https://docs.gitlab.com/ee/integration/saml.html

Edit `/etc/gitlab/gitlab.rb` with the following:

|Parameter|Value|Remarks|
|---|---|---|
|idp_cert_fingerprint|`<certificate-sha1-fingerprint>`|Retrieve from FAC, e.g. `openssl s_client -connect <fac-fqdn>:443 -showcerts < /dev/null | openssl x509 -noout -fingerprint`|
|idp_sso_target_url|`https://<fac-fqdn>/saml-idp/gitlab/login/`|`IdP single sign-on URL` value from earlier SP creation|
|issuer|`https://<gitlab-fqdn>/`|a.k.a. `Entity ID` of the SP|

```rb
gitlab_rails['omniauth_allow_single_sign_on'] = ['saml']
gitlab_rails['omniauth_block_auto_created_users'] = false

gitlab_rails['omniauth_providers'] = [
  {
    name: "saml",
    label: "FortiAuthenticator", # optional label for login button, defaults to "Saml"
    args: {
      assertion_consumer_service_url: "https://gitlab.net.vx/users/auth/saml/callback",
      idp_cert_fingerprint: "58:ef:41:5e:c8:ef:95:bb:d4:fb:af:b0:97:51:a6:c9:a6:d9:b1:e7",
      idp_sso_target_url: "https://fac.net.vx/saml-idp/gitlab/login/",
      issuer: "https://gitlab.net.vx/",
      name_identifier_format: "urn:oasis:names:tc:SAML:2.0:nameid-format:persistent"
    }
  }
]
```

[Reconfigure GitLab](https://docs.gitlab.com/ee/administration/restart_gitlab.html#reconfigure-a-linux-package-installation) using the `gitlab-ctl reconfigure` command

> [!Note]
>
> The SP metadata of GitLab is available at: `https://<gitlab-fqdn>/users/auth/saml/metadata`

### A.5.3. Complete the SP configuration on FortiAuthenticator

![image](https://github.com/user-attachments/assets/ab754ea9-f5d6-47d0-9c92-71d43e19df03)

### A.5.4. Test login

#### A.5.4.1. SP-initiated login

![image](https://github.com/user-attachments/assets/99559378-7b51-4665-868f-3396aa1b02ae)

![image](https://github.com/user-attachments/assets/a1bc21df-a1e9-404f-804f-a50a45458eaf)

![image](https://github.com/user-attachments/assets/a30f6108-d96e-42dd-b6b8-5a9a85154d7d)

![image](https://github.com/user-attachments/assets/dca17e9c-4edd-4b5c-a572-384570aa415e)

![image](https://github.com/user-attachments/assets/a3e4a839-ea93-4eb6-9eb8-fe96702978ad)

![image](https://github.com/user-attachments/assets/1dcb0262-1eda-4db9-9b67-2f30421be16e)

#### A.5.4.2. IdP-initiated login

FortiAuthenticator IdP-initiated login URL: `https://<fac-fqdn>/saml-idp/portal/`

![image](https://github.com/user-attachments/assets/07c0e41e-1aab-4950-9ed2-f036bcf272cc)

#### A.5.4.3. Verify automatically created user:

![image](https://github.com/user-attachments/assets/749a0e7e-1ad9-4fa9-ae36-bb0fb2a76c79)

#### A.5.4.4. Common error: `Email can't be blank`

![image](https://github.com/user-attachments/assets/6bb76f63-df3d-45b4-8276-60207ff61447)

- User that is logging in does not have an email configured
- The email SAML claim mapping is not configured correctly
