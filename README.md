## 1. SASE

https://www.scmagazine.com/resource/sse-vs-sase-whats-the-difference

```mermaid
graph TD
SASE --> SD-WAN
SASE --> SSE
SSE --> SWG
SSE --> ZTNA
SSE --> CASB
SSE --> FWaaS
FWaaS -.- SSLi[SSL Inspection]
FWaaS -.- IPS
FWaaS -.- DNSf[DNS Filtering]
FWaaS -.- AV
FWaaS -.- DLP
SWG -.- RBI
```

- FortiGate / FortiCNF
- FortiClient EMS
- FortiAnalyzer
- FortiManager

## 2. Application Security

Web Application and API Protection (WAAP)
- FortiADC
- FortiWeb

Application Development Security
- FortiDevSec
- FortiDAST (add-on to FortiDevSec)

## 3. Security Operations

- FortiMonitor
- FortiSIEM
- FortiSOAR
