## 1. Connect FortiGate to EMS

### 1.1. Configure EMS Fabric Connector

![image](https://github.com/user-attachments/assets/558fc03a-ce79-411e-aaf7-0cb57c9f626c)

![image](https://github.com/user-attachments/assets/3c14f1e9-4729-45ed-8457-255229900935)

![image](https://github.com/user-attachments/assets/07c53aef-1e2b-4380-9f96-5b54e64574d5)

![image](https://github.com/user-attachments/assets/7ecffb41-3f65-46c7-8760-c51ef453ed02)

### 1.2. Authorize FortiGate in EMS

![image](https://github.com/user-attachments/assets/9f92a05c-7660-4964-a507-859d9501be74)

![image](https://github.com/user-attachments/assets/f382a17a-054d-4d2d-bb73-6761dc3f4790)

<details><summary><h3>Authorize via fabric login</h3></summary>

![image](https://github.com/user-attachments/assets/d3b1ddcb-ca38-40d9-8968-77932213f20e)

![image](https://github.com/user-attachments/assets/aa5a0312-e1bd-4207-807d-bf1f79c2ab84)

</details>

## 2. Create ZTNA server

### 2.1. Create address records for destination servers

![image](https://github.com/user-attachments/assets/01289add-92a9-463d-8abd-81f66f54de2b)

![image](https://github.com/user-attachments/assets/e026a521-4df5-49c6-98e4-64be35edd6c2)

### 2.2. Create ZTNA server

![image](https://github.com/user-attachments/assets/b9d841ce-e020-46ce-98e8-6481f51c7abe)

### 2.3. Create destination server mapping:

#### 2.3.1. HTTP access proxy

![image](https://github.com/user-attachments/assets/cf09534a-685f-4a99-a06e-eb6d7eea5b99)

#### 2.3.2. TCP forwarding access proxy

![image](https://github.com/user-attachments/assets/7d04494e-3922-46d0-ae09-b078c6a0f488)

The ZTNA server creation page allows adding of only 1 real server for TCP Forwarding, the option gets greyed out after adding the first server:

![image](https://github.com/user-attachments/assets/a62e5e91-91c8-41c1-b8e2-e572d5742afa)

Use CLI to add additional servers for TCP Forwarding:

```
config firewall access-proxy
edit ztna-server
config api-gateway
edit 2
config realservers
edit 2
set address file.net.vx
set mappedport 445 3389 
next
end
next
end
next
end
```

After adding a second real server, the UI changes to allow adding of more servers to the list:

![image](https://github.com/user-attachments/assets/c316495a-f4bb-4f3f-a676-18a7600ad856)

![image](https://github.com/user-attachments/assets/3550e007-510d-4147-9150-9f11d13cf599)

#### 2.4. Create ZTNA firewall rule

![image](https://github.com/user-attachments/assets/feda6e68-914d-4b0c-8246-6832092d9675)

## 3. Test client certificate authentication

### 3.1. Enabling client certificate authentication

Client certificate authentication is **enabled** on the access proxy **by default**.

Commands `client-cert` and `empty-cert-action` can be configured on the CLI to change client certificate authentication behaviour.

```
config firewall access-proxy
  edit <name>
    set client-cert { enable | disable }
    set empty-cert-action { accept | block }
  next
end
```

> [!Note]
>
> `empty-cert-action` is available only if `client-cert` is set to `enable`

### 3.2. Incorrect client certificate prompt:

Likely due to EMS fabric connection not configured.

If EMS fabric connection is configured, only the EMS CA signed client certificate should appear in the prompt.

![image](https://github.com/user-attachments/assets/39958406-c14b-4d80-8920-ad875304769f)

### 3.3. Empty client certificate:

No certificate or cancel was selected on the prompt.

![image](https://github.com/user-attachments/assets/e2cb6848-69b4-45d0-b42c-a2f107d87596)

### 3.4. Invalid client certificate:

Wrong certificate selected or EMS fabric connection not configured.

![image](https://github.com/user-attachments/assets/8ee38784-1994-422f-a4a5-678145ceed39)

![image](https://github.com/user-attachments/assets/cb6b27f0-d85f-4fdd-b191-5409286578bb)

### 3.5. Successful access

Notice that only the EMS CA signed client certificate appears in the prompt.

![image](https://github.com/user-attachments/assets/74d1b945-afd7-4d04-b88d-025b2eef7e8a)

![image](https://github.com/user-attachments/assets/7a441fea-878f-4bf4-9c4e-d13be4f9e1e4)

## 4. Configure LDAP authentication

### 4.1. Create LDAP server:

![image](https://github.com/user-attachments/assets/d14d1b0c-ad6f-463e-8a05-d5893c591225)

### 4.2. Create LDAP remote user group:

![image](https://github.com/user-attachments/assets/9e66b2c4-f543-4f9a-8a82-7fe95f459f3f)

### 4.3. Create LDAP authentication scheme:

![image](https://github.com/user-attachments/assets/84380719-c69c-4f81-940d-df0d97205131)

### 4.4. Create LDAP authentication rule:

![image](https://github.com/user-attachments/assets/60a0351f-003e-49c7-83e9-9078a1f1e3bb)

### 4.5. Add the LDAP remote user group to `Source` in the ZTNA firewall rule:

![image](https://github.com/user-attachments/assets/e334211b-fc32-475f-8932-8efdc123e975)

### 4.6. Test access:

![image](https://github.com/user-attachments/assets/8519a6c3-6b1c-4827-9e64-40a55f9d6325)

![image](https://github.com/user-attachments/assets/7a441fea-878f-4bf4-9c4e-d13be4f9e1e4)

## 5. SAML authentication to FortiAuthenticator

> [!Note]
>
> Configure SAML IdP and SP as described here:
>
> https://github.com/joetanx/FortiArchitect/blob/main/lab/fac.md#a3-fortigate-ztna-saml

### 5.1. Create SAML remote user group:

![image](https://github.com/user-attachments/assets/345f0958-8cb1-46cc-acb2-b3af7e1dad1e)

### 5.2. Create SAML authentication scheme:

![image](https://github.com/user-attachments/assets/d6b9146c-d8a0-4d1f-afff-2249ac2f883d)

### 5.3. Create SAML authentication rule:

![image](https://github.com/user-attachments/assets/05e244d9-0fb9-43c9-b4d4-d61c3d227d5d)

### 5.4. Enable SAML in ZTNA server:

![image](https://github.com/user-attachments/assets/11776a54-45b6-407e-8c01-ec0c52ad9b92)

### 5.5. Add the SAML remote user group to `Source` in the ZTNA firewall rule:

![image](https://github.com/user-attachments/assets/b8c8fd48-5586-4093-8f3b-dd7b694d3bb3)

### 5.6. Test access:

![image](https://github.com/user-attachments/assets/ff4f39c3-a100-46e9-abf7-0c915b9c5508)

![image](https://github.com/user-attachments/assets/8fbee610-6ede-4995-8353-e40168e74e68)

![image](https://github.com/user-attachments/assets/2c7d7b23-2ae6-40d1-8e74-d661e0c2b651)

![image](https://github.com/user-attachments/assets/b2fba478-4e62-46ba-8c5b-2d691d79a95c)

![image](https://github.com/user-attachments/assets/7a441fea-878f-4bf4-9c4e-d13be4f9e1e4)

## 6. TCP forwarding access proxy / ZTNA destinations

### 6.1. Configure ZTNA destinations profile

Configure proxy gateway to ZTNA server create above:

![image](https://github.com/user-attachments/assets/ef8ada74-070d-4575-a0aa-9a1ab614f555)

Configure private applications:

![image](https://github.com/user-attachments/assets/0a6263f4-28f4-4929-ba2b-b8dd94e92650)

> [!Tip]
>
> Using IP address of the destination in the private applications configuration will ensure that connection to the destination is captured by FortiClient regardless of using FQDN or IP address when connecting

Configure SaaS applications:

![image](https://github.com/user-attachments/assets/40a2e32f-9696-438f-83b3-c0c7b9790345)

Review and save:

![image](https://github.com/user-attachments/assets/cad29a4b-fc53-4324-8969-8b05626d0982)

> [!Tip]
>
> Click on the "eye" behind the `ZTNA Destination Profile` title to toggle showing of `ZTNA Destination` in FortiClient

### 6.2. Test access

Wait for FortiClient to receive the configuration update:

![image](https://github.com/user-attachments/assets/176d5dcb-bf5a-4b3c-b3b6-9f8379d3f457)

Review ZTNA destinations:

![image](https://github.com/user-attachments/assets/4ba55f27-ec65-46b7-8cc9-74e577278f89)

Test connection:

![image](https://github.com/user-attachments/assets/abba0ec2-c0d5-4a2a-aca3-236c3e3c41d1)

![image](https://github.com/user-attachments/assets/6b9a62f9-2f09-4edd-a358-85c16117308f)

![image](https://github.com/user-attachments/assets/931e2d58-8d60-4772-8e70-fac683b90960)

![image](https://github.com/user-attachments/assets/df8207fc-ab80-45a6-8780-97f975bbc4c0)

![image](https://github.com/user-attachments/assets/47ceb4af-426a-4535-9243-b90e2bb72007)

Notice that connections are made towards the ZTNA server:

![image](https://github.com/user-attachments/assets/bb89b69d-bc8f-4579-9e7e-fff7678c05ed)

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
