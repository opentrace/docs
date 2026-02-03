# Privacy Policy

**OpenTrace**

**Effective Date:** January 23, 2026

**Last Updated:** January 23, 2026

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

OpenTrace allows customers to connect external data sources, including GitHub, GitLab, Linear, Kubernetes, Slack, and various observability platforms (Grafana, Datadog, Jaeger, AWS). When you connect these services, OpenTrace stores OAuth credentials and API tokens (encrypted) and may access and process data from these platforms, which may include:

- Repository information and code metadata
- Commit history, author information, and profile pictures
- Code changes, file paths, and line numbers from diffs
- Pull request and merge request data, including reviewers and approvers
- Issue and ticket data, including assignee information and comments
- CI/CD pipeline execution data
- Kubernetes cluster and deployment information
- Slack workspace IDs, team information, and bot tokens
- AWS credentials for cluster access
- Log, metric, and trace data from observability platforms

This data may contain personal identifiers such as usernames, email addresses, profile pictures, or other information associated with commits, tickets, or system configurations. OpenTrace stores summaries, metadata, and OAuth credentials (encrypted) derived from connected sources and may access original source data as needed to provide the Service.

---

## 3. How We Use Your Information

We use the information we collect for the following purposes:

- **Account Management:** To create and manage your user account and organization memberships
- **Service Delivery:** To provide, operate, and maintain the Service, including:
  - AI-powered investigation and incident analysis using large language models
  - Processing and analyzing data from connected sources (GitHub, GitLab, Kubernetes, etc.)
  - Generating summaries and insights from your operational data
  - Creating and managing investigations, conversations, and timeline events
  - Providing personalized features based on your role and organization context
- **Service Improvement:** To understand how users interact with our Service and to improve functionality through analytics and session replay analysis
- **Security:** To detect, prevent, and address technical issues and security threats
- **Feature Management:** To enable or disable features based on your organization and user context
- **Legal Compliance:** To comply with applicable laws and regulations

We do not use your personal information for marketing purposes or send promotional communications.

**AI and Machine Learning:** We use AI models (including Google Vertex AI) to analyze your investigation data and connected sources. This processing occurs to provide core Service functionality and is not used to train public models.

---

## 4. Third-Party Service Providers

We share your information with the following third-party service providers who assist us in operating the Service:

| Provider | Purpose | Data Shared |
|----------|---------|-------------|
| **Clerk** | User authentication and account management | Email, name, profile picture, organization membership and role, account credentials |
| **Firebase/Google Cloud** | Primary data storage, authentication, and file storage | All application data including user profile, investigations, conversations, timeline events, integration settings, and encrypted OAuth credentials |
| **Google Analytics** | Usage analytics and service improvement (via Firebase) | User ID, organization ID, page views, user interactions, device information |
| **Grafana Faro** | Application performance monitoring and error tracking | Performance metrics, browser errors, application version, environment context, user interaction data |
| **Sentry** | Error tracking, debugging, and session replay | User ID, email, organization ID/name/slug, error logs, stack traces, performance traces, session recordings (with text masking and privacy controls), breadcrumbs, console messages, HTTP request metadata |
| **LaunchDarkly** | Feature flag management and experimentation | User ID, organization ID/slug, user's organization role, application version |
| **OpenTelemetry** | Distributed tracing and observability (optional) | Distributed traces, timing information, service name and version, trace context |
| **Google** | OAuth authentication (optional) | Authentication tokens, basic profile information |

These service providers are contractually obligated to protect your information and may only use it to provide services to us.

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

We use Sentry's session replay functionality to record user interactions with the application for debugging and service improvement purposes. Session replays capture:

- Screen interactions and clicks
- Page navigation
- Form interactions (with input masking enabled)
- Network requests and responses (filtered for sensitive data)

**Privacy Controls:**
- Text content is automatically masked
- Media elements (images, videos) are blocked
- Input fields are masked to prevent capture of sensitive data
- Sensitive HTTP headers and query parameters are filtered
- Only sessions from internal domains are recorded

You cannot opt out of session replay while using the Service, but all recordings are subject to strict privacy controls.

### 5.5 Managing Your Preferences

Most web browsers allow you to control cookies through their settings. However, disabling cookies may limit your ability to use certain features of the Service.

---

## 6. Data Storage and Security

### 6.1 Data Location

Your personal information is stored in the following locations:

- **Clerk** (authentication provider): Primary servers and databases located in the United States
- **Firebase/Firestore** (primary data storage): Google Cloud Platform project in the European Union
- **Google Cloud Storage** (file uploads): Storage bucket in the European Union
- **Sentry** (error tracking): Data stored in Sentry's European (Germany) region
- **Other third-party services**: May store data in the United States or other regions as specified by their privacy policies

### 6.2 Security Measures

We implement appropriate technical measures to protect your personal information, including:

- Encryption of data in transit using industry-standard protocols (TLS/SSL)
- Encryption of data at rest via Firebase/Firestore and Google Cloud Platform
- OAuth credentials and API tokens stored in encrypted Firestore collections using Google Cloud Key Management Service (KMS)
- Service account tokens stored as cryptographic hashes
- JWT-based authentication with token expiration
- Role-based access control (RBAC) for organizational data

While we strive to protect your information, no method of transmission over the Internet or electronic storage is completely secure. We cannot guarantee absolute security.

---

## 7. Data Retention

We retain your personal information for as long as your account remains active or as needed to provide the Service. Specific retention policies:

- **User account data**: Retained until account deletion
- **Investigations and conversations**: Retained according to organization settings (configurable investigation lifetime)
- **Timeline events**: Retained according to organization settings (configurable timeline event lifetime)
- **OAuth credentials and integration settings**: Deleted immediately when you disconnect an integration
- **Session replays and error logs**: Retained by Sentry according to their retention policies (typically 90 days)
- **Analytics data**: Retained by Google Analytics and Grafana Faro according to their retention policies
- **Audit logs**: May be retained for longer periods for security and compliance purposes

Upon account deletion, we will delete or anonymize your personal information within a reasonable timeframe, except where retention is required by law or for legitimate business purposes.

For customer-connected data sources (GitHub, GitLab, Linear, Kubernetes, Slack), stored summaries, metadata, and encrypted credentials will be deleted when you disconnect the integration or delete your account.

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

**Automated Decision-Making:** We do not use automated decision-making or profiling that produces legal or similarly significant effects.

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

Your information may be transferred to and processed in countries other than your country of residence, including the United States and countries within the European Union. These countries may have data protection laws that differ from your jurisdiction.

When we transfer data internationally, we implement appropriate safeguards to protect your information in accordance with applicable law.

---

## 10. Customer Data Processing

When you connect external data sources (such as GitHub, GitLab, Linear, Kubernetes, Slack, AWS, or observability platforms like Grafana, Datadog, Jaeger) to OpenTrace, we act as a data processor on your behalf. You, as the customer, remain the data controller for any personal information contained within your connected data sources.

OpenTrace uses AI models (including Google Vertex AI) to process and analyze data from your connected sources. This processing is performed solely to provide the Service to you and is not used to train public or third-party AI models.

If your use of OpenTrace involves processing personal data subject to GDPR or other data protection regulations, we recommend entering into a Data Processing Agreement (DPA) with us. Please contact support@opentrace.com to request a DPA.

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

**OpenTrace**  
14205 N MO PAC EXPY, STE 570, PMB 640435  
Austin, TX 78728, USA  
Email: support@opentrace.com

We will respond to your inquiry within a reasonable timeframe and in accordance with applicable law.

---

*This Privacy Policy is provided for informational purposes and does not constitute legal advice. We recommend consulting with a qualified legal professional to ensure compliance with all applicable laws and regulations.*
