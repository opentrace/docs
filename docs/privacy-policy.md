# Privacy Policy

**OpenTrace**

**Effective Date:** February 6, 2026

**Last Updated:** February 6, 2026

---

## 1. Introduction

OpenTrace ("Company," "we," "us," or "our") is committed to protecting your privacy. This Privacy Policy explains how we collect, use, disclose, and safeguard your information when you use our application and services (collectively, the "Service").

By accessing or using the Service, you agree to the terms of this Privacy Policy. If you do not agree with the terms of this Privacy Policy, please do not access the Service.

---

## 2. Information We Collect

### 2.1 Information You Provide Directly

When you create an account with OpenTrace, we collect the following personal information:

- Email address
- Full name
- Profile picture or avatar URL (if provided through authentication provider)
- Organization name and logo (if provided)

Additionally, when using the Service, you may provide:

- Investigation titles and descriptions
- Chat and conversation messages
- Custom labels and tags
- Integration configuration names and descriptions
- Service account names and descriptions

### 2.2 Information Collected Automatically

When you access the Service, we may automatically collect certain information, including:

- Device and browser information
- IP address
- Usage data and interaction patterns
- Log data

### 2.3 Information from Third-Party Authentication

If you choose to sign in using Google, we receive basic profile information (such as your name and email address) as authorized by your Google account settings.

### 2.4 Customer-Connected Data Sources

OpenTrace allows customers to connect external data sources, including GitHub, GitLab, Linear, Kubernetes, Slack, AWS, and observability platforms (such as Grafana, Datadog, and Jaeger).

When you connect these services, OpenTrace stores **OAuth credentials and API tokens in encrypted form** and may access and process data from these platforms **solely to provide the Service**.

This data may include:

* Repository information and code metadata
* Commit history, author information, and profile pictures
* Code changes, file paths, and line numbers from diffs
* Pull request and merge request data
* Issue and ticket data, including comments and assignees
* CI/CD pipeline execution data
* Kubernetes cluster metadata and deployment information
* Slack workspace identifiers and message content **when explicitly referenced or authorized**

* Observability data such as logs, metrics, and traces

This data **may contain personal identifiers** such as usernames, email addresses, or profile images.

**Role Clarification**

OpenTrace processes customer-connected data **as a data processor acting on your instructions**. You remain the data controller for any personal data contained in connected systems.

---

## 3. How We Use Your Information

**AI and Machine Learning**

OpenTrace uses artificial intelligence and machine learning models, including Google Vertex AI (Gemini models), to assist in analyzing investigation data and connected system context.
AI processing is used to:

* Correlate signals across connected systems
* Generate hypotheses, summaries, and explanations
* Assist users in understanding system behavior

**Important AI Limitations and Safeguards**:

* AI outputs are **informational and assistive only**
* Outputs may be inaccurate, incomplete, or misleading
* **Human review is required** before relying on AI outputs
* OpenTrace does **not** perform automated decision-making that produces legal or similarly significant effects

**Model Training Assurance**

Customer data and personal information are **not used to train public or third-party AI models**. AI providers process data under contractual terms that prohibit retention or reuse of customer data for model training.

---

## 4. Third-Party Service Providers

**Subprocessor Use**

We engage third-party service providers (“Subprocessors”) to support delivery of the Service. These providers process personal data **only on our instructions** and are contractually obligated to protect it.

We maintain an up-to-date list of Subprocessors, including their purpose and data location, available upon request or via our Privacy Policy page.

We may update Subprocessors from time to time and will provide notice where required by applicable law.

---

## 5. Cookies and Tracking Technologies

OpenTrace uses the following technologies to enhance your experience:

### 5.1 Cookies

Small text files stored on your device that help us recognize you and remember your preferences.

### 5.2 Session IDs

Temporary identifiers that maintain your session while you use the Service.

### 5.3 Local Storage

Browser-based storage used to save application state and preferences locally on your device.

### 5.4 Session Replay

We use session replay technology (via Sentry) to diagnose errors, improve service reliability, and investigate user-reported issues.  Session replay may capture:

* Screen interactions and navigation
* Clicks and UI events
* Network request metadata (with sensitive data filtered)

**Privacy Controls:**

* Text content is masked by default
* Input fields are masked
* Media elements are excluded
* Sensitive headers and parameters are filtered

You cannot opt out of session replay while using the Service.
**Session replay is enabled only where necessary for service reliability and security.**
**Enterprise customers may request alternative arrangements, subject to technical feasibility.**

### 5.5 Managing Your Preferences

Most web browsers allow you to control cookies through their settings. However, disabling cookies may limit your ability to use certain features of the Service.

---

## 6. Data Storage and Security

### 6.1 Data Location

Personal information is stored and processed using OpenTrace systems and approved Subprocessors. Data locations and residency details are described in our Privacy Policy and Subprocessor documentation and may change over time with appropriate safeguards.

### 6.2 Security Measures

We implement appropriate technical measures to protect your personal information, including:

- Encryption of data in transit using industry-standard protocols (TLS/SSL)
- Encryption of data at rest via Firebase/Firestore and Google Cloud Platform
- OAuth credentials and API tokens stored in encrypted Firestore collections using Google Cloud Key Management Service (KMS)
- Service account tokens stored as cryptographic hashes
- JWT-based authentication with token expiration
- Role-based access control (RBAC) for organizational data

While we strive to protect your information, no method of transmission over the Internet or electronic storage is completely secure. We cannot guarantee absolute security.

### 6.3 Security Incident Notification

In the event of a confirmed personal data breach, OpenTrace will notify affected customers **without undue delay** and in accordance with applicable law. Notifications will include, where reasonably available, information about the nature of the incident and mitigation steps taken.

---

## 7. Data Retention

We retain personal information **only for as long as necessary** to provide the Service or as required by law.  Retention periods may be configured at the organization level and include:

* Account data: retained until account deletion
* Investigation data: retained per organization configuration
* Integration credentials: deleted upon disconnection
* Audit and security logs: retained for limited periods for compliance

Following account termination, data is deleted or anonymized within a reasonable timeframe unless retention is legally required.

---

## 8. Your Rights and Choices

Depending on your location, you may have the following rights regarding your personal information:

### 8.1 All Users

- **Access:** Request a copy of your personal information
- **Correction:** Request correction of inaccurate information
- **Deletion:** Request deletion of your personal information
- **Data Portability:** Request your data in a portable format

To exercise any of these rights, please contact us at support@opentrace.com.

### 8.2 European Economic Area (EEA) Residents

If you are located in the EEA, you have additional rights under the General Data Protection Regulation (GDPR), including:

- The right to object to processing
- The right to restrict processing
- The right to withdraw consent (where processing is based on consent)
- The right to lodge a complaint with a supervisory authority

**Legal Basis for Processing:** We process your personal information based on the following legal grounds:

- **Contract Performance:** Processing necessary to provide the Service you requested
- **Legitimate Interests:** Processing necessary for our legitimate business interests, such as improving our Service and ensuring security
- **Legal Obligation:** Processing necessary to comply with applicable laws

**Automated Decision-Making:** OpenTrace does **not** engage in automated decision-making or profiling that produces legal or similarly significant effects within the meaning of GDPR Article 22.

### 8.3 California Residents

If you are a California resident, you have rights under the California Consumer Privacy Act (CCPA), including:

- The right to know what personal information is collected
- The right to know whether personal information is sold or disclosed and to whom
- The right to opt out of the sale of personal information
- The right to request deletion of personal information
- The right to non-discrimination for exercising your rights

**We do not sell your personal information.**

---

## 9. International Data Transfers

Your information may be processed in countries other than your country of residence, including the United States and the European Union.

Where required, OpenTrace relies on appropriate safeguards for international transfers, such as **Standard Contractual Clauses (SCCs)** or equivalent mechanisms, in accordance with applicable data protection laws.

---

## 10. Customer Data Processing

OpenTrace processes customer-connected data solely to provide the Service. AI processing does not involve training or improving foundation models unless explicitly agreed in writing.

Customers remain responsible for determining whether their use of OpenTrace complies with applicable data protection obligations.

---

## 11. Children's Privacy

The Service is not intended for individuals under the age of 13. We do not knowingly collect personal information from children under 13. If you are a parent or guardian and believe your child has provided us with personal information, please contact us at support@opentrace.com, and we will take steps to delete such information.

---

## 12. Changes to This Privacy Policy

We may update this Privacy Policy from time to time. When we make changes, we will update the "Last Updated" date at the top of this policy. We encourage you to review this Privacy Policy periodically.

For material changes, we will provide notice through the Service or by other means as required by applicable law.

---

## 13. Contact Us

If you have questions, concerns, or requests regarding this Privacy Policy or our privacy practices, please contact us at:

**OpenTrace**<br/>
14205 N MO PAC EXPY, STE 570, PMB 640435<br/>
Austin, TX 78728, USA<br/>
Email: support@opentrace.com

We will respond to your inquiry within a reasonable timeframe and in accordance with applicable law.

---

*This Privacy Policy is provided for informational purposes and does not constitute legal advice. We recommend consulting with a qualified legal professional to ensure compliance with all applicable laws and regulations.*
