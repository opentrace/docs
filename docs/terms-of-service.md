# OpenTrace Terms of Service

**Last Updated:** February 6, 2026

**IMPORTANT NOTICE**: This is a draft template created for legal review. It must be reviewed and approved by qualified legal counsel before publication or use.

---

## 1. Introduction and Acceptance of Terms

These Terms of Service ("Terms") govern your access to and use of OpenTrace Insight Platform ("OpenTrace," "Service," "Platform," or "we"), an AI-powered system for investigating operational incidents, analyzing system architecture, and understanding complex distributed systems.

By accessing or using OpenTrace, you agree to be bound by these Terms. If you are using OpenTrace on behalf of an organization, you represent and warrant that you have the authority to bind that organization to these Terms.

**If you do not agree to these Terms, do not use the Service.**

---

## 2. Service Description

### 2.1 Platform Overview

OpenTrace Insight is a cloud-based Software-as-a-Service (SaaS) platform that provides AI-assisted system investigation and understanding for modern distributed systems, including:

- **Automated Incident Investigation**: AI-assisted investigation of production incidents and operational anomalies
- **Root Cause Analysis Support**: AI-powered analysis and hypothesis generation for system failures and operational issues
- **System Architecture Intelligence**: Knowledge-graph-based representation of code, runtime telemetry, and infrastructure relationships
- **Investigation Timeline**: A continuously updated timeline of investigation steps, findings, and evidence
- **Evidence Collection**: Centralized organization of investigation artifacts and references
- **Integration Hub**: Connections to monitoring, observability, error tracking, infrastructure, and code repository platforms

### 2.2 Technical Architecture

The Service operates on Google Cloud Platform infrastructure and includes:

- **Insight API**: RESTful HTTP and gRPC API endpoints hosted on Google Cloud Run
- **Insight Agent**: Multi-agent investigation system powered by Google Vertex AI (Gemini models)
- **Insight UI**: Web-based interface for managing investigations
- **MCP Protocol**: Model Context Protocol for external tool and data source integration
- **Storage Systems**: Google Firestore, Neo4j, PostgreSQL, and Firebase Storage

### 2.3 AI and Machine Learning

OpenTrace uses artificial intelligence and large language models (LLMs), specifically Google Vertex AI with Gemini models, to assist users in:

- Analyze system behavior and operational signals
- Generating investigation hypotheses and explanatory summaries
- Correlating data across connected tools and services
- Producing natural language descriptions of observed system behavior

**Important Limitations and Disclaimers**:

* AI-generated outputs are **informational suggestions only**, not guarantees or determinations of fact
* Outputs may be inaccurate, incomplete, or misleading
* **Human review and validation is required** before acting on any AI-generated output
* OpenTrace does **not** perform automated decision-making producing legal, financial, medical, or similarly significant effects
* OpenTrace is a diagnostic and analysis tool and **must not be used as the sole basis for operational decisions**

---

## 3. Account Terms

### 3.1 Account Registration

To use OpenTrace, you must:

- Create an account with accurate and complete information
- Provide a valid email address
- Create a secure password
- Be at least 18 years of age (or the age of majority in your jurisdiction)
- Comply with all applicable laws and regulations

### 3.2 Organization Accounts

OpenTrace supports organization-based multi-tenant access:

- Organizations can have multiple users and teams
- Users belong to one or more organizations
- Investigation data is isolated by organization
- Organization administrators can manage users, permissions, and settings
- Each organization is responsible for the actions of its users

### 3.3 Authentication

Account authentication is provided through:

- **Firebase Authentication**: Primary authentication system using JWT bearer tokens
- **Clerk**: Organization and team management with OAuth support
- **Third-Party OAuth**: Google, GitHub, GitLab authentication options

You are responsible for:
- Maintaining the confidentiality of your account credentials
- All activities that occur under your account
- Immediately notifying us of any unauthorized use

### 3.4 Account Responsibilities

You agree to:

- Keep your contact information current
- Not share your account with others
- Not create multiple accounts to evade restrictions
- Not use automated means to create accounts
- Not sell, transfer, or sublicense your account

---

## 4. Acceptable Use Policy

### 4.1 Permitted Use

You may use OpenTrace only for lawful purposes and in accordance with these Terms. Specifically, you may:

- Investigate incidents in systems you own or have authorization to monitor
- Analyze your own infrastructure and application architecture
- Integrate with third-party services you have authorization to access
- Share investigation results with authorized team members

### 4.2 Prohibited Conduct

You may not:

- Use the Service to access systems, data, or resources without authorization
- Attempt to circumvent security measures or access controls
- Reverse engineer, decompile, or disassemble any part of the Service
- Use the Service to transmit malware, viruses, or malicious code
- Perform load testing or penetration testing without prior written consent
- Scrape, crawl, or spider the Service
- Interfere with or disrupt the Service or its infrastructure
- Use the Service in violation of any applicable law or regulation
- Impersonate any person or entity
- Collect or harvest personal information without consent
- Use the Service for competitive analysis or to build a competitive product

### 4.3 Third-Party Integration Compliance

When using OpenTrace's integration features (GitHub, GitLab, Slack, Grafana, Jaeger, AWS, etc.), you agree to:

- Comply with the terms of service of each integrated platform
- Only integrate systems and data sources you have authorization to access
- Not exceed rate limits or usage restrictions of integrated services
- Maintain valid credentials and API keys for your integrations

---

## 5. Data and Privacy

### 5.1 Data You Provide

When using OpenTrace, you may provide or the Service may collect:

- **Account Information**: Email, name, organization details, authentication credentials
- **Investigation Data**: Incident descriptions, hypotheses, notes, comments
- **System Data**: Logs, metrics, traces, error reports, code repository information
- **Integration Credentials**: OAuth tokens, API keys, webhooks for third-party services
- **File Uploads**: Evidence files, screenshots, configuration files

### 5.2 Data We Collect

OpenTrace automatically collects:

- **Usage Data**: API requests, feature usage, session duration
- **Technical Data**: IP addresses, browser information, device information
- **Timeline Events**: Investigation progress, agent actions, evidence collection
- **Observability Data**: Platform telemetry via OpenTelemetry tracing

### 5.3 Data Storage and Processing

Your data is stored and processed using OpenTrace-managed systems and approved subprocessors, including:

* **Google Firestore** (investigation metadata and events)
* **Neo4j** (system and context graphs)
* **PostgreSQL** (activity streams and audit logs)
* **Firebase Storage** (file uploads and evidence)
* **Google Vertex** AI (LLM-based analysis)

**Data Location and Subprocessors**
Data storage locations and subprocessors are described in our **Privacy Policy and Subprocessor List**, which may be updated from time to time with reasonable notice. OpenTrace does not guarantee that data will be processed exclusively in a single geographic region unless expressly agreed in writing.

### 5.4 AI Processing of Your Data

When you use OpenTrace:

* Investigation data may be transmitted to Google Vertex AI for real-time analysis
* **Model inputs and outputs may be temporarily processed and logged by OpenTrace solely for service operation, debugging, and security purposes**

**Content logging is subject to access controls, retention limits, and masking of sensitive fields where supported**

* AI processing is performed to provide the Service and **is not used to train or fine-tune underlying AI models**

**Enterprise Controls**

Enterprise customers may be eligible for configuration options to limit or disable content-level logging, subject to technical feasibility and support agreements.

**Sensitive Data Obligation**

You agree **not to submit secrets, credentials, cryptographic keys, or unnecessary personally identifiable information** to the Service. You are responsible for implementing reasonable filtering, redaction, and access controls prior to submitting data for analysis.

### 5.5 Data Retention

Data retention is governed by **organization-level configuration settings** and our Privacy Policy.
Unless otherwise configured or required by law:

* Investigation data is retained while your account is active
* Deleted investigations are retained for a limited recovery period, then permanently deleted
* Account data is deleted within a reasonable period following account termination
* Security and audit logs may be retained for compliance and integrity purposes

### 5.6 Data Access and Deletion

You have the right to:

- Access your investigation data via the UI or API
- Export your investigation data in JSON format
- Delete individual investigations
- Request deletion of your account and all associated data

To exercise these rights, contact us at support@opentrace.com.

### 5.7 Privacy Policy

Our collection, use, and protection of your personal information is governed by our Privacy Policy at [docs.opentrace.com/privacy-policy](https://docs.opentrace.com/privacy-policy/). The Privacy Policy is incorporated into these Terms by reference.

### 5.8 Security Measures

We implement industry-standard security measures including:

- Encryption in transit (TLS/HTTPS)
- Encryption at rest (Google Cloud encryption)
- Organization-based data isolation
- JWT bearer token authentication
- Regular security audits and monitoring
- OpenTelemetry tracing for security event detection

However, no method of transmission or storage is 100% secure. You use the Service at your own risk.

---

## 6. Third-Party Integrations

### 6.1 Integration Authorization

OpenTrace integrates with external services using:

- **OAuth 2.0**: GitHub, GitLab, Slack, Google authentication
- **API Keys**: Grafana, Bugsnag, Sentry, FusionReactor, OpenSearch
- **Webhooks**: Slack events, GitHub events, GitLab events
- **MCP Protocol**: Standardized tool integration for logs, metrics, traces

You grant OpenTrace permission to:

- Access integrated services on your behalf
- Query data from integrated services during investigations
- Store integration credentials securely (encrypted)
- Use webhooks to trigger investigations automatically

### 6.2 Integration Data Access

When you connect integrations, OpenTrace may access:

- **GitHub/GitLab**: Repository files, commit history, issues, pull requests, webhook events
- **Slack**: Message content (when mentioned), channel information, user information
- **Grafana**: Dashboards, Prometheus metrics, Loki logs, Tempo traces, alerts
- **Jaeger**: Distributed traces and spans
- **AWS**: EKS cluster metadata, infrastructure information
- **Bugsnag/Sentry**: Error reports, stack traces, occurrence data
- **OpenSearch**: Log data and search results

### 6.3 Your Responsibilities

You are responsible for:

- Ensuring you have authorization to integrate third-party services
- Maintaining valid credentials for integrations
- Complying with third-party terms of service
- Revoking access when no longer needed
- Monitoring integration usage and costs

### 6.4 Third-Party Terms

Your use of integrated services is subject to their respective terms of service. OpenTrace is not responsible for:

- Availability or performance of third-party services
- Changes to third-party APIs or terms
- Data loss or corruption in third-party services
- Violations of third-party terms by you or your users

### 6.5 Integration Limits

We may impose limits on:

- Number of integrations per organization
- API call volume to integrated services
- Data retrieval from integrated services
- Webhook frequency and payload size

---

## 7. Intellectual Property Rights

### 7.1 OpenTrace IP

OpenTrace and all related technology, including:

- Source code, algorithms, and software
- User interface design and branding
- Documentation and training materials
- AI models, prompts, and workflows (excluding underlying Google models)
- MCP server implementations

...are owned by OpenTrace or our licensors and protected by copyright, trademark, and other intellectual property laws.

**License Grant to You**: Subject to these Terms, we grant you a limited, non-exclusive, non-transferable, revocable license to access and use the Service for your internal business purposes.

### 7.2 Your Data and Content

You retain all ownership rights to Customer Data, including investigation data, files, evidence, comments, and system information submitted to or processed by the Service.

**License Grant to OpenTrace**

You grant OpenTrace a limited, worldwide, non-exclusive, royalty-free license to **host, process, transmit, and display Customer Data solely to provide, secure, and support the Service**.

**No Training by Default**

OpenTrace **does not use Customer Data to train, fine-tune, or improve AI models** unless a **separate written agreement** is executed with you that expressly permits such use.

**Aggregated and De-Identified Data**

OpenTrace may generate and use aggregated, de-identified data derived from Service usage for analytics and service improvement, provided that such data:

* Does not identify you or any individual
* Cannot reasonably be re-identified
* Is not shared in customer-identifiable form

### 7.3 AI-Generated Content

Content generated by OpenTrace’s AI features:

* Is provided “as-is” and without warranties
* May be inaccurate, incomplete, or misleading
* Requires human review and validation prior to use
* Does not constitute professional advice

Ownership and usage rights in AI-generated content follow the same terms as Customer Data.

### 7.4 Feedback and Suggestions

If you provide feedback, suggestions, or ideas about OpenTrace:

- We may use them without restriction or compensation
- You waive any intellectual property rights in such feedback
- We have no obligation to implement or respond to feedback

### 7.5 Open Source Components

OpenTrace includes open source software components, each subject to its own license terms. A list of open source components is available at [OPEN SOURCE URL].

---

## 8. Payment Terms

### 8.1 Billing

- Subscription fees are billed [monthly / annually] in advance
- Fees are non-refundable except as required by law
- All fees are in [USD / CURRENCY] and exclude applicable taxes
- You are responsible for all taxes, duties, and assessments

### 8.2 Usage-Based Charges

In addition to subscription fees, you may incur charges for:

- [AI model API calls exceeding plan limits]
- [Data storage exceeding plan limits]
- [Investigation volume exceeding plan limits]
- [Premium integrations or features]

Usage-based charges are billed [monthly] in arrears.

### 8.3 Payment Methods

We accept payment via:

- Credit card (Visa, Mastercard, American Express)
- [ACH bank transfer]
- [Invoice (for enterprise customers)]

You authorize us to charge your payment method on file.

### 8.4 Late Payment

If payment fails:

- We will attempt to collect payment for 15 days
- Your access may be suspended after 15 days
- Your account may be terminated after 30 days
- You remain liable for all outstanding charges plus collection costs

### 8.5 Price Changes

We may change pricing with 30 days' advance notice. Price changes apply:

- Immediately for new customers
- At next renewal for existing customers

### 8.6 Refund Policy

[**TO BE DETERMINED** - Add specific refund terms]

---

## 9. Service Level and Availability

### 9.1 Service Availability

OpenTrace is provided on an "as available" basis. We do not guarantee:

- Uninterrupted access to the Service
- Error-free operation
- Specific uptime percentages (unless covered by separate SLA)
- Compatibility with all browsers or devices

### 9.2 Maintenance and Downtime

We may:

- Perform scheduled maintenance with [24 hours] advance notice
- Perform emergency maintenance without notice
- Temporarily suspend Service for security, legal, or technical reasons

### 9.3 Service Level Agreement (SLA)

[OPTIONAL - For enterprise customers]

Enterprise customers may be eligible for a separate Service Level Agreement. Contact [SALES EMAIL] for details.

### 9.4 Service Modifications

We reserve the right to:

- Add, modify, or remove features
- Change Service architecture or technology
- Update user interface design
- Modify APIs (with reasonable notice for breaking changes)

We will make reasonable efforts to maintain backward compatibility and provide migration assistance for significant changes.

---

## 10. Limitation of Liability

### 10.1 Disclaimer of Warranties

**THE SERVICE IS PROVIDED "AS IS" AND "AS AVAILABLE" WITHOUT WARRANTIES OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO:**

- **MERCHANTABILITY**
- **FITNESS FOR A PARTICULAR PURPOSE**
- **NON-INFRINGEMENT**
- **ACCURACY OR RELIABILITY OF AI-GENERATED CONTENT**
- **AVAILABILITY OR UNINTERRUPTED ACCESS**
- **SECURITY OR FREEDOM FROM VIRUSES**
- **RESULTS OR OUTCOMES FROM USE OF THE SERVICE**

**AI-SPECIFIC DISCLAIMER**: OpenTrace uses artificial intelligence and large language models that may produce inaccurate, incomplete, biased, or inappropriate output. We do not warrant the accuracy, completeness, or reliability of any AI-generated insights, analysis, or recommendations. You are solely responsible for reviewing, validating, and acting on (or not acting on) AI-generated content.

### 10.2 Limitation of Liability

**TO THE MAXIMUM EXTENT PERMITTED BY LAW, OPENTRACE SHALL NOT BE LIABLE FOR:**

- **INDIRECT, INCIDENTAL, SPECIAL, CONSEQUENTIAL, OR EXEMPLARY DAMAGES**
- **LOSS OF PROFITS, REVENUE, DATA, OR BUSINESS OPPORTUNITIES**
- **SYSTEM DOWNTIME OR INCIDENT RESPONSE DELAYS**
- **ERRORS IN AI-GENERATED ANALYSIS OR RECOMMENDATIONS**
- **ACTIONS TAKEN BASED ON SERVICE OUTPUT**
- **UNAUTHORIZED ACCESS TO YOUR DATA**
- **THIRD-PARTY INTEGRATION FAILURES**
- **DAMAGE TO YOUR SYSTEMS FROM SERVICE USE**

**OPENTRACE'S TOTAL LIABILITY FOR ALL CLAIMS ARISING FROM OR RELATED TO THESE TERMS SHALL NOT EXCEED THE AMOUNT YOU PAID TO OPENTRACE IN THE 12 MONTHS PRECEDING THE CLAIM (OR $100 IF NO FEES WERE PAID).**

### 10.3 Critical Systems Warning

**⚠️ CRITICAL NOTICE**: OpenTrace is a diagnostic and analysis tool. **DO NOT USE OPENTRACE AS THE SOLE BASIS FOR OPERATIONAL DECISIONS IN:**

- Life-critical systems (medical devices, emergency services)
- Safety-critical systems (aviation, automotive, industrial control)
- Financial transaction systems requiring regulatory compliance
- Any system where failure could result in death, injury, or significant property damage

You are solely responsible for human oversight and validation of all Service outputs before taking action.

### 10.4 Indemnification

You agree to indemnify, defend, and hold harmless OpenTrace and its officers, directors, employees, and agents from any claims, damages, losses, liabilities, and expenses (including legal fees) arising from:

- Your use or misuse of the Service
- Your violation of these Terms
- Your violation of third-party rights
- Your violation of applicable laws or regulations
- Actions taken based on AI-generated content
- Unauthorized access to systems via integrations
- Your data or content submitted to the Service

---

## 11. Term and Termination

### 11.1 Term

These Terms begin when you first access the Service and continue until terminated by either party.

### 11.2 Termination by You

You may terminate at any time by:

- Canceling your subscription via the UI
- Emailing support@opentrace.com with termination request
- Closing your account in account settings

Termination is effective at the end of your current billing period. No refunds for partial periods.

### 11.3 Termination by OpenTrace

We may suspend or terminate your access immediately if:

- You breach these Terms
- You fail to pay fees when due
- Your use poses a security risk
- We are required by law to terminate
- We discontinue the Service (with 30 days' notice)

### 11.4 Effect of Termination

Upon termination or expiration of the Service:

* Your access to the Service will cease
* You remain responsible for any outstanding fees
* Customer Data will be retained and deleted in accordance with:
  * Your organization’s retention settings, and
  * Our Privacy Policy
* You may request a data export for a limited period following termination, subject to authentication and security controls

### 11.5 Data Export

You may export your data before termination by:

- Using the data export feature in the UI
- Requesting export via support@opentrace.com
- Accessing data via API (while access is active)

Data exports are provided in JSON format.

---

## 12. Confidentiality

### 12.1 Confidential Information

Confidential Information does **not** include information that:

* Is or becomes publicly available without breach
* Was lawfully known prior to disclosure
* Is independently developed without reference to Confidential Information

### 12.2 Confidentiality Obligations

You agree to:

- Not disclose OpenTrace's Confidential Information
- Use Confidential Information only for authorized purposes
- Protect Confidential Information with reasonable care
- Notify us promptly of any unauthorized disclosure

We will treat your data and account information as confidential pursuant to our Privacy Policy.

---

## 13. General Legal Terms

### 13.1 Governing Law

These Terms are governed by the laws of [STATE/COUNTRY], without regard to conflict of law principles.

### 13.2 Dispute Resolution

**[CHOOSE ONE APPROACH]:**

**Option A - Arbitration**:
Any dispute arising from these Terms shall be resolved by binding arbitration under the rules of [ARBITRATION PROVIDER] in [LOCATION]. You waive the right to a jury trial or to participate in a class action.

**Option B - Court Jurisdiction**:
Any dispute arising from these Terms shall be resolved exclusively in the state or federal courts located in [LOCATION]. You consent to personal jurisdiction in these courts.

### 13.3 Class Action Waiver

You agree to resolve disputes with OpenTrace on an individual basis. You waive the right to participate in class actions, class arbitrations, or representative actions.

### 13.4 Modifications to Terms

We may modify these Terms at any time by:

- Posting updated Terms on our website
- Notifying you via email or in-app notification
- Requiring acceptance of new Terms on next login (for material changes)

Continued use after changes constitutes acceptance. If you disagree with changes, your sole remedy is to terminate your account.

### 13.5 Assignment

You may not assign or transfer your rights under these Terms without our written consent. We may assign these Terms without your consent in connection with a merger, acquisition, or sale of assets.

### 13.6 Entire Agreement

These Terms, together with our Privacy Policy and any additional agreements you enter into with OpenTrace, constitute the entire agreement between you and OpenTrace and supersede all prior agreements, understandings, and communications.

### 13.7 Severability

If any provision of these Terms is found unenforceable, the remaining provisions remain in full effect, and the unenforceable provision is modified to the minimum extent necessary to make it enforceable.

### 13.8 No Waiver

Our failure to enforce any provision does not waive our right to enforce it later. Any waiver must be in writing and signed by an authorized representative.

### 13.9 Force Majeure

We are not liable for delays or failures due to causes beyond our reasonable control, including:

- Natural disasters, pandemics, or acts of God
- War, terrorism, or civil unrest
- Government actions or regulations
- Labor disputes or strikes
- Internet or telecommunications failures
- Third-party service provider failures (Google Cloud, etc.)

### 13.10 Export Compliance

You represent that you are not located in a country subject to U.S. embargo or designated as a "terrorist supporting" country, and you are not on any U.S. government list of prohibited or restricted parties.

You agree to comply with all export and import laws when using the Service.

### 13.11 Government Use

If you are a U.S. government entity, OpenTrace is a "commercial item" as defined in FAR 2.101, and licensing is in accordance with these Terms.

### 13.12 Notices

Notices to you may be sent to the email address associated with your account. Notices to OpenTrace should be sent to:

[COMPANY LEGAL NAME]
[ADDRESS]
Email: [LEGAL EMAIL]

### 13.13 Relationship

These Terms do not create a partnership, joint venture, employment, or agency relationship between you and OpenTrace.

---

## 14. Contact Information

For questions about these Terms, contact us at:

**Email**: support@opentrace.com<br/>
**Address**: 14205 N MO PAC EXPY, STE 570, PMB 640435<br/>
Austin, TX 78728, USA<br/>
**Website**: https://opentrace.com

For technical support: [SUPPORT EMAIL]
For security issues: [SECURITY EMAIL]
For privacy concerns: [PRIVACY EMAIL]

---

## 15. Definitions

- **"Account"**: Your registered user account for accessing the Service
- **"AI"**: Artificial intelligence, including large language models (LLMs)
- **"API"**: Application Programming Interface provided by OpenTrace
- **"Evidence"**: Files, screenshots, logs, or data collected during an investigation
- **"Integration"**: Connection to third-party services like GitHub, Slack, Grafana
- **"Investigation"**: A specific incident analysis session in OpenTrace
- **"MCP"**: Model Context Protocol for tool integration
- **"Organization"**: Multi-user tenant account in OpenTrace
- **"Service"**: OpenTrace Insight Platform and all related services
- **"Timeline"**: Chronological record of investigation events and AI agent actions
- **"You"**: The individual or entity using OpenTrace

---

## Version History

- **[DATE]**: Initial draft created from codebase analysis

---

**END OF TERMS OF SERVICE**

---

## NEXT STEPS FOR LEGAL REVIEW

This draft requires review and completion of the following by legal counsel:

1. **[TO BE DETERMINED]** sections need specific details
2. **Contact information** needs to be filled in (emails, addresses)
3. **Governing law and jurisdiction** must be selected
4. **Dispute resolution method** (arbitration vs. courts) must be chosen
5. **Pricing and billing terms** need to be finalized
6. **Data residency and compliance** (GDPR, CCPA, etc.) should be added if applicable
7. **Export control** details should be verified
8. **Insurance and liability caps** should be reviewed by counsel
9. **Enterprise vs. standard terms** may need separate agreements
10. **Compliance certifications** (SOC 2, ISO 27001, etc.) should be referenced if available

This document was generated from source code analysis and general legal templates. It must not be used without thorough review by qualified legal counsel familiar with software licensing, SaaS agreements, AI/ML liability, and applicable jurisdictional requirements.
