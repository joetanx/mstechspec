## 1. Connect FortiGate to EMS

### 1.1. Configure EMS Fabric Connector

![image](https://github.com/user-attachments/assets/558fc03a-ce79-411e-aaf7-0cb57c9f626c)

![image](https://github.com/user-attachments/assets/3c14f1e9-4729-45ed-8457-255229900935)

![image](https://github.com/user-attachments/assets/07c53aef-1e2b-4380-9f96-5b54e64574d5)

![image](https://github.com/user-attachments/assets/7ecffb41-3f65-46c7-8760-c51ef453ed02)

### 1.2. Authorize FortiGate in EMS

![image](https://github.com/user-attachments/assets/9f92a05c-7660-4964-a507-859d9501be74)

![image](https://github.com/user-attachments/assets/f382a17a-054d-4d2d-bb73-6761dc3f4790)

## 2. HTTP Access Proxy

### 2.1. Create ZTNA server

Create address record for destination server:

![image](https://github.com/user-attachments/assets/01289add-92a9-463d-8abd-81f66f54de2b)

Create ZTNA server:

![image](https://github.com/user-attachments/assets/0595a2c0-e4bc-4cff-8472-803b701e6767)

Create destination server mapping:

![image](https://github.com/user-attachments/assets/cf09534a-685f-4a99-a06e-eb6d7eea5b99)

> [!Note]
>
> Client certificate authentication is **enabled** on the access proxy **by default**.
>
> Commands `client-cert` and `empty-cert-action` can be configured on the CLI to change client certificate authentication behaviour.
>
> ```
> config firewall access-proxy
>   edit <name>
>     set client-cert { enable | disable }
>     set empty-cert-action { accept | block }
>   next
> end
> ```
> 
> `empty-cert-action` is available only if `client-cert` is set to `enable`

### 2.2. Create ZTNA firewall rule

![image](https://github.com/user-attachments/assets/3fc98ccf-86a4-489a-a603-c00867db9eef)

### 2.3. Test client certificate authentication

Incorrect client certificate prompt:

(Likely due to EMS fabric connection not configured, if EMS fabric connection is configured, only the EMS signed signed client certificate should be in the prompt)

![image](https://github.com/user-attachments/assets/b58fd056-3f9a-4499-94e6-4c831d8a0d12)

Empty client certificate:

(No certificate or cancel was selected on the prompt)

![image](https://github.com/user-attachments/assets/366b0c1a-1f99-43eb-9ed9-4142a0390d81)

Wrong certificate selected or EMS fabric connection not configured:

![image](https://github.com/user-attachments/assets/6f130a22-58ba-4bea-8273-b666f0a2e1a1)

![image](https://github.com/user-attachments/assets/a97ef800-258b-40ea-b370-0184b4cfad2a)

Successful access:

(Notice that only the EMS CA signed client certificate is in the prompt)

![image](https://github.com/user-attachments/assets/d2cdb08e-8a60-442e-9136-af1fbb77459c)

![image](https://github.com/user-attachments/assets/27e435aa-1c49-41e7-8525-78590cd0bd50)

### 2.4. Configure ZTNA authentication

Create LDAP server:

![image](https://github.com/user-attachments/assets/d14d1b0c-ad6f-463e-8a05-d5893c591225)

#### 2.4.1. LDAP authentication

Create LDAP remote user group:

![image](https://github.com/user-attachments/assets/cf8ba0b2-47cc-4c05-b6ca-682cb72156f2)

Create LDAP authentication scheme:

![image](https://github.com/user-attachments/assets/84380719-c69c-4f81-940d-df0d97205131)

Create LDAP authentication rule:

![image](https://github.com/user-attachments/assets/60a0351f-003e-49c7-83e9-9078a1f1e3bb)

#### 2.4.2. SAML authentication to FortiAuthenticator

> [!Note]
>
> Configure SAML IdP and SP as described here:
>
> https://github.com/joetanx/FortiArchitect/blob/main/lab/fac.md#a3-fortigate-ztna-saml

Create SAML remote user group:

![image](https://github.com/user-attachments/assets/497d5d03-0a7b-4a8b-87f5-2f332a3d6b5a)

Create SAML authentication scheme:

![image](https://github.com/user-attachments/assets/0f02a788-43fa-4075-bf41-c1ecc6f8d643)

Create SAML authentication rule:

![image](https://github.com/user-attachments/assets/05e244d9-0fb9-43c9-b4d4-d61c3d227d5d)

## X. EMS security tagging

### X.1. On-fabric detection rules

![image](https://github.com/user-attachments/assets/5ef279a8-3c9c-4e97-a24e-e9cec6cf238b)

![image](https://github.com/user-attachments/assets/a6e14e9c-2390-4716-b5e3-f47b13d0c529)

**Off-Fabric**:

![image](https://github.com/user-attachments/assets/88c8690d-3fa3-4344-9883-fb0ad3e23043)

**On-Fabric**:

![image](https://github.com/user-attachments/assets/90dbae3e-7e42-4852-bead-047e1539b29a)

### X.2. Configure EMS security posture tagging rules

![image](https://github.com/user-attachments/assets/06c7109c-dc52-4c85-9b9e-8576b714bc20)

![image](https://github.com/user-attachments/assets/a2e31d11-fd64-41c4-b7ba-562569c128de)

**Example 1**: Endpoints with critical vulnerabilities

![image](https://github.com/user-attachments/assets/ce9e6010-a197-4af6-8cb6-24a50e0c7e2b)

**Example 2**: Signed-in user is member of IT

![image](https://github.com/user-attachments/assets/9ef7fde5-1d18-41fc-bd03-e10301dcdd99)

Configured security posture tagging rules

![image](https://github.com/user-attachments/assets/3e550278-0e71-40a0-a156-d861b38219c8)
