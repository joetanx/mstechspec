##  1. Firewall / IPS

## 2. Web Application and API Protection

### 2.1. Web Application Firewall

1. **Traffic Monitoring**: The WAF monitors incoming and outgoing traffic to the web application, inspecting every HTTP request and response.

2. **Rule-Based Filtering**: WAFs use a set of predefined rules or policies to filter out potentially malicious traffic. These rules are based on known attack patterns, such as SQL injection, cross-site scripting (XSS), cross-site request forgery (CSRF), etc.

3. **Signature-Based Detection**: WAFs can identify known attack patterns by matching incoming requests against a database of attack signatures. If a request matches a known attack signature, the WAF can block it.

4. **Behavioral Analysis**: Some advanced WAFs employ behavioral analysis techniques to detect anomalies in web traffic. They analyze traffic patterns and behavior to identify potentially malicious activity that may not match known attack signatures.

5. **IP Reputation Checks**: WAFs can check the reputation of the IP addresses sending requests to the web application. If an IP address is associated with suspicious or malicious activity, the WAF can block or restrict traffic from that IP.

6. **Rate Limiting**: WAFs can enforce rate limits on incoming requests to prevent abuse or flooding attacks, such as Distributed Denial of Service (DDoS) attacks.

7. **Session Management**: WAFs can help manage user sessions and prevent session-related attacks, such as session hijacking or fixation.

8. **Logging and Reporting**: WAFs typically log detailed information about detected threats and security events. This logging allows administrators to analyze traffic patterns, investigate security incidents, and fine-tune WAF rules.

### 2.2. API Security

Web Application Firewalls (WAFs) can secure APIs (Application Programming Interfaces) in several ways:

1. **Protocol Validation**: WAFs inspect API requests and responses to ensure they adhere to the expected protocol schemas (JSON, XML) or protocol standards (OpenAPI). This validation helps prevent protocol-level attacks and ensures that API communications are conducted securely.

2. **Input Validation**: WAFs validate input parameters and payloads of API requests to prevent common attacks such as SQL injection, cross-site scripting (XSS), and command injection. By filtering and sanitizing input data, WAFs can block malicious payloads before they reach the API backend.

3. **Rate Limiting and Throttling**: WAFs can enforce rate limits and throttle excessive API requests to mitigate abuse, prevent denial-of-service (DoS) attacks, and protect API endpoints from being overwhelmed by malicious or excessive traffic.

4. **Authentication and Authorization**: WAFs can enforce authentication and authorization policies for API access, ensuring that only authorized users or applications can interact with the API endpoints. This helps prevent unauthorized access and protects sensitive data from being exposed.

5. **API-Specific Signatures and Rules**: Some WAFs offer specialized rule sets and signatures tailored specifically for API security. These rules are designed to detect and block API-specific threats, such as parameter manipulation, API endpoint enumeration, or API key abuse.

6. **Content Inspection**: WAFs inspect the content of API requests and responses for potential security threats, such as sensitive data exposure or data leakage. By analyzing API payloads, WAFs can detect and prevent data exfiltration attempts and enforce data privacy regulations.

7. **Session Management**: WAFs can assist in managing API sessions and preventing session-related attacks, such as session hijacking or session fixation. By enforcing secure session handling practices, WAFs help ensure the integrity and confidentiality of API sessions.

8. **API Gateway Integration**: In some cases, WAF functionality may be integrated directly into API gateways, which act as intermediaries between clients and API endpoints. API gateways with built-in WAF capabilities can provide comprehensive API security, including traffic filtering, authentication, rate limiting, and policy enforcement.

9. **API Discovery to Identify Exposed Endpoints**: API discovery involves identifying all the endpoints exposed by an application. WAFs can leverage this information to create comprehensive security policies that cover all API endpoints, ensuring that no critical entry points are left unprotected. This helps prevent shadow APIs and API Sprawls.

### 2.3. Virtual patching

A Web Application Firewall (WAF) provides virtual patching capabilities by dynamically filtering and blocking malicious or suspicious traffic before it reaches the web application. Here's how it achieves this:

1. **Immediate Protection**: When a security vulnerability is discovered in a web application, it may take time for the application's developers to create and deploy a patch. In the meantime, the application remains vulnerable to attacks exploiting that vulnerability. A WAF can provide immediate protection by applying virtual patches, which are essentially rules configured to block traffic that attempts to exploit the vulnerability.

2. **Rule-Based Blocking**: WAFs use rule sets or policies to inspect incoming HTTP requests and responses. When a vulnerability is identified, security experts can create custom rules specific to that vulnerability or use pre-configured rule sets provided by the WAF vendor. These rules are designed to detect and block malicious traffic attempting to exploit the vulnerability.

3. **Pattern Matching**: Virtual patching often involves pattern matching techniques to identify traffic patterns associated with exploit attempts. For example, if a SQL injection vulnerability is discovered in a web application, the WAF can be configured with rules to detect SQL injection patterns in incoming requests and block them.

4. **Behavioral Analysis**: Some advanced WAFs employ behavioral analysis techniques to identify and block exploit attempts based on anomalous behavior. Instead of relying solely on known attack patterns, these WAFs analyze traffic patterns and behavior to detect and block suspicious activity that may indicate an attempted exploit.

5. **Regular Updates**: WAF vendors continuously update their rule sets to address new vulnerabilities and evolving attack techniques. This ensures that virtual patches remain effective against the latest threats.

6. **Logging and Reporting**: WAFs typically log details about detected threats and security events, including blocked exploit attempts. This logging allows administrators to monitor for attempted attacks, investigate security incidents, and fine-tune virtual patching rules as necessary.

By providing virtual patching capabilities, WAFs help protect web applications from known vulnerabilities and exploits, even before patches are available or deployed. This helps to reduce the window of exposure to attacks and enhance the overall security posture of the web application.

### 2.4. Advanced Bot Protection

Prevent business logic attacks from all access points – websites, mobile apps and APIs. Gain seamless visibility and control over bot traffic to stop online fraud through account takeover or competitive price scraping.

- Allow and monitor known bots: Allow good bots such as search engine crawlers and news bots to crawl your applications, but monitor and block abusive behavior.
- Control unknown bots: Alert or block requests originating from bots with unknown intent, including headless browsers, command-line tools and good bot impersonators.
- Define custom bots: Create bot definitions for bots your team decides are known-good or malicious.

### 2.5. DoS Protection

Block attack traffic at the edge to ensure business continuity with guaranteed uptime and no performance impact. Secure your on premises or cloud-based assets – whether you’re hosted in AWS, Microsoft Azure, or Google Public Cloud.

### 2.6. Machine Learning / Attack Analytics

Machine learning (ML) plays a significant role in enhancing the capabilities of Web Application Firewalls (WAFs) by enabling them to adapt to evolving threats and improve detection accuracy. Here are several ways in which machine learning helps in web application firewall:

1. **Anomaly Detection**: Machine learning algorithms can analyze historical traffic patterns and learn what constitutes "normal" behavior for a web application. By identifying deviations from these normal patterns, ML-powered WAFs can detect anomalous activities that may indicate attacks, such as DDoS attacks, SQL injection attempts, or other forms of malicious behavior.

2. **Behavioral Analysis**: ML algorithms can analyze the behavior of incoming requests and responses in real-time to identify suspicious patterns or sequences of events that may indicate an attack. For example, ML models can detect unusual sequences of HTTP requests that might be indicative of a reconnaissance or probing attack.

3. **Adaptive Rule Generation**: ML algorithms can automatically generate and refine rules for the WAF based on observed traffic patterns and known attack techniques. This helps in adapting the WAF's defense mechanisms to new and emerging threats without manual intervention.

4. **Attack Pattern Recognition**: ML algorithms can learn to recognize attack patterns and signatures by analyzing large volumes of historical attack data. This allows the WAF to accurately detect and block known attack types, such as SQL injection, cross-site scripting (XSS), or command injection, even if they have not been explicitly defined in rule sets.

5. **Reducing False Positives**: ML algorithms can help in reducing false positives by accurately distinguishing between legitimate and malicious traffic. By continuously learning from feedback and adjusting their models, ML-powered WAFs can improve their accuracy in detecting and blocking attacks while minimizing disruptions to legitimate users.

6. **Zero-Day Threat Detection**: ML-powered WAFs can detect previously unseen or zero-day threats by identifying patterns and behaviors that deviate from normal traffic. This capability is particularly valuable in defending against new and evolving attack techniques for which traditional signature-based detection methods may not be effective.

7. **User and Entity Behavior Analytics (UEBA)**: ML algorithms can analyze user behavior within the web application to detect suspicious activities, such as account takeover attempts or insider threats. By monitoring user interactions and identifying deviations from normal behavior, ML-powered WAFs can help prevent unauthorized access and data breaches.

Overall, machine learning enables WAFs to become more proactive, adaptive, and effective in defending against a wide range of web application attacks, ultimately enhancing the security posture of the protected applications.

### 2.7. Deployment flexibility

1. Physical/virtual WAF appliances that integrate with cloud-based security services
2. Microservices-based WAF instances that integrate with cloud-based security services
3. Cloud-based WAAP platforms with integrated WAF, Bot, API, and DDoS security controls

## 3. Security Operations

### 3.1. SOC Functions

1. Threat monitoring
2. Alert investigations
3. Incident response

### 3.2. Technologies used in SOC

1. SIEM
2. EDR/ NDR/XDR
3. TIP
4. SOAR
5. Ticketing systems (e.g. ServiceNow, Jira, may also use built-in functions from SOAR)

### 3.3. SIEM use cases

1. Log collection
2. Log aggregation
3. Rule-based alert
4. Artificial intelligence
5. Response
6. Parsing
7. Normalization
8. Categorization
9. Enrichment
10. Indexing
11. Storage

### 3.4. SIEM Integration with EDR/NDR/XDR

SIEM, EDR, NDR, and XDR solutions work together to provide comprehensive visibility, detection, and response capabilities across an organization's IT infrastructure, helping security teams detect and mitigate a wide range of cybersecurity threats.

1. **SIEM (Security Information and Event Management)**:
   - SIEM systems collect, aggregate, and analyze log data from various sources across an organization's IT infrastructure, such as firewalls, servers, endpoints, and applications.
   - They use correlation rules and advanced analytics to detect patterns of suspicious behavior or potential security threats.
   - SIEM platforms provide real-time monitoring and incident response capabilities, allowing security teams to investigate and mitigate security incidents promptly.

2. **EDR (Endpoint Detection and Response)**:
   - EDR solutions focus on protecting individual endpoints, such as desktops, laptops, servers, and mobile devices.
   - They continuously monitor endpoint activities and behaviors, including file accesses, process executions, network connections, and registry changes.
   - EDR tools leverage advanced detection techniques, such as machine learning and behavioral analysis, to identify and respond to threats that traditional antivirus software might miss.
   - When a potential threat is detected on an endpoint, EDR solutions can trigger alerts, quarantine suspicious files, or initiate automated response actions to contain and remediate the threat.

3. **NDR (Network Detection and Response)**:
   - NDR solutions are designed to monitor network traffic and identify suspicious or malicious activities occurring within the network perimeter.
   - They analyze network packets in real-time, looking for indicators of compromise (IoCs), anomalous behavior, or known attack patterns.
   - NDR tools provide visibility into lateral movement, data exfiltration, command-and-control communications, and other network-based threats.
   - When a threat is detected, NDR solutions can generate alerts, block malicious traffic, and provide forensic data to aid in incident investigation and response.

4. **XDR (Extended Detection and Response)**:
   - XDR integrates and correlates data from multiple security tools, including SIEM, EDR, NDR, and other sources, to provide holistic threat detection and response capabilities.
   - By aggregating and analyzing telemetry data from endpoints, networks, and other security controls, XDR solutions can identify sophisticated, multi-stage attacks that span across different layers of the IT environment.
   - XDR platforms use advanced analytics, threat intelligence, and automated response actions to detect, investigate, and remediate security incidents more effectively than individual security products operating in isolation.

### 3.5. SOC Roles

#### 3.5.1. L1 SOC Analyst

1. Alert triage
2. First line of defence
3. Identifying anomalies
4. Raising requests for whitelists
5. Performing investigations

#### 3.5.2. L2 SOC Analyst

1. Monitoring alerts
2. Threat hunting
3. Resource mentoring
4. Creating and approving whitelists
5. Handling escalated investigations

#### 3.5.3. L3 SOC Analyst

1. Client onboarding
2. Incident management
3. Report and documentation
4. Stakeholders communication (technical)

### 3.6. SOC Automation

1. Triage
2. Enrichment
3. TI Gathering
4. Validation across detection tools
5. Close false positives
6. Notify users and stakeholders
7. Block IOCs
8. Alert administration

### 3.7. SANS Incident Response Framework

https://www.sans.org/media/score/504-incident-response-cycle.pdf

#### 3.7.1. Preparation

#### 3.7.2. Identification

#### 3.7.3. Containment

#### 3.7.4. Eradication

1. Removing artifacts
2. Identify all hosts
3. Updating configurations
4. Patches
5. Documentation

#### 3.7.5. Recovery

1. Restoration
2. Normal operations
3. Activities
4. Monitoring
5. Documentation
6. Prevent re-infection

#### 3.7.6. Lessons Learned

1. Meeting
2. 5W1H
3. Way forward
4. Documentation

## 4. Reference Links

### Analyst Reports

|Topic|Link|
|---|--|
|**Firewall and SASE**|
|Magic Quadrant for Network Firewalls 2022|https://www.gartner.com/doc/reprints?id=1-2C2Q9662&ct=221222|
|Magic Quadrant for Single-Vendor SASE 2023|https://www.gartner.com/doc/reprints?id=1-2EQ0YMTZ&ct=230816|
|2024 Strategic Roadmap for SASE Convergence|https://www.gartner.com/doc/reprints?id=1-2G2V1C8T&ct=231229|
|**WAAP and CNAPP**|
|Magic Quadrant for Cloud WAAP 2022|https://www.techcity.cloud/information/gartner-magic-quadrant-for-cloud-web-application-and-api-protection/|
|Market Guide for Cloud WAAP 2023|https://www.gartner.com/doc/reprints?id=1-2G5WIWUG&ct=240105&st=sb|
|Market Guide for CNAPP 2023|https://www.gartner.com/doc/reprints?id=1-2CYRBHBR&ct=230317|
|**SecOps**|
|Critical Capabilities for SIEM 2024|https://www.gartner.com/doc/reprints?id=1-2HXU226Z&ct=240626|
|Magic Quadrant for SIEM 2024|https://www.gartner.com/doc/reprints?id=1-2HI8DCZY&ct=240508|
|Market Guide for SOAR 2023|https://www.gartner.com/doc/reprints?id=1-2E78ER5R&ct=230620|
|Market Guide for XDR 2023|https://www.gartner.com/doc/reprints?id=1-2EOYTQA6&ct=230811|

### Technical Documents

|Topic|Link|
|---|--|
|Third-party firewall appliance vs AWS Network Firewall/WAF|https://www.linkedin.com/pulse/third-party-firewall-appliance-vs-aws-network-dinesh-sharma-64kmc|
|Design your firewall deployment for Internet ingress traffic flows|https://aws.amazon.com/blogs/networking-and-content-delivery/design-your-firewall-deployment-for-internet-ingress-traffic-flows/|
|Exposing Kubernetes Applications|- Part 1: Service and Ingress Resources https://aws.amazon.com/blogs/containers/exposing-kubernetes-applications-part-1-service-and-ingress-resources/<br>- Part 2: AWS Load Balancer Controller https://aws.amazon.com/blogs/containers/exposing-kubernetes-applications-part-2-aws-load-balancer-controller/<br>- Part 3: NGINX Ingress Controller https://aws.amazon.com/blogs/containers/exposing-kubernetes-applications-part-3-nginx-ingress-controller/|
|AWS Integration with SIEM/SOAR|https://maturitymodel.security.aws.dev/en/3.-efficient/siem-soar/|
