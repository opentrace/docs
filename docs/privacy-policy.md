# OpenTrace Privacy Statement

Last updated: April 30, 2026 · Effective date: April 30, 2026

## 1. About this Privacy Statement

This Privacy Statement explains how OpenTrace, Inc. ("OpenTrace," "we," "us," or "our") collects, uses, discloses, and otherwise processes personal data in connection with our hosted code intelligence service, our website, the OpenTrace open-source tools when used in a manner that interacts with our infrastructure, and our related products and services (together, the "Service").

### 1.1 Who we are and how to contact us

OpenTrace, Inc. is a Delaware corporation with its principal place of business at 14205 N Mo Pac Expy, Ste 570, PMB 640435, Austin, Texas 78728-6529, USA. For privacy questions, you can reach us at privacy@opentrace.com.

### 1.2 Our role under data protection law

When we provide the Service to a business customer, that customer typically determines what personal data is processed through the Service and for what purpose. In those cases, the customer is the "controller" (or "business," in U.S. terminology) and OpenTrace is the "processor" (or "service provider"). The customer's own privacy notice governs how the personal data of its end users is handled within that customer's environment.

In addition to that processor role, OpenTrace acts as a controller for certain limited processing — for example, when we process information about visitors to our website, account administrators who interact with us directly, or when we process technical data to operate, secure, and improve the Service. This Privacy Statement describes our processing in that controller capacity. Where we act as a processor, our obligations are set out in our Data Processing Addendum.

### 1.3 Scope

This Privacy Statement applies to:

- visitors to opentrace.com and other OpenTrace-operated websites;

- individuals who sign up for or administer an OpenTrace account, on free plans and paid plans alike;

- users authorized by an OpenTrace customer to access the Service ("Authorized Users");

- users of the OpenTrace open-source tools to the extent their use interacts with OpenTrace infrastructure (for example, when uploading derived artifacts to the Service); and

- individuals who contact OpenTrace, attend our events, or otherwise interact with us.

This Statement does not apply to:

- use of the OpenTrace open-source tools that is purely local and does not interact with OpenTrace infrastructure — that use is governed exclusively by the applicable open-source license;

- third-party services we integrate with, even when accessed through the Service — those services are governed by their own privacy notices; or

- AI providers you connect to using your own API keys — your direct API call to and from those providers is governed by your agreement with the AI provider. Where prompts, responses, saved chat history, or related content are saved to or processed by the OpenTrace Service, OpenTrace treats that content as Customer Data under this Statement.

## 2. How OpenTrace processes data

Because OpenTrace can be used in several configurations, the data we process — and where it goes — depends on how you use the product. This Section walks through each configuration so you can see exactly what reaches us and what does not.

### 2.1 Local-only use of the open-source tools

When you use the OpenTrace open-source tools entirely on your own machine, without connecting to OpenTrace infrastructure, no source code, derived artifacts, query content, or output content reaches OpenTrace. The open-source tools read your codebase, build the knowledge graph and indexes locally, and store everything on your own machine. Embeddings used by the open-source tools are computed by an open-source embedding model running on your machine; no third-party AI provider is involved.

We may receive limited information from the open-source tools in two narrow cases:

- If the open-source tools include a web-based interface that connects to OpenTrace infrastructure for any reason (for example, account-linked features), the technical and usage data described in Section 3 may be collected during that connection.

- If you choose to install or upgrade the open-source tools through a delivery channel we operate, we may receive standard distribution telemetry such as version, platform, and download timestamps.

### 2.2 Connected use of the hosted Service

When you use the hosted Service, some of your data is stored on OpenTrace infrastructure. The flows differ depending on configuration:

**Locally-processed materials.** When you process source materials with the OpenTrace open-source tools on your own machine and upload the resulting derived artifacts (knowledge graph, indexes, embeddings) for a given repository, those derived artifacts are stored on OpenTrace infrastructure. The source materials themselves stay on your machine.

**Integration-fetched data (Connected Data).** When you authorize the Service to connect to a third-party system and fetch data into the Service — for example, a code-repository integration that fetches source files, a Slack integration that fetches messages, a project-management integration that fetches tickets and comments, or an observability integration that fetches logs and metrics — the fetched content (Connected Data) is stored on OpenTrace infrastructure for the duration of your use and is accessible through the Service's API and interfaces. The Service produces derived artifacts from Connected Data on OpenTrace infrastructure; both are stored there.

In all hosted configurations:

- derived artifacts may include identifiers such as function names, variable names, file paths, dependency relationships, log patterns, and similar metadata, and OpenTrace treats them as Customer Confidential Information;

- derived artifacts are not intended to contain complete source files or complete underlying documents unless you expressly enable a feature that produces such inclusion. Depending on configuration, derived artifacts may contain identifiers, names, paths, dependency relationships, log patterns, terms, tokens, snippets, embeddings, or other representations derived from the underlying materials, and where the underlying material is itself the input being processed (for example, a Slack message ingested as Connected Data) the content of that material is held as Connected Data on Service infrastructure;

- OpenTrace does not transmit Customer Code, Connected Data, derived artifacts, or query content to any AI provider or other machine learning Subprocessor in standard operation, as further described in Section 4.1; and

- account, billing, telemetry, and operational data described in Section 3 are also processed.

### 2.3 Hybrid use

You may combine these configurations on a per-repository, per-project, or per-integration basis. For repositories or materials processed locally and not connected to the Service, the description in Section 2.1 applies. For repositories or integrations connected to the Service, the description in Section 2.2 applies. Account-level data is processed regardless of which repositories or integrations you connect.

### 2.4 Connecting your own AI provider keys

OpenTrace components that run in your own environment — including the OpenTrace command-line tools and the OpenTrace web interface running in your browser — include functionality that allows you to connect directly to AI providers (for example, to a large language model API) using your own API keys. When you use this configuration:

- the network call to the AI provider is initiated from your machine or browser and does not pass through OpenTrace's server as a proxy;

- the AI provider is not engaged by OpenTrace as a Subprocessor; and

- your relationship with the AI provider is governed by the AI provider's own terms and privacy policy, which you should review.

Responses received from the AI provider may be processed and stored by the Service in the ordinary course — for example, to render a chat response or to maintain saved chat history. Where stored on OpenTrace infrastructure, such content is treated as Customer Data with the same protections as other Customer Data.

Where you configure an API key in our open-source tools or in the OpenTrace web interface running in your browser for direct calls to an AI provider from your environment, the API key is stored only in your local environment (for example, in the open-source tool's local configuration or in your browser local storage) and is not transmitted to or stored on our server. Where you instead choose to provide an API key to the hosted Service for use by Service infrastructure (for example, in a bring-your-own-key configuration of server-side AI functionality), the API key is stored on OpenTrace infrastructure as Customer Data, encrypted at rest, and used only to make calls to the AI provider as you configure.

If OpenTrace introduces functionality in which the Service makes calls to an AI provider on your behalf from Service infrastructure — whether under OpenTrace's own contracts with the AI provider or using API keys you supply — the procedure in Section 4.1 applies (advance notice, description of the data flow, Subprocessor list update where applicable, no-training contractual protections, and opt-in consent).

### 2.5 Telemetry from our web interface

Our web interface uses error monitoring and analytics tools to help us identify and fix problems. Specifically, we use Sentry to capture error reports and crash data, and we collect product usage and feature analytics. Error reports may incidentally include diagnostic context — such as the URL being accessed, the parameters of the failing request, the call stack of the error, and similar information. We have configured these tools to scrub common categories of sensitive content, but we cannot guarantee that no identifier or fragment of context originating from your use of the Service is ever captured in an error report.

We do not intentionally transmit derived-artifact content, query content, or other Customer Data to error monitoring or analytics tools, and we do not use error monitoring data for purposes other than diagnosing, fixing, and improving the Service. (Session replay, which records the user's interaction with the web interface, is described separately in Section 2.6.)

### 2.6 Session replay

Our web interface uses Sentry session replay to diagnose errors, investigate user-reported issues, and improve service reliability. Session replay records interactions with the web interface, such as clicks, navigation, UI events, and limited technical metadata. Because replay captures what is rendered in the interface, it may incidentally include Customer Data visible on screen. We configure replay to mask text and input fields, exclude media elements, and filter sensitive headers and request and response bodies. We do not use session replay for advertising, profiling, or AI model training.

Session replay recordings are retained for no more than 30 days unless needed to investigate a specific support, reliability, or security issue. Session replay cannot be disabled by individual users while using the Service. Enterprise customers may request that session replay be disabled for their organization, and OpenTrace will support this through enterprise configuration or the applicable Order Form.

## 3. Information we collect

We collect information in three ways: information you provide to us directly, information collected automatically when you use the Service, and information we receive from third parties.

### 3.1 Categories of personal data we collect

|                                     |                                                                                                                                                                                                                                                                                                                                                                                                                              |                                                                                                                                |
| ----------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| **Category**                        | **Examples**                                                                                                                                                                                                                                                                                                                                                                                                                 | **Purposes for which we use it**                                                                                               |
| Identity & contact data             | Name, email address, employer, job title, country, password (stored hashed).                                                                                                                                                                                                                                                                                                                                                 | Account creation and administration; communication with you; security; legal compliance.                                       |
| Account & usage data                | Service plan, account settings, repositories connected, features used, frequency and patterns of use, query and output metadata.                                                                                                                                                                                                                                                                                             | Operating the Service; billing where applicable; security; product analytics; service improvement.                             |
| Customer Data stored in the Service | Derived Artifacts you upload from local processing (graph, indexes, embeddings) for each connected repository, and Connected Data the Service fetches from third-party integrations you authorize (which may include source code, configuration, messages, tickets, telemetry, and similar content depending on the integration). Both include identifiers such as function and variable names, paths, and similar metadata. | Operating the Service for you; responding to your queries; security and access control; meeting your contractual instructions. |
| Billing data                        | Billing contact, address, tax identifiers. Payment card data is collected and processed by our payment processor and is not stored by OpenTrace.                                                                                                                                                                                                                                                                             | Processing payments; tax and accounting compliance; collections.                                                               |
| Device & connection data            | IP address, device identifiers, operating system, browser type, language, timestamps, log data.                                                                                                                                                                                                                                                                                                                              | Operating and securing the Service; debugging; analytics.                                                                      |
| Communications data                 | Content of support requests, sales inquiries, survey responses, feedback.                                                                                                                                                                                                                                                                                                                                                    | Responding to you; supporting the relationship; improving the Service.                                                         |
| Integration credentials             | OAuth tokens, installation tokens, webhook secrets, and similar credentials authorizing the Service to access connected third-party systems on your behalf. Stored encrypted at rest.                                                                                                                                                                                                                                        | Operating integrations; authentication and authorization; security and access control.                                         |
| Marketing data                      | Event registrations, content preferences, marketing-list status.                                                                                                                                                                                                                                                                                                                                                             | Sending marketing communications where permitted by law and subject to your right to opt out.                                  |

### 3.2 Information from connected systems and third parties (Connected Data)

When you connect a third-party system to the Service — such as a code-hosting platform, project management tool, communication platform, observability platform, or identity provider — the Service receives information from that system as authorized by you. We refer to this fetched content as Connected Data. Depending on the integration and your configuration, Connected Data may include:

- source code, configuration, and other repository content from code-hosting platforms (where you have authorized the integration to fetch source contents);

- identity, authentication, and authorization information from your identity provider;

- workflow, ticket, document, comment, and message content from connected tools, to the extent you choose to connect them;

- logs, metrics, traces, error reports, and similar telemetry from observability platforms.

Connected Data is stored on OpenTrace infrastructure for the duration of your use, accessible to you through the Service's API and interfaces, and is treated with the same confidentiality, security, and retention commitments as other Customer Data.

### 3.3 Personal data within source materials and Connected Data

Source code repositories and other source materials typically contain personal data — for example, author names and email addresses on commits, code review comments, identifiers in configuration files, references to individuals in documentation, names and identifiers in messages and tickets, and personal information in logs or telemetry. Whether your source materials reach OpenTrace as Connected Data fetched via an integration or only as derived artifacts produced from local processing, the data we hold may contain identifiers that relate to or identify natural persons. We treat all such embedded personal data with the same care as other Customer Data, and we process it only as needed to provide the Service.

## 4. How we use information

We use the information described above to:

- provide, operate, maintain, and secure the Service, including authenticating users, authorizing access, processing requests, and generating Outputs;

- build and operate on the knowledge graph and indexes that the Service is designed to query;

- communicate with you, including service announcements, security notifications, support responses, and administrative messages;

- monitor, troubleshoot, and improve the Service, including identifying and fixing bugs, analyzing performance, and developing new features;

- protect the Service, our customers, and the public, including detecting and preventing fraud, abuse, and security incidents, and enforcing our Terms of Service;

- process payments and manage our commercial relationships, including invoicing, collections, and account management;

- send marketing communications about OpenTrace products and offerings, where permitted by law and subject to your right to opt out at any time; and

- comply with legal obligations, respond to lawful requests from public authorities, and establish, exercise, or defend legal claims.

### 4.1 What we do not do with your data

To make our position completely clear:

- We do not sell your personal data.

- We do not share your personal data for cross-context behavioral advertising.

- We do not use Customer Code, Connected Data, Derived Artifacts, Customer Data, or Outputs to train, fine-tune, or improve the weights of any foundation model or other generally-available machine learning model — neither our own nor any third party's, on free plans or paid plans alike.

- As of the date of this Statement, our server-side infrastructure does not transmit your data to any large language model provider, embedding model provider, or other machine learning service. Today, where the Service involves LLM functionality, the LLM call happens from your environment with an API key you control, and responses saved to OpenTrace infrastructure (for example, as chat history) are treated as Customer Data with the same protections. We plan to introduce functionality in which the Service will make LLM calls on your behalf from Service infrastructure — using either LLM providers we engage directly (as Subprocessors of OpenTrace) or your own API keys used by the Service. Before that applies to your configuration, we will provide advance notice, describe the functionality and data flow, update our Subprocessor list where applicable, require contractual no-training protections, and obtain your opt-in consent.

## 5. Legal bases for processing (EEA, UK, and Switzerland)

If you are located in the European Economic Area, the United Kingdom, or Switzerland, we rely on the following legal bases under Article 6 of the GDPR (and its UK and Swiss equivalents):

|                           |                                                                                                                                                                                                                                                                                                       |
| ------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Legal basis**           | **When we rely on it**                                                                                                                                                                                                                                                                                |
| Performance of a contract | To provide the Service to you or to the customer that authorized your access, including to authenticate users, deliver requested features, and process payments.                                                                                                                                      |
| Legitimate interests      | To secure the Service, prevent fraud and abuse, debug and improve our products, run our business, conduct B2B marketing, and communicate with users about non-core matters. We balance these interests against your rights and interests, and you may object to processing as described in Section 9. |
| Consent                   | Where required by law, for example for certain cookies and electronic marketing. You may withdraw consent at any time.                                                                                                                                                                                |
| Legal obligation          | To comply with applicable laws, including tax, accounting, and lawful requests from public authorities.                                                                                                                                                                                               |

## 6. Sharing and disclosure

We do not sell personal data, and we do not share personal data for cross-context behavioral advertising. We disclose personal data only as described below.

### 6.1 Subprocessors and service providers

We engage third parties to perform services on our behalf. As of the date of this Statement, the categories of Subprocessors we use include:

- cloud hosting and infrastructure;

- graph database services;

- authentication, single sign-on, and session management;

- error monitoring, crash reporting, and session replay (including Sentry, as described in Sections 2.5 and 2.6);

- product analytics;

- feature-flag management;

- observability and monitoring;

- payment processing.

We may engage additional Subprocessors in the future — for example, customer support and ticketing platforms, communication and email delivery providers, or customer relationship management tools. We will update our Subprocessor List at docs.opentrace.com/subprocessor-list/ before any new Subprocessor begins processing Customer Data.

Note: as of the Effective Date of this Statement, we do not use any third-party large language model provider or third-party embedding model provider as a Subprocessor for processing Customer Code, Connected Data, Derived Artifacts, or query content. If that changes, we will update our Subprocessor list and notify customers in advance.

Our current list of named Subprocessors is published at docs.opentrace.com/subprocessor-list/. We require these parties to use personal data only as needed to perform their services for us, in line with appropriate data protection terms.

### 6.2 OpenTrace customers and Authorized Users

When you use the Service as part of an organization that has an account with OpenTrace, certain personal data — such as your name, email address, account activity, and Outputs you have generated — may be visible to your organization's administrators and to other Authorized Users in your organization, in accordance with your organization's configuration of the Service.

### 6.3 Connected third-party systems

When you authorize the Service to connect to a third-party system, the Service exchanges data with that system as required to perform the integration. The processing of personal data within that third-party system is governed by the third party's own privacy notice and your agreements with that third party.

### 6.4 Direct connections to AI providers

When you configure OpenTrace components running in your own environment to connect directly to an AI provider using your own API key, the network call to the AI provider is initiated from your environment and is not proxied through OpenTrace's server. The AI provider's own privacy notice governs the AI provider's processing of that direct call. Where prompts, responses, saved chat history, or related content are saved to or processed by the OpenTrace Service, OpenTrace treats that content as Customer Data under this Statement.

### 6.5 Corporate transactions

If we are involved in a merger, acquisition, financing, restructuring, sale of assets, bankruptcy, or similar transaction, personal data may be transferred to the counterparty as part of that transaction, subject to standard confidentiality and data protection obligations.

### 6.6 Legal and safety disclosures

We may disclose personal data when we believe in good faith that disclosure is necessary to: (a) comply with applicable law or a binding order; (b) enforce our agreements; (c) protect the rights, property, or safety of OpenTrace, our customers, or others; or (d) detect, prevent, or address fraud, security, or technical issues. Where legally permitted, we will provide affected customers with notice before disclosing their data.

## 7. International data transfers

OpenTrace is established in the United States, and our Subprocessors are located in various countries. Personal data we collect may therefore be transferred to, stored in, and processed in countries other than the country in which it was originally collected, including countries that may not be assessed as providing the same level of data protection as your country of residence.

Where we transfer personal data from the European Economic Area, the United Kingdom, or Switzerland to countries that have not been recognized as providing an adequate level of protection, we rely on appropriate safeguards as required by applicable law, including the European Commission's Standard Contractual Clauses, the UK International Data Transfer Agreement or Addendum, and equivalent Swiss mechanisms. Where we rely on these mechanisms with our Subprocessors, we will, on request, provide you with information about the safeguards in place.

## 8. How long we keep information

We keep personal data for as long as needed for the purposes described in this Statement, unless a longer retention period is required or permitted by law. Specifically:

- account information is retained for as long as the account is active, and for a reasonable period thereafter to allow account recovery, dispute resolution, and legal compliance;

- Derived Artifacts, Connected Data, and other Customer Data stored in the Service are retained as set out in our Terms of Service and your account configuration; on termination or repository deletion, we provide a thirty-day export window, then delete from production systems within sixty days, after which the data is overwritten in routine backups within ninety days;

- session replay recordings are retained for no more than 30 days unless needed to investigate a specific support, reliability, or security issue;

- error monitoring data and application diagnostic logs are retained for no more than 90 days, except for security or compliance-related entries which may be retained for up to one year;

- product usage and web analytics data are retained for up to 14 months;

- billing records are retained as required by tax and accounting laws;

- marketing data is retained until you opt out, and for a short period thereafter to suppress further communications.

When personal data is no longer needed, we delete it or anonymize it so that it can no longer be associated with you.

## 9. Your rights

### 9.1 Rights under the GDPR (EEA, UK, Switzerland)

If you are located in the European Economic Area, the United Kingdom, or Switzerland, subject to applicable law, you have the right to:

- access the personal data we hold about you and receive a copy of it;

- request correction of inaccurate or incomplete personal data;

- request deletion of your personal data, subject to applicable exceptions;

- request restriction of processing in certain circumstances;

- object to processing based on our legitimate interests;

- request portability of personal data you provided to us, in a structured, commonly used, and machine-readable format;

- withdraw consent at any time where processing is based on consent, without affecting the lawfulness of prior processing; and

- lodge a complaint with a supervisory authority in the country where you live, work, or believe a violation has occurred.

### 9.2 Rights under U.S. state privacy laws

If you are a resident of a U.S. state with a comprehensive privacy law — including California, Colorado, Connecticut, Delaware, Indiana, Iowa, Kentucky, Maryland, Minnesota, Montana, Nebraska, New Hampshire, New Jersey, Oregon, Rhode Island, Tennessee, Texas, Utah, or Virginia — you have the rights described below. Specific rights vary by state; the rights below are presented in their cumulative form, and any limits applicable in your state will be applied automatically when you exercise them.

#### 9.2.1 Common rights across covered states

- Right to know / access: confirm whether we are processing your personal data, and access the data and supporting information.

- Right to a copy / portability: receive a copy of your personal data in a portable, machine-readable format where technically feasible.

- Right to delete: request deletion of personal data we have collected from you or about you, subject to applicable exceptions.

- Right to correct: request correction of inaccuracies in your personal data, subject to certain conditions.

- Right to opt out of sale or sharing: we do not sell your personal data and do not share it for cross-context behavioral advertising. You retain the right to direct us not to do so in the future.

- Right to opt out of targeted advertising: we do not engage in targeted advertising as defined in the state laws.

- Right to opt out of profiling: we do not engage in profiling that produces legal or similarly significant effects on you.

- Right to non-discrimination: we will not discriminate against you for exercising your rights.

#### 9.2.2 Additional California rights

Under California Civil Code §§ 1798.83-1798.84 ("Shine the Light"), California residents may request information about disclosures of personal data to third parties for those third parties' direct marketing purposes. To make such a request, contact us at privacy@opentrace.com.

We do not knowingly sell or share for cross-context behavioral advertising the personal data of consumers under 16 years of age.

We do not collect or use sensitive personal information for purposes that would require an opt-out under California Civil Code § 1798.121.

#### 9.2.3 Right to appeal a denied request

In a number of states, including Colorado, Connecticut, Delaware, Indiana, Kentucky, Maryland, Minnesota, Montana, Nebraska, New Hampshire, New Jersey, Oregon, Rhode Island, Tennessee, Texas, and Virginia, if we deny your request, you may appeal our decision. To appeal, send a written appeal to privacy@opentrace.com identifying yourself, the original request, and the basis for your appeal. We will respond to your appeal within the time period required under applicable law. If we deny your appeal, you may contact your state’s Attorney General. California, Iowa, and Utah do not provide a parallel statutory right to appeal a denied request and so are not listed above; if you are a resident of one of those states, you may still contact us about a denied request and we will respond on the same basis.

#### 9.2.4 Authorized agents

Where permitted by your state's law, you may authorize an agent to exercise your rights on your behalf. To do this, you must provide your agent with written permission to exercise your rights, and we may request a copy of that permission and verify your identity directly before completing the request.

### 9.3 How to exercise your rights

To exercise any of these rights, contact us at privacy@opentrace.com. Where you use the Service through an OpenTrace customer that is acting as a controller, we may direct your request to that customer, who is responsible for responding under its own privacy notice. We will respond to verifiable requests within the time required by applicable law. We may need to verify your identity before processing a request, and we will not respond to requests that are excessive, repetitive, or manifestly unfounded without explanation.

## 10. Cookies and similar technologies

We and our service providers use cookies, local storage, pixels, and similar technologies on our website and in the Service. These technologies allow us to recognize your device, remember your preferences, secure the Service, and understand how it is used. Where required by law, we obtain your consent before placing non-essential cookies; you can manage your preferences through our cookie banner or through your browser settings.

We use the following categories of cookies and similar technologies:

- **Essential.** Required to provide features you request, including authentication and session management, security features such as cross-site request forgery protection, and recording your cookie consent choice. Disabling these will prevent core functionality from working.

- **Functional.** Record your settings and preferences (for example, your interface choices and feature-flag context) so that the Service recognizes you on return visits.

- **Performance / Analytical.** Help us understand aggregate usage of our website and the Service so that we can improve them. For example, Google Analytics uses cookies to measure visitor traffic and interactions on opentrace.com; you can opt out of Google Analytics specifically through the browser add-on at https://tools.google.com/dlpage/gaoptout.

You can also manage cookies through your browser settings, including blocking new cookies or deleting existing ones. Doing so may require you to re-enter preferences on each visit and may prevent some features from working. To learn more about cookies generally, you can visit https://www.allaboutcookies.org.

### 10.1 "Do Not Track" and Global Privacy Control

There is no industry-standard interpretation of "Do Not Track" browser signals, so our Service does not currently respond to them. Where the Global Privacy Control signal is legally recognized as an opt-out — for example, under California law — we treat it as an opt-out of any sale or sharing of personal information.

## 11. Security

We implement administrative, technical, and physical safeguards designed to protect personal data against unauthorized access, use, disclosure, alteration, and destruction. These safeguards include encryption in transit and at rest, role-based access controls, network and endpoint security, logging and monitoring, secure development practices, and routine testing.

No system can be guaranteed to be entirely secure. If we become aware of a security incident affecting your personal data, we will notify you and any affected customer in accordance with applicable law and our contractual obligations.

## 12. Children

The Service is not directed to children under the age of 13, and we do not knowingly collect personal data from children. If you believe a child has provided personal data to us, contact us at privacy@opentrace.com and we will take appropriate steps to delete it.

## 13. Changes to this Statement

We may update this Privacy Statement from time to time. When we make material changes, we will provide notice through the Service or by email, and we will update the "Last updated" date at the top of this Statement. We encourage you to review this Statement periodically.

## 14. Contact us

If you have questions, comments, or requests regarding this Privacy Statement or our processing of personal data, please contact us at:

OpenTrace, Inc.

14205 N Mo Pac Expy, Ste 570, PMB 640435, Austin, Texas 78728-6529, USA

Email: privacy@opentrace.com

_— End of Privacy Statement —_
