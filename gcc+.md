##  1. Firewall / IPS

### 1.1. Competition

| Use case                                | Fortinet             | AWS                                                                                                             | Azure                                                                     | GCP                                          | Third-Party |
| --------------------------------------- | -------------------- | --------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------- | -------------------------------------------- | ----------- |
| NGFW<br>(IPS, AV, Web Filter, App Ctrl) | FortiGate / FortiCNF | • AWS Security Groups<br>• AWS network Access Control List (ACL)<br>• AWS Network Firewall<br>• AWS NAT Gateway | • Network Security Group (NSG)<br>• Azure Firewall<br>• Azure NAT Gateway | • Cloud NGFW<br>• Cloud NAT                  |             |
| WAN/SDWAN                               | FortiGate / FortiCNF | • AWS Virtual Private Network (VPN)<br>• Amazon Cloud WAN<br>• AWS Transit Gateway                              | • Azure Virtual Private Network (VPN)<br>• Azure Virtual WAN              | • Cloud VPN<br>• Network Connectivity Center |             |

### 1.2. Value Drivers

## 2. Web Application and API Security

### 2.1. Competition

| Use case                                           | Fortinet                                                          | AWS                                               | Azure                                                                        | GCP                                                                          | Third-Party |
| -------------------------------------------------- | ----------------------------------------------------------------- | ------------------------------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ----------- |
| CDN                                                | FortiWeb Cloud                                                    | Amazon CloudFront                                 | Azure Front Door                                                             | • Cloud CDN<br>• Media CDN                                                   |             |
| GSLB                                               | FortiGSLB                                                         | AWS Route 53                                      | Azure Traffic Manager                                                        | Cloud DNS                                                                    |             |
| DDOS                                               | • FortiDDOS<br>• FortiWeb / FortiWeb Cloud                        | AWS Shield Advanced                               | Azure DDoS Protection                                                        | Google Cloud Armor Managed Protection Plus                                   |             |
| Web Application Firewall (WAF) /<br>API Protection | FortiWeb / FortiWeb Cloud                                         | • AWS WAF<br>• AWS Shield<br>• Amazon API Gateway | • Azure Web Application Firewall (WAF)<br>• Azure API Management             | • Google Cloud Armor<br>• Web App and API Protection (WAAP)<br>• API Gateway |             |
| Load balancing                                     | • FortiADC (non-HTTP(S))<br>• FortiWeb / FortiWeb Cloud (HTTP(S)) | • AWS NLB (non-HTTP(S))<br>• AWS ALB (HTTP(S))    | • Azure Load Balancer (non-HTTP(S))<br>• Azure Application Gateway (HTTP(S)) | Cloud Load Balancing                                                         |             |

## 3. SIEM / SOAR

### 3.1. Competition

| Use case            | Fortinet  | AWS                                                                 | Azure                                                          | GCP                                                       | Third-Party |
| ------------------- | --------- | ------------------------------------------------------------------- | -------------------------------------------------------------- | --------------------------------------------------------- | ----------- |
| SIEM                | FortiSIEM | • AWS CloudTrail<br>• Amazon CloudWatch Logs<br>• Amazon OpenSearch | • Azure Audit Logs<br>• Azure Monitor Logs<br>• Azure Sentinel | • Cloud Audit Logs<br>• Cloud Logging<br>• Chronicle SIEM |             |
| Security Automation | FortiSOAR | AWS Security Hub Automated Security Response add-on                 | Microsoft Defender for Cloud<br>\+ Azure Logic Apps            | Chronicle SOAR                                            |             |

## 4. CNAPP / Others

### 4.1. Competition

| Use case                          | Fortinet                         | AWS                                                                              | Azure                                     | GCP                            | Third-Party |
| --------------------------------- | -------------------------------- | -------------------------------------------------------------------------------- | ----------------------------------------- | ------------------------------ | ----------- |
| Cloud Security Posture Management | FortiCNP                         | • AWS Security Hub<br>• Amazon Guard Duty<br>• AWS Audit Manager<br>• AWS Config | Microsoft Defender for Cloud              | Security Command Center        |             |
| Secure Access                     | • FortiPAM<br>• FortiSASE (ZTNA) | AWS Systems Manager                                                              | Azure Bastion Host                        | Identity-Aware Proxy (IAP)     |             |
| Application Security              | FortiDevSec                      | Amazon CodeGuru Security                                                         | GitHub Advanced Security for Azure DevOps | Cloud Build On-Demand Scanning |             |
