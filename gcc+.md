## 1. Firewall and Intrusion Prevention System

### FortiGate IPS

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

## 2. Secure Web Gateway

FortiProxy
- content inspection with SSL inspection (web filtering, application control, antivirus)
- SWG with LDAP/RADIUS authentication

## 3. Web Application and API Protection

FortiWeb
- Protection against web application exploits
  - up to date signature-based attack prevention with latest updates from FortiGuard https://docs.fortinet.com/document/fortiweb/7.4.3/administration-guide/210196/blocking-known-attacks
  - OWASP top 10 compliance monitoring https://docs.fortinet.com/document/fortiweb/7.4.3/administration-guide/897881/owasp-top-10-compliance
  - prevent client-side attacks such as XSS and CSRF
    - https://docs.fortinet.com/document/fortiweb/7.4.3/administration-guide/56487/defeating-cross-site-request-forgery-csrf-attacks
    - https://docs.fortinet.com/document/fortiweb/7.4.3/administration-guide/981691/syntax-based-sql-xss-injection-detection
- API security
  - Schema validation for JSON and XML APIs
  - OpenAPI 3.0.x validation
- machine learning
  - ML bot detection: https://docs.fortinet.com/document/fortiweb/7.4.3/administration-guide/600188/configuring-ml-based-bot-detection-policy
  - ML Based Anomaly Detection: https://docs.fortinet.com/document/fortiweb/7.4.3/administration-guide/94907/ml-based-anomaly-detection
  - ML Based API Protection: https://docs.fortinet.com/document/fortiweb/7.4.3/administration-guide/98060/configuring-ml-based-api-protection-policy
- Ingress controller for Kubernetes (EKS)

## 4. Integrated Security Mesh

FortiAnalyzer
- fabric integration, corelation across firewall, swg and waf

## 5. Security Information and Event Management

FortiSIEM
- Detection for MITRE ATT&CK
  - Detect DGA https://help.fortinet.com/fsiem/Public_Resource_Access/7_1_3/rules/PH_RULE_DGA_DETECTED.htm
- Centralize storage and visibility for data from Fortinet, EC2 instance guest OS, EKS and Cloud Trail
- Correlate log data from Fortinet fabric and Cloud environment to help identify cross-layer anomalies and suspicious activities that may indicate a compromise

## 6. Security Orchestration, Automation and Response

FortiSOAR
- Automate incident triage to reduce response times by ensuring that critical incidents are addressed promptly, while less urgent alerts are handled in a timely manner
- Automate response
  - enable the creation of customizable response playbooks that define step-by-step workflows for responding to specific types of security incidents
  - relieve analyze effort on repetitive tasks and manual processes involved in incident response, such as ticketing, documentation, and communication
