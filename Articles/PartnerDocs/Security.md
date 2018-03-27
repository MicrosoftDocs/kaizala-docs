# Security
## Approach

Microsoft Kaizala services and data are hosted on Office 365 & Microsoft Azure cloud platform. Microsoft is recognized as an industry leader in cloud security. Using decades of experience building enterprise software and running online services, our team is constantly learning and continuously updating our services and applications to deliver a secure cloud productivity service that meets rigorous industry standards for compliance.  

Security development lifecycle (SDL) addresses security at each development phase, right from initial planning to launch. For example – in the design phase detailed data flow diagrams (DFD), threat models are created and thoroughly reviewed for the various components to identify and address security risks. In addition to the peer reviews, tools are used for automated detection and verification of any security issues.  

Industry standard physical and network protocols are supported to meet the highest security needs of any solution. These data centres are certified with industry standard certifications.  More information about Azure security can be found on this [website](https://www.microsoft.com/en-us/trustcenter/security/azure-security).


## Service Level Security

 At the service level, we use a defense-in-depth strategy that protects your data through multiple layers of security, as depicted in the diagram below:

![](Images/Defence%20in%20Depth.PNG)
 
A defense-in-depth strategy ensures that security controls are present at various layers of the service and that, should any one area fail, there are compensating controls to maintain security at all times. The strategy also includes tactics to detect, prevent, and mitigate security breaches before they happen. This involves continuous improvements to service-level security features, including:
    - Physical controls, video surveillance, access control, smart cards, fire protection etc. 
    - Edge routers, firewalls, intrusion detection, vulnerability scanning 
    - Access control and monitoring, anti-malware, patch and configuration management 
    - Secure engineering (SDL), access control and monitoring, anti-malware 
    - Account management, training and awareness, screening 
    - Threat and vulnerability management, security monitoring, and response, access control and monitoring, file/data integrity, encryption 

We continue to invest in systems automation that helps identify abnormal and suspicious behavior and respond quickly to mitigate security risk. We are also continuously evolving a highly effective system of automated patch deployment that generates and deploys solutions to problems identified by the monitoring systems—all without human intervention. This greatly enhances the security and agility of the service. We regularly conduct penetration tests to enable continuous improvement of incident response procedures. These internal tests help our security experts create a methodical, repeatable, and optimized stepwise response process and automation.

## Anti-malware, Patching, and Configuration Management

 The use of anti-malware software is a principal mechanism for protection of your assets from malicious software. The software detects and prevents the introduction of computer viruses and worms into the service systems. It also quarantines infected systems and prevents further damage until remediation steps are taken. Anti-malware software provides both preventive and detective control over malicious software. 

Our standard baseline configuration requirements for servers, network devices, and other Microsoft applications are documented where the standards outline the use of a standard package. These packages are pretested and configured with security controls. 

Changes, such as updates, hotfixes, and patches made to the production environment, follow the same standard change management process. Patches are implemented within the time frame specified by the issuing company. Changes are both reviewed and evaluated by our review teams and the Change Advisory Board for applicability, risk, and resource assignment prior to being implemented

## Protection from Security Threats

The overall cyber threat landscape has evolved from traditional opportunistic threats to also include persistent and determined adversaries. We equip you with a defense-in-depth approach to address the continuum of threats ranging from common “hacktivists” to cyber criminals to nation-state actors.   

Our Office 365 security strategy is founded upon a dynamic strategy with four pillars of thought. The mindset shift we made to make our defenses more effective and ever evolving is commonly referred to as “Assume Breach” and assumes that a breach has already happened in the environment and is simply not known. With this mindset, the security teams are continuously attempting to detect and mitigate security threats that are not widely known. One set of exercises is to artificially propagate a security threat and have another group respond and mitigate the threat. The primary goal of these exercises is to make Office 365 resilient so the new vulnerabilities are quickly detected and mitigated.  

![SecurityThreat.PNG](Images/SecurityThreat.PNG)

The first pillar of the security strategy is referred to as “Prevent Breach.” Our investment in this pillar involves continuous improvements to built-in security features.
    - These include port scanning and remediation, perimeter vulnerability scanning, operating system patches, network level Isolation/breach boundaries, DDoS detection and prevention, just-in-time access, live site penetration testing, and multi-factor authentication for service access. 
    - The second pillar is referred to as “Detect Breach.” In this pillar, our system and security alerts are harvested and correlated via a massive internal analysis system. The signals analyze alerts that are internal to the system as well as external signals (for example coming from customer incidents). Based on machine learning, we can quickly incorporate new patterns to trigger alerts, as well as automatically trigger alerts on anomalies in the system.
    - The third pillar is referred to as “Respond to Breach.” This pillar is used to mitigate the effects if a component is compromised. A diligent incident response process, standard operating procedures in case of an incident, ability to deny or stop access to sensitive data and identification tools to promptly identify involved parties helps ensure that the mitigation is successful.
    - The fourth pillar is referred to as “Recover from Breach,” which includes the standard operating procedures to return the service to operations. The pillar includes the ability to change the security principals in the environment, automatically update the affected systems, and audit the state of the deployment to identify any anomalies. 

## Least Privilege Access Control

No Microsoft engineer has a standing access to the production environment. The regular deployment, management and maintenance tasks are handled through automation. This stops any possibility of a rouge Microsoft individual getting access to customer data. 

We conduct regular vulnerability, risk and other threat assessments for all hosted components including operating systems, infrastructure, databases, web services, network devices, installed and running applications along with configuration on all identified information system components. A regular audit of existing permissions to the users and service accounts is conducted to adhere to least privilege access policy. 

## Data Encryption at Rest

Server side encryption of all resources is enabled with service managed keys. Encryption at rest protects data in case attackers get their hands on physical media. Following Azure encryption-decryption features are enabled to ensure data encryption at rest:  

- Azure Storage Service Encryption (SSE) for Azure Blob Storages. All data is encrypted using 256bit AES encryption, one of the strongest block ciphers available. Encryption of classic storage accounts hence all the storages are moved to resource managed storages. 
 
 
- Transparent Data Encryption (TDE) is used to perform real-time I/O encryption and decryption of the data and log files to provide data encryption at-rest. In addition, TDE can provide encryption in-transit for mirrored or log-shipped data. All replicas of data are also enabled for encryption.

## Cryptography and encryption

Cryptography uses data encryption, cryptographic key management, and secure random number generation. Only Microsoft Crypto Board approved cryptography algorithms are used. We are using only FIPS 140-2(Federal Information Processing Standard) compliant hashing algorithms. None of the banned hashing algorithm, banned symmetric block cyphers, banned random functions, asymmetric algorithms or crypto primitives are used, and regular scanning of source code is done to ensure future proofing. 

## Secure Access

Kaizala enables all communications over HTTPS protocol only, which ensures secure communication over the public Internet. TLS 1.2 is enabled, and all other versions of TLS/SSL are disabled. (available from June release). TLS configuration meet or exceed Microsoft security requirements. It doesn’t support weak key, and uses SHA256withRSA signature algorithm only. 

Only following cipher suites are enabled: 
- TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 (0xc028)   ECDH secp384r1 (eq. 7680 bits RSA)   FS 
- TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 (0xc027)   ECDH secp256r1 (eq. 3072 bits RSA)   FS 
- TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA (0xc014)   ECDH secp384r1 (eq. 7680 bits RSA)   FS 
- TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA (0xc013)   ECDH secp256r1 (eq. 3072 bits RSA)   FS 
- TLS_RSA_WITH_AES_256_GCM_SHA384 (0x9d)  
- TLS_RSA_WITH_AES_128_GCM_SHA256 (0x9c) 
- TLS_RSA_WITH_AES_256_CBC_SHA256 (0x3d) 
- TLS_RSA_WITH_AES_128_CBC_SHA256 (0x3c) 
- TLS_RSA_WITH_AES_256_CBC_SHA (0x35)  
- TLS_RSA_WITH_AES_128_CBC_SHA (0x2f)  
- TLS_RSA_WITH_3DES_EDE_CBC_SHA (0xa) 
 
TLS configuration is setup with  
- Insecure renegotiation must be disabled. 
- TLS compression must be disabled. 

TLS session ticket resumption is enabled for faster connectivity. 
Token based Authentication is used for authenticating and authorizing user access. 

## Secret Storage and Management

The fundamental mission of Secrets Management is to protect the data of the customers we serve in a manner consistent with the highest ideals within our industry and, to take advantage of automated processes to reduce human access to customer data, which will help us succeed in that endeavour.  


All the HBI data like service keys, passwords, keys, certificates, and other securable that are needed to operate the service are stored in secure key vault to without any human access to it. Only required service components which require access to keep the service running in highly available and reliable manner have access. 

To ensure secret management, Kaizala uses defined secret exchange process, uses secure secret store support, and provides access control to restrict secret access. We do not copy secret to file shares or any other external communication or storages and/or do not create any resources outside of secure Office Services Infrastructure environment. It also provides auditing layer. Centralized secrets management tools designed to provide consistency, isolation, redundancy and help avoid downtime due to expiring secrets.
