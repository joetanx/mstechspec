## 1. Next Generation Firewall

### 1.1. Intrusion Prevention System

Intrusion Prevention System (IPS) detects network attacks and prevents threats from compromising the network, including protected devices.

IPS can be in the form of a standalone appliance, or part of the feature set of a Next Generation Firewall (NGFW), such as FortiGate.

IPS utilizes signatures, protocol decoders, heuristics (or behavioral monitoring), threat intelligence (such as FortiGuard Labs), and advanced threat detection in order to prevent exploitation of known and unknown zero-day threats.

FortiGate IPS is even capable of performing deep packet inspection to scan encrypted payloads in order to detect and prevent threats from attackers.

- Up to date IPS with latest data on IPS signatures, malicious URLs and Botnet IPs and Domains from FortiGuard
  - The FortiGuard Service periodically adds new predefined signatures to counter new threats. New predefined signatures are automatically included in IPS sensors that are configured to use filters when the new signatures match existing filter specifications.
  - FortiGuard Service continually updates the botnet C&C domain list. The botnet C&C domain blocking feature can block the botnet website access at the DNS name resolving stage.
- Prevent Botnet C&C communication via various methods: IPS signatures, malicious URLs and Botnet IPs and Domains

Ref:
- https://docs.fortinet.com/document/fortigate/7.4.3/administration-guide/213498/signature-based-defense
- https://docs.fortinet.com/document/fortigate/7.4.3/administration-guide/668865/ips-with-botnet-c-c-ip-blocking
- https://docs.fortinet.com/document/fortigate/7.4.3/administration-guide/105208/botnet-c-c-domain-blocking

### 1.2. Secure Web Gateway

#### 1.2.1. DNS Filtering

DNS filtering takes place at the domain name resolution level, which means that undesired traffic can be prevented even before any inspection needs to occur.

Integration with FortiGuard enables FortiGuard category-based DNS domain filter and Botnet C&C domain blocking. This makes use of FortiGuard's continuously updated domain rating database and botnet C&C domain list for more reliable protection.

#### 1.2.2. Antivirus

FortiGate can be configured to apply antivirus protection to HTTP, FTP, IMAP, POP3, SMTP, CIFS, and NNTP sessions. Proxy-based profiles also support MAPI and SSH.

Antivirus inspection prevents potentially unwanted and malicious files from entering the network.

Antivirus profiles include multiple different functions, such as scanning files for virus signatures, scanning for advanced persistent threats, checking external malware hash lists and threat feeds, and others. Malicious files can be blocked or monitored, and can be quarantined.

Ref:
- https://docs.fortinet.com/document/fortigate/7.4.3/administration-guide/610527/antivirus-techniques

#### 1.2.3. Web Filtering

The FortiGuard filter enhances the web filter features by sorting billions of web pages into a wide range of categories that users can allow or block.

The FortiGuard Web Filtering service includes over 45 million individual website ratings that apply to more than two billion pages.

When the FortiGuard filter is enabled in a web filter profile and applied to firewall policies, if a request for a web page appears in traffic controlled by one of the firewall policies, the URL is sent to the nearest FortiGuard server. The URL category or rating is returned.
- If the category is blocked, the FortiGate shows a replacement message in place of the requested page.
- If the category is not blocked, the page request is sent to the requested URL as normal.

- content inspection with SSL inspection (web filtering, application control, antivirus)
- user authentication

Ref:
- https://docs.fortinet.com/document/fortigate/7.4.3/administration-guide/675558/fortiguard-filter

#### 1.2.4. User Authentication

FortiGate enhances Secure Web Gateway (SWG) capabilities by integrating user authentication, ensuring that traffic is allowed only for authenticated users who comply with firewall policies.

- If a user is authenticated and authorized according to the firewall policy, FortiGate permits the web traffic to proceed.
- If a user fails to authenticate or doesn't meet the policy requirements, FortiGate blocks the traffic, preventing unauthorized access to web resources.

This approach adds an additional layer of security to the Secure Web Gateway, mitigating the risk of unauthorized access and enforcing compliance with security policies.

By integrating user authentication with SWG functionality, FortiGate ensures that only authorized users can access web resources, enhancing overall network security and control.

### 1.3. Comparison with Cloud-Native or Open Source solutions

#### 1.3.1. AWS Firewall

AWS firewall provides some basic web filtering and intrusion prevention capabilities, but it is insufficient in detecting and mitigating advanced threats.

1. **Rudimentary Web Filtering and Intrusion Prevention**:
   While AWS firewall offers some level of web filtering and intrusion prevention, its capabilities are basic and may not be sufficient to defend against sophisticated threats. The firewall primarily relies on SNI-based (Server Name Indication) and signature-based blocking techniques. While these methods can be effective against known threats, they may struggle to detect and prevent advanced or zero-day attacks that don't match predefined signatures.

2. **Limited Intrusion Detection Capabilities**:
   Although AWS firewall provides some intrusion detection capabilities, they are limited in scope. The intrusion detection feature may offer basic alerts for suspicious network activity, but it may lack advanced detection mechanisms for identifying complex attack patterns or anomalies. This limitation could result in missed detections of emerging threats or sophisticated attack techniques.

3. **Reliance on Open Source Suricata for Extended Intrusion Detection**:
   To supplement the rudimentary intrusion detection capabilities of AWS firewall, users may choose to integrate open-source solutions like Suricata. Suricata is a widely used Intrusion Detection System (IDS) and Intrusion Prevention System (IPS) that offers more advanced features for detecting and mitigating network-based attacks. However, deploying and managing Suricata alongside AWS firewall adds complexity to the setup and may require additional expertise and resources.

> **Web filtering**
>
> AWS Network Firewall supports inbound and outbound web filtering for unencrypted web traffic. For encrypted web traffic, Server Name Indication (SNI) is used for blocking access to specific sites. SNI is an extension to Transport Layer Security (TLS) that remains unencrypted in the traffic flow and indicates the destination hostname a client is attempting to access over HTTPS. In addition, AWS Network Firewall can filter fully qualified domain names (FQDN).

> **Intrusion prevention**
>
> AWS Network Firewall’s intrusion prevention system (IPS) provides active traffic flow inspection with real-time network and application layer protections against vulnerability exploits and brute force attacks. Its signature-based detection engine matches network traffic patterns to known threat signatures based on attributes such as byte sequences or packet anomalies.

Ref:
- https://aws.amazon.com/network-firewall/features/
- https://aws.amazon.com/blogs/opensource/scaling-threat-prevention-on-aws-with-suricata/

#### 1.3.2. Squid / Nginx

Squid and Nginx provide basic forward proxy capabilities, but they lack security features in content inspection and depends on manual updates for web filtering blacklists.

1. **Limited Content Inspection**: While Squid and Nginx offer basic forward proxy capabilities, they lack robust content inspection features. Without content inspection, these proxies cannot thoroughly analyze the content of web traffic passing through them. This limitation makes it challenging to detect and block malicious content, such as malware, phishing attempts, or inappropriate content.

2. **Dependency on External Sources for Filtering**: To enhance web filtering capabilities, administrators often integrate SquidGuard with Squid. However, SquidGuard relies on external blacklists, such as Shalla's Blacklists or URLhaus, for URL filtering. These blacklists need to be manually updated and may not provide real-time protection against emerging threats. As a result, there can be delays in blocking malicious URLs or botnet domains until the blacklists are updated.

3. **Lack of Automatic Updates for Blacklists**: One of the significant limitations is the absence of automatic updates for blacklists in SquidGuard. Administrators must regularly monitor and manually update the blacklists to ensure they contain the latest information about malicious URLs and botnet domains. This manual process can be time-consuming and may lead to gaps in protection if updates are overlooked or delayed.

4. **Reliance on Community-Supported Solutions**: Open-source Squid, Nginx, and SquidGuard rely heavily on community-supported solutions for updates, patches, and documentation. While community contributions can be valuable, they may not always meet the same level of reliability, support, and security as commercial solutions. As a result, organizations using open-source proxies may face challenges in maintaining the stability and security of their web filtering infrastructure.

## 2. Web Application and API Protection

### 2.1. Web Application Firewall

FortiADC offers more comprehense security features to provide web layer protection for application deployed in AWS.

1. **Predefined WAF Profiles for Out-of-the-Box Security**: FortiADC provides predefined WAF profiles that enable robust security right from the start. These profiles are tailored to address specific security concerns, such as SQL injection and cross-site scripting (XSS). With FortiADC, you can activate these profiles with a single click, ensuring immediate protection for your applications.

2. **Wizard-Driven Configuration for OWASP Top 10 Protection**: FortiADC's wizard-driven configuration makes it easy to implement OWASP Top 10 protection. The wizard guides you through a straightforward process to set up WAF profiles that address the most critical web application security risks. This ensures that you have comprehensive protection against threats like injection attacks, broken authentication, and cross-site request forgery (CSRF).

3. **FortiView Dashboard for Threat Monitoring and Analysis**: The FortiView dashboard provides real-time threat monitoring and analysis, allowing you to track threats by OWASP Top 10 categories. This intuitive dashboard offers:
- Visualization: Clearly see the top 10 most critical attacks and trends.
- Drill-down capabilities: Investigate specific threats and analyze their impact.
- Customizable reporting: Generate reports to meet compliance requirements.

### 2.2. API Protection

FortiADC offers comprehensive API protection, securing your APIs from threats and vulnerabilities.

1. **JSON and XML payload protection**: Detects and prevents malicious payload attacks. validates API requests against predefined schemas, ensuring adherence to expected structures and preventing malformed requests.

2. **OpenAPI validation**: Ensures adherence to OpenAPI specifications

3. **API discovery and visibility**: Identifies and secures unknown or unmanaged APIs, preventing Shadow APIs and API sprawls

4. **Rate limiting and quota management**: Controls API request rates and quotas

5. **Protection for East-West Traffic and traffic between GCC+ and GEN**: Enable API protection for securing API traffic within the GCC+ Compartments, such as between applications in EC2, EKS, as well as GEN consumers.

### 2.3. EKS Security

FortiADC's Ingress Controller seamlessly integrates with Kubernetes clusters, extending robust Web Application Firewall (WAF) and API protection to cloud-native applications.

1. **Unified security for cloud-native applications**: FortiADC Ingress Controller provides consistent WAF and API protection across Kubernetes clusters, ensuring security policies are enforced uniformly.

2. **Simplify Kubernetes security management**: FortiADC Ingress Controller is deployed as a Kubernetes-native application, leveraging Helm charts or Kubernetes manifests for easy installation. FortiADC Ingress Controller automatically generates security configurations based on Kubernetes deployment metadata, eliminating manual configuration.

### 2.4. Support for both HTTP and non-HTTP load balancing

FortiADC's ability to load balance both HTTP and non-HTTP traffic provides a unified solution for application delivery, enhancing security and operations for disparate applications.

1. **Centralized security controls**: FortiADC provides a single pane of glass to enforce application delivery controls for both HTTP and non-HTTP traffic, ensuring consistent security controls and reducing complexity.

2. **Streamlined operations**: FortiADC's centralized management platform streamlines the management, monitoring and analysis of both HTTP and non-HTTP applications, reducing administrative overhead and offering real-time insights into application performance and security.

### 2.5. Comparison with Cloud-Native or Open Source solutions

#### 2.5.1. AWS

1. **Incomplete Protection**: AWS WAF recommends using vendor-managed rules for comprehensive protection. Fortinet's complete OWASP Top 10 rule group is one of the recommended vendors, indicating that AWS WAF alone may not provide adequate security.

2. **Limited API Protection**: AWS API Gateway is primarily used for exposing Lambda functions over APIs. Other APIs in EC2 or EKS require third-party API protection, which may lead to additional complexity and security gaps.

3. **Restricted NLB Use**: The use of Network Load Balancer (NLB) for non-HTTP traffic is restricted, and Nginx is stated as alternatic under GCC+ policies, this creates complexities or overhead for non-HTTP applications

#### 2.5.2. Nginx

1. **Config-File Based**: Nginx rules are configured through config files on the guest OS, which can bring become complex even lead to potential security misconfigurations. More advanced features requires paid version of Nginx Plus.

2. **Steep Configuration Learning curve**: Nginx config files involve an overwhelming quantity of variables, this requires expertise for fine-tuning, monitoring, and troubleshooting, which can be time-consuming and may lead to security vulnerabilities if not done correctly.

## 3. Security Information and Event Management

FortiSIEM
- Detection for MITRE ATT&CK
  - Detect DGA https://help.fortinet.com/fsiem/Public_Resource_Access/7_1_3/rules/PH_RULE_DGA_DETECTED.htm
- Centralize storage and visibility for data from Fortinet, EC2 instance guest OS, EKS and Cloud Trail
- Correlate log data from Fortinet fabric and Cloud environment to help identify cross-layer anomalies and suspicious activities that may indicate a compromise

## 4. Integrated Security Mesh

FortiWeb and FortiGate can form an integrated security mesh with FortiAnalyzer to enhance network security posture by providing centralized management, advanced analytics, and comprehensive visibility into security events in the environment.

1. **Centralized Logging and Reporting**: FortiAnalyzer aggregates logs and provides centralized reporting for both FortiWeb and FortiGate, making it easier to monitor and analyze security events across your network infrastructure.

2. **Comprehensive Visibility**: By integrating these solutions, you gain comprehensive visibility into network traffic, application usage, and security events. This holistic view allows for better understanding of potential threats and vulnerabilities.

3. **Advanced Threat Detection and Response**: FortiAnalyzer's advanced analytics capabilities enable efficient threat detection and response. It can correlate data from FortiWeb and FortiGate to identify suspicious patterns and behaviors indicative of cyber threats.

4. **Forensic Analysis and Compliance**: FortiAnalyzer facilitates forensic analysis by providing detailed logs and historical data. This is valuable for investigating security incidents and ensuring compliance with regulatory requirements.

5. **Customizable Dashboards and Alerts**: FortiAnalyzer allows you to create customized dashboards and alerts based on your specific security requirements. This enables proactive monitoring and rapid response to potential security incidents.

## 5. Security Orchestration, Automation and Response

FortiSOAR
- Automate incident triage to reduce response times by ensuring that critical incidents are addressed promptly, while less urgent alerts are handled in a timely manner
- Automate response
  - enable the creation of customizable response playbooks that define step-by-step workflows for responding to specific types of security incidents
  - relieve analyze effort on repetitive tasks and manual processes involved in incident response, such as ticketing, documentation, and communication
