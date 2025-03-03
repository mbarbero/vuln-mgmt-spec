# Vulnerability handling for products with digital elements

## Introduction

Organizations need to handle reported vulnerabilities. The industry is agreeing on common practices, and they have been described in various guidelines.

This specification describes in a formal way the needed elements of such a vulnerability handling procedure using the model of coordinated disclosure. Other models like “full disclosure” are out of scope of this document.

The document starts with definitions of the main terms, then covers the content of a Vulnerability Reporting Policy. With those two elements, it then describes steps of a vulnerability handling process.

## Definitions

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and "OPTIONAL" in this document are to be interpreted as described in [BCP 14](https://www.rfc-editor.org/info/bcp14) ([RFC 2119](https://datatracker.ietf.org/doc/html/rfc2119), [RFC 8174](https://datatracker.ietf.org/doc/html/rfc8174)) when, and only when, they appear in UPPERCASE.

Organization is any organization with commercial or non-commercial scope, that is applying this specification, and corresponds to the term "vendor" in \[ISO.29147.2018\] and \[CERT.CVD\].

The term "Researcher" corresponds to the terms "finder" and "reporter" in \[ISO.29147.2018\] and \[CERT.CVD\]. 

The term "Implementors" includes all parties involved in the vulnerability disclosure process.

Vulnerability Reporting Policy is a policy describing Organization-specific details of the vulnerability reporting fulfilling requirements laid out in section \[\]

Security Policy is…

Vulnerability is a defect in a software or hardware component of a Product that can be used by attackers to cause negative impact on Confidentiality, Integrity or Availability.

An SBOM (Software Bill of Materials) is a machine readable representation of all software components of a given Product and its dependencies.

A Product is a unit of hardware or software. It can be combined with other Products. Examples of Products include applications, libraries, websites, appliances, hardware modules, hardware chips, specifications.

A Coordinated Vulnerability Disclosure is a way of disclosing a Vulnerability in a way that synchronizes the disclosure between multiple parties.

A Coordinator is a person or organization that coordinates communication and disclosure between multiple parties including Researchers and Organizations.

## Vulnerability Reporting Policy

An Organization MUST have a method to deal with vulnerability reports, resolution of issues and distribution of fixes, mitigations, or information.

The Organization Vulnerability Reporting Policy is a document containing the following elements:

- MUST contain the preferred reporting method  
- MAY contain additional reporting methods  
- MUST contain a timeline of typical expected disclosure of the Vulnerability  
- MUST describe the expectations from the reporter to determine whether or not a report is considered a valid vulnerability report. This SHALL be “reasonable”  
- MUST describe the information the initial report SHOULD include to be processed  
- MUST contain information on which vulnerability identification the Organization assigns  
- MUST contain information on where the list of known vulnerabilities in the products of the Organization is located  
- RECOMMENDED contain information how the Organization credits Researchers  
- SHOULD include information on the payments provided to Researchers for valid findings, if the Organization provides any; or information that the Organization does not pay for reports  
- If the Organization has a bug bounty, the Policy SHOULD contain information about the bug bounty program

The Vulnerability Reporting Policy MAY be included into the Security Policy. The Organization MAY include additional elements, specific to their processes and use-cases.

At least one of the reporting methods listed in the Policy MUST allow reporting without creating a dedicated account.

If email is provided as a method of reporting vulnerabilities, the Organisation SHOULD provide the encryption key to be used for encrypted communications. The RECOMMENDED encryption methods and keys are OpenPGP (RFC 4880), and age [https://c2sp.org/age](https://c2sp.org/age)).

One method for reporting MAY be a ticketing system. If offered, the system SHOULD offer confidentiality of issues and responses. The ticketing system MAY use a third party service, e.g., in the case of a bug bounty program.

It is RECOMMENDED that the list of reporting methods is provided in a machine-readable format.

The Policy MUST adhere to the Coordinated Vulnerability Disclosure principles, assuming coordination between all stakeholders; as opposed to “full disclosure” or “no disclosure”.

If the Organization is distributing software in the source code form, the source code MUST include an URL to the reporting policy or an URL to the policy, and the specific Project information, if applicable. It is RECOMMENDED to use a separate, dedicated file with the name like SECURITY, SECURITY.md or SECURITY.txt. The Organization MAY distribute the complete content of the Policy in such a file.

If the Organization is distributing software in the binary form, the software MUST either

- Have an option to show the Policy and contact information for reporting vulnerabilities;  
- Or an URL of the Policy or the Policy text MUST be included in the distributed archive.

## Vulnerability sources

Organizations accept vulnerabilities from multiple sources and they MUST accept vulnerability reports from external and internal Researchers. If it does trace Vulnerabilities in dependencies using SBOM, it MUST also accept reporting from automatic tools.

### External reporting

Organizations MUST publish their Vulnerability Reporting Policy on their website, if they have one. It is RECOMMENDED to use a page name like “Security” or “How to report a vulnerability” or similar. Such a page MUST be publicly available.

If an Organization is hosting multiple software Products, they MAY have specific clauses, for example a specific preferred reporting mechanism.

### Internal reporting

Organizations MUST apply the same processes for internal and external vulnerability reporting.

### Automated reporting

Organizations SHOULD trace disclosed vulnerabilities in dependencies.

## Vulnerability handling inside an organization

Organizations MUST clearly assign potential vulnerability management to a group or individuals.

All Vulnerabilities MUST be resolved: either fixed, or mitigated, or documented. The resolution time depends on the vulnerability type, but it MUST be reasonable.

If during the analysis the organization finds out that the cause of a Vulnerability is located in a product that is a dependency, the Organization MUST report the Vulnerability to the upstream project, using one of their official vulnerability reporting channels. The communication between multiple Organizations follows the rules of Coordinated Vulnerability Handling and Disclosure.

In case if the upstream Organization does not provide a fix in a reasonable timeline, the Organization MAY provide a fix or a mitigation.

Each Organization decides how to develop fixes for Vulnerabilities. It is RECOMMENDED that this development happens privately and all parts of the solution (fixes, mitigations, documentation, Vulnerability identification) become public at the same time with a bug fix release (if provided).

## Multi-party vulnerability handling and disclosure

Sometimes the vulnerability handling and disclosure includes more parties than the Researcher and the Organization. It might include a case when the vulnerability is in a dependency, or if the analysis finds that multiple similar vulnerabilities exist in products with the same functionality, or even if the vulnerable code is shared between different Products.

In such a case, the Organization and Researcher MUST notify additional parties. They MAY decide to name a Coordinator, a party dealing with communication and synchronization between Organizations and Researchers.

In case of such a multi-party vulnerability handling, all parties SHOULD agree on and release all the vulnerability information on a coordinated basis and on a coordinated date.

## Vulnerability publication

The Organization MUST publish all resolved vulnerabilities. Each Organization MUST publish a list of all publicly known Vulnerabilities in their products. This publication SHOULD happen on a web page and it is RECOMMENDED to offer a machine-readable version.

The publication of the list of known Vulnerabilities takes a form of a list of their identification (one or multiple ones) and at least one link to a public resource describing this Vulnerability (at least the affected product and versions, affected configurations and a general description) and RECOMMENDED to include an estimation of severity of the Vulnerability. The Organization MAY include additional information.

The publication MUST include a Vulnerability identification from a public database. It MAY include additional identification numbers from public and private databases.

It is STRONGLY RECOMMENDED that this information is also available in machine-readable format.

For higher severity Vulnerabilities, it is RECOMMENDED that the Organization also publishes an advisory containing information regarding affected configurations, possible mitigations and all information considered useful for users of the Product.

## References

[RFC 2119](https://datatracker.ietf.org/doc/html/rfc2119)  
[RFC 8174](https://datatracker.ietf.org/doc/html/rfc8174)  
\[ISO.29147.2018\]  
\[CERT.CVD\]  
\[CISA.CVD\] [https://www.cisa.gov/coordinated-vulnerability-disclosure-process](https://www.cisa.gov/coordinated-vulnerability-disclosure-process)  
\[ETSI.CVD\] [https://www.etsi.org/standards/coordinated-vulnerability-disclosure](https://www.etsi.org/standards/coordinated-vulnerability-disclosure)  
\[NCSC.Guidelines\] [http://web.archive.org/web/20240811071923/https://www.enisa.europa.eu/news/member-states/WEB\_115207\_BrochureNCSC\_EN\_A4.pdf](http://web.archive.org/web/20240811071923/https://www.enisa.europa.eu/news/member-states/WEB_115207_BrochureNCSC_EN_A4.pdf)  
\[OpenSSF.MaintainerGuideline\] [https://github.com/ossf/oss-vulnerability-guide/blob/main/maintainer-guide.md\#readme](https://github.com/ossf/oss-vulnerability-guide/blob/main/maintainer-guide.md#readme)  
\[OpenSSF.FinderGuide\] [https://github.com/ossf/oss-vulnerability-guide/blob/main/finder-guide.md\#readme](https://github.com/ossf/oss-vulnerability-guide/blob/main/finder-guide.md#readme)  
\[CVE.Glossary\] [https://www.cve.org/ResourcesSupport/Glossary](https://www.cve.org/ResourcesSupport/Glossary)
