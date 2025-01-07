## 1. Microsoft Defender XDR

Microsoft Defender XDR is a solution that natively integrates multiple security solutions into one unified user experience (defender.microsoft.com, formerly security.microsoft.com)

![image](https://github.com/user-attachments/assets/ef9d9207-5d39-4857-8996-861e143245a1)

https://learn.microsoft.com/en-us/defender-xdr/pilot-deploy-overview

### 1.1. Microsoft Defender for Endpoint

Previously _Microsoft Defender Advanced Threat Protection (MDATP)_

![image](https://github.com/user-attachments/assets/61a02c39-ae28-4be1-92b6-136bd9e4c111)

https://learn.microsoft.com/en-us/defender-endpoint/microsoft-defender-endpoint

### 1.2. Microsoft Defender for Office 365 (MDO)

- Comprises of [Exchange Online Protection](https://learn.microsoft.com/en-us/defender-office-365/eop-about) and Defender for Office 365 Plan 1 / Plan 2
- Identify and remediate email-based attacks, such as phishing, malware, and business email compromise
- Also has attack simulator to run realistic phishing attack simulations
- Previously _Office 365 Advanced Threat Protection (ATP)_

![image](https://github.com/user-attachments/assets/9ac6f389-7d83-4cd3-bee5-de81d754f0df)

https://learn.microsoft.com/en-us/defender-office-365/protection-stack-microsoft-defender-for-office365

### 1.3. Microsoft Defender for Cloud Apps (MDA)

- CASB, previously _Microsoft office 365 Cloud App Security (MCAS)_
- SaaS Security Posture Management (SSPM) 

![image](https://github.com/user-attachments/assets/53edda00-a22d-423b-a21b-a82f1d0f0c12)

https://learn.microsoft.com/en-us/defender-cloud-apps/what-is-defender-for-cloud-apps

### 1.4. Microsoft Defender for Identity (MDI)

- Uses signals from on-premises AD DS and ADFS to identify, detect, and investigate attacks using UEBA (identifies anomalies with adaptive built-in intelligence), and direct threat detection of many attacks such as pass-the-hash, golden ticket, skeleton key, and more.
- Comprises of
  - Microsoft Defender portal
  - Defender for Identity sensor (installed on ADDS, ADFS and ADCS servers)
  - Defender for Identity cloud service (connected to Microsoft's intelligent security graph)

![image](https://github.com/user-attachments/assets/e5330655-64fb-4ebf-a4d7-1fb7170b9c20)

https://learn.microsoft.com/en-us/defender-for-identity/architecture

### 1.5. Microsoft Entra ID Protection

Evaluates the risk of each sign-in based on data from billions of sign-in attempt, then allow or prevent account access based on configured Conditional Access policies

![image](https://github.com/user-attachments/assets/21f7d1f2-b1da-4d9d-9499-026bfc6d0083)

https://learn.microsoft.com/en-us/entra/id-protection/overview-identity-protection

## 2. Microsoft Defender for Cloud (MDC)

CNAPP

![image](https://github.com/user-attachments/assets/1ca5cbf6-8f14-474b-a23d-decb4938a0c8)

https://www.microsoft.com/en-us/security/blog/2023/03/22/the-next-wave-of-multicloud-security-with-microsoft-defender-for-cloud-a-cloud-native-application-protection-platform-cnapp/

### 2.1. Cloud Security Posture Management (CSPM)

Provides visibility across multicloud and hybrid environments from development to runtime, provide alerts and recommendations to security teams on critical vulnerabilities and misconfigurations that could lead to issues, and have built-in workflows to strengthen security posture and help drive remediation (and at scale).

[CSPM](https://www.microsoft.com/security/business/cloud-security/microsoft-defender-cloud-security-posture-management) in MDC helps cut through the noise to focus on remediating your most critical risk with integrated insights across the SOC, DevOps, External Attack Surface Management (EASM), identity and access management, and compliance.

It has a single connected view in the cloud security graph with attack path analysis to help security teams identify exploitable resource paths and the built-in tools to mitigate risk across cloud environments.

### 2.2. Cloud Workload Protection Platform (CWPP)

Provides real-time detection and response to modern threats across your cloud workloads including virtual machines, containers and Kubernetes, databases, storage accounts, network layers, app Services, and more.

[CWP](https://www.microsoft.com/security/business/solutions/cloud-workload-protection) in MDC analyzes workloads using advanced analytics and threat intelligence to help reduce the attack surface and respond to emerging threats quickly.

The integrated experience with Microsoft 365 Defender and [Sentinel](https://www.microsoft.com/security/business/siem-and-xdr/microsoft-sentinel) enables a comprehensive detection and response solution for a modern security operations center.

### 2.3. Unified DevOps security management

[Microsoft Defender for DevOps](https://www.microsoft.com/security/business/cloud-security/microsoft-defender-devops) in MDC empowers security teams to unify, strengthen, and manage multipipeline DevOps security, shift security left, and enable **code-to-cloud** protections in a central console.

This solution helps security teams rightfully focus on critical evolving threats by **securing Infrastructure as Code (IaC)** templates and container images to minimize cloud misconfigurations reaching production environments, and correlate contextual cloud security intelligence from runtime to dev platforms to prioritize remediation in code.

### 2.4. Cloud Infrastructure Entitlement Management (CIEM)

> Permissions give identities the ability to perform an action on a resource.
>
> Across major clouds, more than 40,000 permissions can be granted, of which over 50 percent are high risk, meaning they can cause service disruption, service degradation, or data leakage when used improperly.
>
> To help support a viable multicloud strategy and avoid accidental or malicious permission misuse, streamlined permissions management is essential.

[Microsoft Entra Permissions Management](https://www.microsoft.com/security/business/identity-access/microsoft-entra-permissions-management) helps you understand the real footprint of your cloud infrastructure entitlements, prevent permissions creep, and enforce the principle of least privilege across your multicloud environment.

MDC integrates with Permissions Management, enabling security teams to get unified visibility and recommendations in a central cloud security dashboard.

## 3. Microsoft Sentinel

SIEM and SOAR

![image](https://github.com/user-attachments/assets/84f89e01-3b92-43a1-9967-aea601a5e217)

## 4. Others

### 4.1. Microsoft Defender for IoT

CyberX

### 4.2. External Attack Surface Management (EASM)

RiskIQ

### 4.3. Microsoft Defender Threat Intelligence (MDTI)



### 4.4. Microsoft Copilot for Security

