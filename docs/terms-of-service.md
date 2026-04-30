# OpenTrace Terms of Service

Last updated: April 30, 2026 · Effective date: April 30, 2026

These Terms of Service ("Terms") govern your access to and use of the OpenTrace hosted code intelligence service, the OpenTrace website, the application programming interfaces, and the related services (together, the "Service") made available by OpenTrace, Inc., a Delaware corporation ("OpenTrace," "we," "us," or "our").

By clicking to accept these Terms, by signing an Order Form that incorporates these Terms by reference, or by accessing or using any part of the Service, you agree to be bound by these Terms. If you are entering into these Terms on behalf of a company or other legal entity, you represent that you have the authority to bind that entity, in which case "you," "your," and "Customer" refer to that entity. If you do not have such authority, or if you do not agree with these Terms, you must not accept these Terms and you may not use the Service.

OpenTrace also publishes open-source software, including the OpenTrace command-line tools, available at github.com/opentrace. Your use of those open-source components, when used purely locally and without connecting to the hosted Service, is governed exclusively by the open-source license that applies to the relevant repository, not by these Terms. These Terms govern your use of the hosted Service and any other functionality OpenTrace provides through opentrace.com, app.opentrace.ai, or other OpenTrace properties.

## 1. Definitions

In these Terms, capitalized terms have the meanings set out below. Other capitalized terms are defined in the body of these Terms.

**"Affiliate"** means, with respect to a party, any entity that directly or indirectly controls, is controlled by, or is under common control with such party, where "control" means ownership of more than 50% of the voting interests of an entity.

**"Agreement"** means these Terms together with any Order Form, Data Processing Addendum, Service Level Agreement, and other documents incorporated by reference.

**"Authorized User"** means an employee, contractor, agent, or AI agent operated on behalf of Customer or its Affiliates that has been authorized by Customer to access the Service under Customer's account.

**"Connected Data"** means data the Service fetches from third-party systems and integrations Customer has authorized, including code repository platforms, project management tools, communication platforms, observability platforms, and similar systems. Connected Data may include source code (where Customer has authorized a code-repository integration to fetch source contents — in which case it is also Customer Code), configuration, messages, tickets, telemetry, error reports, and other content depending on the integration. Connected Data is stored on Service infrastructure for the duration of Customer's use and is accessible to Customer through the Service's interfaces and APIs.

**"Customer Code"** means source code, configuration files, build artifacts, dependency manifests, and related software materials that belong to or are controlled by Customer or its Authorized Users. Customer Code processed locally by the OpenTrace Open-Source Components on Customer's infrastructure is not transmitted to or stored by the Service. Customer Code that Customer has authorized to be fetched into the Service via a third-party integration is stored on Service infrastructure as Connected Data, subject to the protections that apply to Customer Data generally.

**"Customer Data"** means all data and content submitted to, fetched into, or generated within the Service by or on behalf of Customer, including Connected Data, Derived Artifacts, account information, queries, prompts, and Outputs. Customer Data does not include Customer Code that remains on Customer's own infrastructure and is not transmitted to the Service.

**"Derived Artifacts"** means the structural and metadata representations that the OpenTrace Open-Source Components or the Service produce by processing Customer Code, Connected Data, or other source materials Customer submits or authorizes the Service to fetch, whether processed on Customer's own infrastructure or on Service infrastructure. Derived Artifacts include knowledge graphs, full-text search indexes, semantic indexes, embeddings, and similar artifacts, and may include identifiers, names, paths, dependency relationships, log patterns, terms, tokens, snippets, embeddings, and other representations or metadata derived from the underlying materials. Derived Artifacts are not intended to contain complete source files or complete underlying documents unless Customer expressly enables a feature that produces such inclusion.

**"Documentation"** means the user guides, API references, and other technical materials made available by OpenTrace describing the operation and use of the Service.

**"OpenTrace Open-Source Components"** means the OpenTrace command-line tools and any other software that OpenTrace publishes under an open-source license. Use of OpenTrace Open-Source Components, when used purely locally and without connecting to the Service, is governed exclusively by the applicable open-source license.

**"Order Form"** means an ordering document signed or otherwise accepted by both parties that references these Terms and specifies the Service plan, fees, term, and other commercial terms.

**"Output"** means analyses, summaries, code-intelligence responses, and other materials generated by the Service in response to queries against Customer's Derived Artifacts, Connected Data, or other Customer Data.

**"Personal Data"** has the meaning given in applicable Data Protection Laws, and includes information that identifies or is reasonably capable of identifying a natural person.

**"Service Plan"** means the tier, package, or edition of the Service that Customer has subscribed to or signed up for, as set out in the applicable Order Form or self-service signup, including free plans.

**"Subprocessor"** means a third party engaged by OpenTrace to process Customer Data as part of providing the Service.

**"Third-Party Service"** means any product, service, or system not provided by OpenTrace that Customer chooses to connect to the Service or to use alongside OpenTrace Open-Source Components, including code-hosting platforms, identity providers, communication tools, and large language model providers accessed via Customer-supplied API keys.

## 2. The Service

### 2.1 What the Service does

The Service hosts and operates on Customer's Derived Artifacts, Connected Data, and other Customer Data to provide code intelligence and related capabilities, including the ability to query the knowledge graph and indexes, retrieve structural information about Customer's codebase and connected systems, generate Outputs in response to programmatic and human queries, and integrate with Customer's broader development and operational workflow. The Service is intended to be consumed both by humans and by automated systems acting on Customer's behalf.

### 2.2 Local, hosted, and hybrid use

The Service supports the following deployment configurations:

- **Local use**: Customer uses OpenTrace Open-Source Components entirely on Customer's own infrastructure, without connecting to the Service. In this configuration, the Open-Source Components ingest Customer Code and other source materials locally, build Derived Artifacts locally, and store Derived Artifacts locally. No Customer Code, source materials, or Derived Artifacts are transmitted to OpenTrace.

- **Hosted use with locally-processed materials**: Customer uses the OpenTrace Open-Source Components on Customer's own infrastructure to process source materials and uploads the resulting Derived Artifacts to the Service. In this configuration, Customer Code and other source materials processed locally remain on Customer's infrastructure; only the Derived Artifacts produced from them are stored on Service infrastructure.

- **Hosted use with integration-fetched data**: Customer authorizes the Service to connect to third-party systems (such as code repository platforms, project management tools, communication platforms, or observability platforms) and fetch data from those systems into the Service. Fetched content — which may include source code (from code-repository integrations Customer has authorized), configuration, messages, tickets, telemetry, error reports, and other content depending on the integration — is stored on Service infrastructure as Connected Data. The Service may produce Derived Artifacts from Connected Data on Service infrastructure; both Connected Data and the Derived Artifacts produced from it are stored on Service infrastructure for the duration of Customer's use.

- **Hybrid use**: Customer may combine these configurations on a per-repository, per-project, or per-integration basis. The Service supports configuration to indicate the path each input takes.

### 2.3 OpenTrace Open-Source Components

OpenTrace publishes the OpenTrace command-line tools and certain other components as open-source software, available at github.com/opentrace. Use of those components, when used purely locally and without connecting to the Service, is governed exclusively by the open-source license that applies to the relevant repository, and not by these Terms. These Terms apply to the Service and to any use of OpenTrace Open-Source Components that connects to or otherwise interacts with the Service.

### 2.4 Customer-supplied keys for Third-Party Services

OpenTrace components that run in Customer's own environment — including the OpenTrace command-line tools and the OpenTrace web interface running in Customer's browser — may include functionality that allows Customer or its Authorized Users to configure direct connections to Third-Party Services using Customer-supplied API keys, including connections to large language model providers. Where Customer uses such a configuration:

- the network call to the Third-Party Service is initiated from Customer's environment (the local component or the browser) and does not pass through OpenTrace's server as a proxy;

- the Third-Party Service is not engaged by OpenTrace as a Subprocessor;

- Customer's relationship with the Third-Party Service is governed by Customer's agreement with that provider; and

- Customer is responsible for ensuring that its use of the Third-Party Service complies with the provider's terms.

Responses received from the Third-Party Service may be processed and stored by the Service in the ordinary course — for example, to render a chat response, to associate it with Customer's session or saved chat history, or to integrate it into the Service's interfaces. Where stored on Service infrastructure, such content is treated as Customer Data and is governed by the same confidentiality, security, retention, and no-training commitments as other Customer Data.

Where Customer configures an API key in OpenTrace's open-source components or in the OpenTrace web interface running in Customer's browser for direct calls to a Third-Party Service from Customer's environment, that API key is stored only in Customer's local environment (for example, in the open-source component's local configuration or in Customer's browser local storage) and is not transmitted to or stored on OpenTrace's server. Where Customer instead chooses to provide an API key to the hosted Service for use by Service infrastructure (for example, in a bring-your-own-key configuration of server-side functionality), the API key is stored on Service infrastructure as Customer Data, encrypted at rest, and used only to make calls to the Third-Party Service as configured by Customer.

If OpenTrace introduces functionality that would have the Service make calls to a Third-Party Service from Service infrastructure on Customer's behalf — whether under OpenTrace's own contracts with that Third-Party Service or using Customer-supplied API keys — the procedure in Section 4.6 applies.

### 2.5 Programmatic and AI-agent access

The Service is designed to be consumed by software systems acting on Customer's behalf, including AI coding agents, build systems, internal automation, and developer tooling. Customer is expressly permitted to access the Service programmatically through OpenTrace's APIs and integration points, and to operate AI agents and automated systems that consume Outputs, in each case subject to the Documentation, applicable rate limits, and these Terms. No additional consent or authorization beyond Customer's acceptance of these Terms is required for such use.

### 2.6 Updates and changes to the Service

OpenTrace continuously develops the Service and may add, modify, deprecate, or remove features at its discretion. OpenTrace will use reasonable efforts to provide advance notice of material adverse changes affecting paid Service Plans. OpenTrace may release the Service or specific features as alpha, beta, preview, or experimental, in which case those features are provided "as is" and may be changed or withdrawn without notice.

### 2.7 Documentation

OpenTrace makes Documentation available describing the Service. Customer's use of the Service must materially conform to the Documentation. To the extent of any conflict, these Terms prevail over the Documentation.

### 2.8 Maintenance and downtime

OpenTrace may perform scheduled maintenance on reasonable advance notice through the Service or by email, perform emergency maintenance without prior notice where reasonably required to address security, integrity, or operational issues, and temporarily suspend access to all or part of the Service where necessary for technical, security, or legal reasons. OpenTrace will use commercially reasonable efforts to minimise the duration and impact of any such interruption.

## 3. Accounts and Authorized Users

### 3.1 Registration

To use the Service, Customer must register an account and provide accurate, current, and complete information. Customer is responsible for maintaining the confidentiality of account credentials and for all activity that occurs under its account.

### 3.2 Authorized Users

Customer may permit its Authorized Users — including AI agents acting on Customer's behalf — to access the Service. Customer is responsible for the acts and omissions of its Authorized Users as if they were Customer's own. Customer must promptly disable access for any Authorized User who is no longer entitled to use the Service.

### 3.3 Security of credentials

Customer must use commercially reasonable measures to safeguard authentication credentials, API keys, and tokens. Customer must notify OpenTrace promptly of any suspected unauthorized access to or compromise of its account.

## 4. Customer Code, Derived Artifacts, and Outputs

### 4.1 Customer ownership

As between the parties, Customer retains all right, title, and interest in and to Customer Code, Derived Artifacts, and Customer Data, including all intellectual property rights therein. OpenTrace acquires no ownership interest in Customer Code, Derived Artifacts, or Customer Data under these Terms.

### 4.2 Where data lives

Where Customer processes source materials locally with the OpenTrace Open-Source Components, those source materials — including Customer Code — remain on Customer's infrastructure. Locally-processed source materials are not transmitted to or stored by the Service. The Service stores and operates on the Derived Artifacts that Customer chooses to upload from local processing.

Where Customer authorizes the Service to fetch data from third-party integrations, the fetched content is stored on Service infrastructure as Connected Data for the duration of Customer's use. Connected Data may include source code (where Customer has authorized a code-repository integration to fetch source contents), configuration, messages, tickets, telemetry, and similar content depending on the integration. Connected Data and any Derived Artifacts produced from it are governed by the same confidentiality, security, retention, no-training, no-sale, and no-LLM-Subprocessor commitments as other Customer Data.

Connected Data and Derived Artifacts may include identifiers, structural information, and metadata that reveal substantial information about Customer's codebase, infrastructure, and operations. OpenTrace treats Connected Data and Derived Artifacts stored on Service infrastructure with the same confidentiality, security, and retention commitments as other Customer Data.

### 4.3 License to OpenTrace

Customer grants OpenTrace a worldwide, non-exclusive, royalty-free license, during the Term and for a limited period thereafter as reasonably required for wind-down, to host, copy, transmit, process, analyze, index, and display Derived Artifacts, Connected Data, and other Customer Data submitted to, fetched into, generated within, or otherwise processed by the Service, solely as necessary to: (a) provide, secure, maintain, and improve the Service for Customer; (b) prevent or address technical or security issues; (c) enforce these Terms; and (d) comply with applicable law.

For the avoidance of doubt, "improve the Service" as used in this Section 4.3 does not include training, fine-tuning, or improving the weights of any machine learning model (which is governed by Section 4.6), and does not include any use of customer-specific Derived Artifacts, Customer Code, or Customer Data except as expressly permitted in Section 4.5.

### 4.4 Outputs

Subject to Customer's payment of fees and ongoing compliance with these Terms, OpenTrace assigns to Customer all of OpenTrace's right, title, and interest, if any, in Outputs that are specific to Customer's Derived Artifacts, Connected Data, or other Customer Data, and grants Customer a perpetual, irrevocable, worldwide license to use such Outputs for any lawful purpose.

Customer acknowledges that, due to the nature of code intelligence and machine learning, Outputs may not be unique. Other customers may receive similar Outputs from independent inputs. OpenTrace and its other customers retain rights in such independent outputs, and OpenTrace's assignment under this Section does not extend to outputs generated for other customers from independent inputs.

### 4.5 Service improvement and aggregated data

OpenTrace may collect and use technical, performance, and usage data about the Service, and may create aggregated and de-identified data, in each case in a form that does not identify Customer, Customer's Authorized Users, or any individual, and does not contain Customer's identifiers, structural information about Customer's codebase or operations, or any material that could reasonably be used to reconstruct Customer's code, Connected Data, or Derived Artifacts. OpenTrace may use such aggregated and de-identified data to operate, analyze, secure, and improve the Service and OpenTrace's business.

Queries, prompts, and Outputs may also be temporarily processed and logged by OpenTrace solely to operate, support, debug, and secure the Service. Such processing is subject to access controls, retention proportionate to those purposes, and scrubbing of sensitive fields where supported. It is not used to train AI models (see Section 4.6) and is not shared with third parties except with Subprocessors performing these functions on OpenTrace's behalf.

### 4.6 No training of AI models on Customer Code, Connected Data, or Derived Artifacts

OpenTrace will not use Customer Code, Connected Data, Derived Artifacts, Customer Data, or Outputs to train, fine-tune, or otherwise improve the weights of any foundation model or other generally-available machine learning model, whether owned by OpenTrace or by a third party. This restriction applies across all Service Plans, including free plans, and is not contingent on Customer's payment of fees.

As of the Effective Date of these Terms, OpenTrace does not engage any large language model provider, embedding model provider, or other machine learning service as a Subprocessor, and OpenTrace's server-side infrastructure does not transmit Customer Code, Connected Data, Derived Artifacts, or other Customer Data to any such service. Where the Service involves LLM functionality today, the LLM call is initiated by Customer through OpenTrace components running in Customer's environment, using API keys Customer has configured; the response, where stored on Service infrastructure (for example, as part of saved chat history), is treated as Customer Data and is subject to the protections in this Section 4.

OpenTrace anticipates introducing functionality in which the Service will make LLM calls on Customer's behalf from Service infrastructure. Such functionality may use either (i) LLM providers that OpenTrace engages under its own contracts (in which case the LLM provider would be engaged as a Subprocessor of OpenTrace) or (ii) Customer-supplied API keys that the Service uses to call an LLM provider on Customer's behalf. In either case, before any such functionality applies to Customer's configuration, OpenTrace will: (a) provide advance notice through the Service or by email; (b) describe the functionality, the categories of data that would be transmitted, and the LLM provider involved; (c) where applicable, update the Subprocessor list and require by contract that the LLM provider not use Customer's data for its own model training purposes; and (d) obtain Customer's prior opt-in consent before such functionality is enabled for Customer.

### 4.7 Customer responsibility for inputs

Customer represents and warrants that: (a) it has all rights, licenses, and permissions necessary to provide Customer Code, to authorize the Service to fetch Connected Data from third-party integrations, to upload Derived Artifacts and other Customer Data, and to grant the licenses set out in this Section 4; (b) the provision, fetching, and processing of Customer Code, Connected Data, Derived Artifacts, and Customer Data through the Service does not and will not violate any applicable law, regulation, or third-party right; (c) Customer Code, Connected Data, Derived Artifacts, and Customer Data do not contain any item that Customer is not authorized to share with a cloud service provider, including under any agreement with a third party; and (d) Customer has implemented reasonable filtering, redaction, and access controls to avoid submitting (or authorizing the Service to fetch) secrets, credentials, cryptographic keys, access tokens, or sensitive personal data not strictly necessary for the function Customer is performing.

## 5. Acceptable Use

Customer must not, and must not permit any Authorized User or other third party to:

- use the Service in violation of any applicable law, regulation, or third-party right;

- submit to the Service any content that is unlawful, infringing, defamatory, obscene, or that contains malware, viruses, or other harmful code, except for samples submitted in good faith for legitimate security research within a Service Plan that expressly permits such use;

- attempt to gain unauthorized access to the Service, other customers' accounts or data, or any underlying systems or networks;

- reverse engineer, decompile, or disassemble the Service, or attempt to derive its source code, except (i) to the extent applicable law expressly permits despite this limitation, or (ii) for OpenTrace Open-Source Components, in accordance with their open-source license;

- use the Service or any Output to train, fine-tune, or otherwise develop any artificial intelligence model, code intelligence platform, or similar service that competes with the Service;

- use the Service to build a competing product or service, or to benchmark the Service for the purpose of publishing comparisons, without OpenTrace's prior written consent;

- circumvent or disable any usage limits, rate limits, security features, or access controls of the Service;

- remove, obscure, or alter any proprietary notices contained in the Service, the Documentation, or Outputs;

- submit Personal Data of categories prohibited by applicable law for the Service's data classification, or sensitive data such as government-issued identifiers, payment card data, or protected health information, unless the parties have agreed in writing that the Service is configured for such data;

- submit to the Service or authorize the Service to fetch any secrets, credentials, cryptographic keys, access tokens, or other authentication material, except as expressly required for an integration or feature documented to receive such material;

- use the Service to make decisions that produce legal or similarly significant effects on individuals without meaningful human review.

OpenTrace may, but is not obligated to, monitor use of the Service for compliance with these Terms and may investigate suspected violations.

## 6. Third-Party Services and Integrations

### 6.1 Customer-enabled integrations

The Service supports integrations with Third-Party Services, including code-hosting platforms, identity providers, issue trackers, communication tools, observability platforms, and AI agents and tools. By enabling an integration, Customer authorizes OpenTrace to access, fetch, transmit, and process data through that integration on Customer's behalf in accordance with the integration's configuration. Data fetched into the Service through such integrations is treated as Connected Data (as defined in Section 1) and is governed by the same confidentiality, security, retention, no-training, no-sale, and no-LLM-Subprocessor commitments as other Customer Data. Deleting or modifying data in a connected Third-Party Service may not automatically delete or modify the corresponding Connected Data already stored on Service infrastructure, unless the integration or Customer's configuration supports that behavior. Customer may delete integration-fetched datasets through the Service as described in Section 8.6.

### 6.2 Customer-supplied keys for AI providers

OpenTrace components running in Customer's own environment may permit Customer to configure direct connections to AI providers using Customer-supplied API keys, as further described in Section 2.4. The AI provider is not engaged by OpenTrace as a Subprocessor, and Customer's relationship with the AI provider is governed by Customer's agreement with that provider. Responses received by the Service from the AI provider are treated as Customer Data when stored on Service infrastructure, as described in Section 2.4. OpenTrace is not responsible for the AI provider's availability, security, or terms of use.

### 6.3 Customer responsibility for Third-Party Services

Customer's use of any Third-Party Service is governed by Customer's agreement with that third party. OpenTrace is not responsible for Third-Party Services and makes no warranty regarding their availability, security, or performance. If a Third-Party Service ceases to be available or changes its interface, OpenTrace may suspend or modify the corresponding integration.

## 7. Service Plans, Fees, and Payment

### 7.1 Free Service Plans

OpenTrace offers free Service Plans. Free plans may have feature, capacity, support, and availability limitations, which OpenTrace may modify at its discretion on reasonable notice. Free plans do not carry the warranties or service-level commitments applicable to paid Service Plans, and OpenTrace may discontinue free plans on reasonable notice. The commitments set out in Section 4.6 (No training of AI models) apply equally to free plans.

### 7.2 Paid Service Plans

Paid Service Plans are subject to fees specified in the applicable Order Form or self-service signup. Except as expressly stated in these Terms or required by applicable law, all fees are non-refundable and all payment obligations are non-cancellable.

### 7.3 Invoicing and payment terms

Unless otherwise stated, fees for Paid Service Plans paid by invoice are due within thirty (30) days of the invoice date. Fees for self-service Paid Service Plans are charged in advance to the payment method on file. Late amounts accrue interest at the lower of 1.5% per month or the maximum rate permitted by law.

### 7.4 Auto-renewal

**AUTO-RENEWAL NOTICE.** Paid Service Plans with a term of one month or longer renew automatically for successive periods of equal length unless either party gives written notice of non-renewal at least thirty (30) days before the end of the then-current term, or as otherwise specified in the Order Form. By subscribing to a recurring Paid Service Plan, Customer authorizes OpenTrace, directly or through its payment processor, to charge Customer's payment method on file for each renewal period until Customer cancels. Customer may cancel a self-service subscription at any time through the account settings page; cancellation takes effect at the end of the then-current term.

### 7.5 Taxes

Fees are exclusive of all taxes, levies, and duties (including value-added tax, sales tax, and goods and services tax) other than taxes based on OpenTrace's net income. Customer is responsible for paying all such taxes.

### 7.6 Suspension for non-payment

OpenTrace may suspend access to a Paid Service Plan if any undisputed amount is more than thirty (30) days overdue, after providing at least seven (7) days' prior written notice.

## 8. Term, Termination, and Suspension

### 8.1 Term

These Terms commence on the Effective Date and continue until terminated. Each Order Form has its own subscription term as specified therein. Self-service Service Plans continue until cancelled by Customer or terminated by OpenTrace in accordance with these Terms.

### 8.2 Termination for cause

Either party may terminate the Agreement for cause: (a) on thirty (30) days' written notice of a material breach by the other party that remains uncured at the end of that period; or (b) immediately if the other party becomes the subject of a petition in bankruptcy or any other proceeding relating to insolvency, receivership, or liquidation.

### 8.3 Termination for convenience

Customer may terminate any free Service Plan at any time. Customer may terminate a Paid Service Plan in accordance with the cancellation procedures applicable to that plan. OpenTrace may terminate a free Service Plan at any time on reasonable notice.

### 8.4 Suspension

OpenTrace may suspend Customer's access to all or part of the Service immediately if (a) OpenTrace reasonably believes that continued access poses a security or legal risk to OpenTrace, the Service, or any third party; (b) Customer's use violates Section 5 (Acceptable Use); or (c) suspension is required to comply with applicable law or a binding order. OpenTrace will notify Customer as soon as reasonably practicable.

### 8.5 Effect of termination

On expiration or termination of the Agreement: (a) Customer's right to access and use the Service ceases; (b) each party returns or destroys the other party's Confidential Information in its possession, except to the extent retention is required by law or by routine backup procedures; and (c) Customer remains liable for any fees accrued before termination.

### 8.6 Data export and deletion

For a period of thirty (30) days after termination, OpenTrace will make Derived Artifacts, Connected Data, and other Customer Data available for export through the Service's standard export tools. After that period, OpenTrace will delete Derived Artifacts, Connected Data, and other Customer Data from production systems within sixty (60) days, subject to retention in routine backups for up to ninety (90) days thereafter, after which they will be overwritten in the ordinary course. Customer may also delete specific repositories, projects, or integration-fetched datasets at any time through the Service, in which case the same sixty- and ninety-day windows apply to that data.

## 9. Confidentiality

### 9.1 Definition

"Confidential Information" means any non-public information disclosed by one party (the "Discloser") to the other (the "Recipient") that is identified as confidential or that, given the nature of the information and the circumstances of disclosure, a reasonable person would understand to be confidential. Customer Code, Connected Data, Derived Artifacts, and other Customer Data are Customer's Confidential Information. The Service, the Documentation, and OpenTrace's non-public technical and business information are OpenTrace's Confidential Information.

### 9.2 Obligations

The Recipient must: (a) use the Discloser's Confidential Information solely to perform the Recipient's obligations or exercise its rights under these Terms; (b) protect such Confidential Information using at least the same degree of care it uses for its own confidential information of similar nature, and in no event less than a reasonable degree of care; and (c) not disclose such Confidential Information to any third party except to its employees, contractors, and advisors who have a need to know and are bound by confidentiality obligations no less protective than those in these Terms.

### 9.3 Exclusions

Confidential Information does not include information that: (a) is or becomes publicly available without breach of these Terms by the Recipient; (b) was known to the Recipient before receipt from the Discloser; (c) is rightfully obtained by the Recipient from a third party without restriction; or (d) is independently developed by the Recipient without use of or reference to the Discloser's Confidential Information.

### 9.4 Compelled disclosure

The Recipient may disclose Confidential Information if compelled by law or legal process, provided that, to the extent legally permitted, the Recipient gives the Discloser prior notice and reasonable assistance to seek a protective order or other relief.

## 10. Intellectual Property

### 10.1 OpenTrace IP

OpenTrace and its licensors retain all right, title, and interest in and to the Service, the Documentation, and all related intellectual property, including all improvements, modifications, and derivative works. Except for the limited rights expressly granted in these Terms or in the applicable open-source license for OpenTrace Open-Source Components, no rights are granted to Customer.

### 10.2 Feedback

If Customer or any Authorized User provides suggestions, ideas, or other feedback regarding the Service ("Feedback"), Customer grants OpenTrace a perpetual, irrevocable, worldwide, royalty-free license to use, exploit, and incorporate such Feedback into the Service and other OpenTrace products, without obligation or compensation to Customer.

### 10.3 Trademarks

Neither party may use the other party's trademarks, service marks, or logos without prior written consent, except that OpenTrace may identify Customer as a customer in customer lists and case studies with Customer's reasonable consent, not to be unreasonably withheld.

## 11. Warranties and Disclaimers

### 11.1 Mutual warranties

Each party represents and warrants that it has the legal authority to enter into and perform the Agreement, and that its performance does not violate any other agreement to which it is a party.

### 11.2 OpenTrace warranties

For Paid Service Plans, OpenTrace warrants that, during the subscription term, the Service will perform materially in accordance with the Documentation. As Customer's exclusive remedy and OpenTrace's entire liability for breach of this warranty, OpenTrace will use commercially reasonable efforts to correct the non-conformity, and if it cannot do so within a reasonable period, Customer may terminate the affected Order Form and OpenTrace will refund any prepaid fees for the unused portion of the term.

### 11.3 AI-generated outputs

Customer acknowledges that the Service applies algorithmic and, where Customer enables them, machine learning techniques to generate Outputs, and that such Outputs may be incomplete, incorrect, or otherwise unsuitable for a particular purpose. Customer is responsible for evaluating Outputs before relying on them for any consequential decision, and for any actions taken by automated systems, including AI agents, based on the Service's responses.

To the extent the Service itself uses AI or other autonomous components to take actions — for example, to propose changes, perform tasks, or invoke other systems on Customer's behalf within the Service — those components may also make mistakes, including by drawing incorrect inferences, taking unintended actions, or producing results Customer did not anticipate. Customer is responsible for configuring appropriate authorization scopes and review checkpoints before allowing the Service to affect Customer's source code, infrastructure, or third-party systems.

Where AI agents acting on Customer's behalf take actions that modify Customer's source code, infrastructure, or third-party systems based on Outputs — for example, editing or deleting code, executing commits, deploying changes, or invoking other systems — Customer is responsible for implementing appropriate human-review checkpoints, authorization controls, and rollback procedures, and bears the risk of those actions.

### 11.4 Disclaimer

**EXCEPT AS EXPRESSLY SET OUT IN THIS SECTION 11, THE SERVICE AND ALL OUTPUTS ARE PROVIDED "AS IS" AND "AS AVAILABLE." OPENTRACE DISCLAIMS ALL OTHER WARRANTIES, EXPRESS, IMPLIED, OR STATUTORY, INCLUDING IMPLIED WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE, NON-INFRINGEMENT, AND ANY WARRANTIES ARISING FROM COURSE OF DEALING OR USAGE OF TRADE. OPENTRACE DOES NOT WARRANT THAT THE SERVICE WILL BE UNINTERRUPTED, ERROR-FREE, OR SECURE, OR THAT OUTPUTS WILL MEET CUSTOMER'S REQUIREMENTS. FREE SERVICE PLANS ARE PROVIDED WITHOUT ANY WARRANTY OF ANY KIND.**

### 11.5 Critical systems warning

**THE SERVICE IS A DIAGNOSTIC, ANALYSIS, AND CODE-INTELLIGENCE TOOL AND IS NOT DESIGNED OR CERTIFIED FOR USE AS THE SOLE BASIS FOR OPERATIONAL DECISIONS IN: (a) LIFE-CRITICAL SYSTEMS, INCLUDING MEDICAL DEVICES, EMERGENCY SERVICES, LIFE-SUPPORT, AND CLINICAL DECISION-MAKING; (b) SAFETY-CRITICAL SYSTEMS, INCLUDING AVIATION, AUTOMOTIVE, RAIL, MARINE, INDUSTRIAL CONTROL, AND NUCLEAR SYSTEMS; (c) FINANCIAL TRANSACTION SYSTEMS SUBJECT TO REGULATORY ACCURACY OR AUDITABILITY REQUIREMENTS; OR (d) ANY OTHER SYSTEM WHERE A FAILURE, ERROR, OR OMISSION COULD REASONABLY BE EXPECTED TO RESULT IN DEATH, PERSONAL INJURY, OR SIGNIFICANT PROPERTY OR FINANCIAL DAMAGE. CUSTOMER IS SOLELY RESPONSIBLE FOR ENSURING APPROPRIATE HUMAN OVERSIGHT, INDEPENDENT VALIDATION, AND PROCEDURAL SAFEGUARDS BEFORE RELYING ON OUTPUTS — OR ACTIONS TAKEN BY THE SERVICE OR BY AI AGENTS ACTING ON OUTPUTS — IN ANY SUCH SYSTEM.**

## 12. Limitation of Liability

### 12.1 Cap on liability

**EXCEPT FOR EXCLUDED CLAIMS, EACH PARTY'S AGGREGATE LIABILITY ARISING OUT OF OR RELATING TO THE AGREEMENT, WHETHER IN CONTRACT, TORT, OR OTHERWISE, IS LIMITED TO THE GREATER OF (A) ONE HUNDRED U.S. DOLLARS ($100) OR (B) THE FEES PAID OR PAYABLE BY CUSTOMER UNDER THE AGREEMENT IN THE TWELVE (12) MONTHS PRECEDING THE EVENT GIVING RISE TO THE LIABILITY.**

### 12.2 Exclusion of certain damages

**EXCEPT FOR EXCLUDED CLAIMS, IN NO EVENT WILL EITHER PARTY BE LIABLE FOR ANY LOST PROFITS, LOST REVENUES, LOSS OF DATA, LOSS OF GOODWILL, OR ANY INDIRECT, INCIDENTAL, CONSEQUENTIAL, SPECIAL, OR PUNITIVE DAMAGES, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGES.**

### 12.3 Excluded Claims

"Excluded Claims" means: (a) Customer's payment obligations; (b) either party's breach of Section 9 (Confidentiality), excluding breaches arising from a security incident affecting Connected Data, Derived Artifacts, or other Customer Data, which are subject to the cap in Section 12.1; (c) either party's indemnification obligations under Section 13; (d) Customer's violation of Section 5 (Acceptable Use) or of OpenTrace's intellectual property rights; and (e) liability that cannot be excluded or limited under applicable law.

### 12.4 Duty to mitigate

Each party will use commercially reasonable efforts to mitigate any damages it incurs in connection with the Agreement. The limitations of liability in this Section 12 do not relieve a party of its obligation to mitigate.

## 13. Indemnification

### 13.1 OpenTrace indemnification

OpenTrace will defend Customer against any claim by an unaffiliated third party alleging that the Service, when used in accordance with the Documentation and these Terms, infringes that third party's patent, copyright, trademark, or trade secret right ("IP Claim"), and will indemnify Customer for amounts finally awarded against Customer or agreed in settlement of such IP Claim. If the Service becomes, or in OpenTrace's opinion is likely to become, the subject of an IP Claim, OpenTrace may, at its option: (a) procure for Customer the right to continue using the Service; (b) modify the Service so that it is non-infringing; or (c) terminate the affected Service Plan and refund any prepaid fees for the unused portion of the term. The foregoing states OpenTrace's entire liability for IP Claims. This Section 13.1 does not apply to free Service Plans or to OpenTrace Open-Source Components used outside the Service.

### 13.2 Customer indemnification

Customer will defend OpenTrace against any claim by an unaffiliated third party arising out of (a) Customer Code, Connected Data, Derived Artifacts, or other Customer Data, including any claim that they infringe third-party rights; (b) Customer's use of the Service in violation of these Terms or applicable law; or (c) Customer's violation of Section 5, and will indemnify OpenTrace for amounts finally awarded or agreed in settlement of such claim.

### 13.3 Procedure

The indemnified party must (a) promptly notify the indemnifying party in writing of the claim; (b) give the indemnifying party sole control of the defense and settlement, except that no settlement may impose any non-monetary obligation on the indemnified party without its consent; and (c) provide reasonable assistance at the indemnifying party's expense.

## 14. Data Protection and Security

### 14.1 Privacy Statement

OpenTrace processes Personal Data as described in the OpenTrace Privacy Statement, which is incorporated into these Terms by reference.

### 14.2 Data Processing Addendum

To the extent OpenTrace processes Personal Data on Customer's behalf in the course of providing the Service, the OpenTrace Data Processing Addendum ("DPA") applies and is incorporated by reference. The current DPA is made available to Customer upon written request to legal@opentrace.com. Where required, the parties will execute the DPA, including the standard contractual clauses contained therein.

### 14.3 Security

OpenTrace will implement and maintain administrative, technical, and physical safeguards designed to protect Connected Data, Derived Artifacts, and other Customer Data against unauthorized access, use, disclosure, alteration, or destruction. Details of OpenTrace's security program are described in the OpenTrace Security Documentation made available to Customer on request, subject to confidentiality obligations.

### 14.4 Subprocessors

OpenTrace uses Subprocessors to provide the Service. A current list of Subprocessors is published at docs.opentrace.com/subprocessor-list/. OpenTrace will provide notice of any new Subprocessor before that Subprocessor begins processing Customer Data, by updating the list and, where Customer has subscribed to Subprocessor change notifications, by email.

### 14.5 Security incidents

If OpenTrace becomes aware of any actual or reasonably suspected unauthorized access, acquisition, disclosure, or loss of Connected Data, Derived Artifacts, or other Customer Data ("Security Incident"), OpenTrace will notify Customer without undue delay and in any event within the timeframes required by applicable law, and will provide Customer with information reasonably required to satisfy Customer's notification and other obligations under applicable law.

## 15. Children

The Service is not directed to children under the age of 13, and OpenTrace does not knowingly collect Personal Data from children. If you are under the age of 13, do not register for or use the Service. If OpenTrace learns that it has collected Personal Data from a child under the age of 13, it will delete that information as quickly as possible. If you believe a child under the age of 13 has provided Personal Data to OpenTrace, please contact privacy@opentrace.com.

## 16. General

### 16.1 Governing law and venue

The Agreement is governed by the laws of the State of Delaware, United States, without regard to its conflict of laws principles. The state and federal courts located in Travis County, Texas have exclusive jurisdiction over any dispute arising out of or relating to the Agreement, and each party consents to the personal jurisdiction of those courts.

### 16.2 Notices

Notices to OpenTrace must be sent to legal@opentrace.com with a copy to OpenTrace, Inc., 14205 N Mo Pac Expy Ste 570, PMB 640435, Austin, Texas 78728-6529, USA. Notices to Customer may be sent to the email address associated with Customer's account or to the address set out on the applicable Order Form. Notices are deemed given on receipt.

### 16.3 Order Form and MSA precedence

These Terms govern Customer's use of the Service. If Customer and OpenTrace enter into a separately signed Master Services Agreement, Order Form, or other written agreement that expressly references these Terms, such agreement governs in respect of the matters expressly addressed therein, and these Terms continue to govern all other matters. In the event of a conflict between these Terms and a separately signed Order Form or MSA, the separately signed agreement prevails for the matters expressly addressed therein.

### 16.4 Assignment

Neither party may assign or transfer the Agreement without the other party's prior written consent, except that either party may assign the Agreement, on notice but without consent, to an Affiliate or in connection with a merger, acquisition, or sale of substantially all of its assets. Any other purported assignment is void.

### 16.5 Force majeure

Neither party is liable for any failure or delay in performance (other than payment obligations) caused by circumstances beyond its reasonable control, including acts of God, war, terrorism, civil unrest, labor disputes, internet or telecommunications failures, governmental orders, and pandemics.

### 16.6 Independent contractors

The parties are independent contractors. The Agreement does not create an agency, partnership, joint venture, or employment relationship.

### 16.7 Severability and waiver

If any provision of the Agreement is held unenforceable, the remaining provisions remain in effect, and the unenforceable provision will be modified to the minimum extent necessary to make it enforceable. A waiver is effective only if in writing and signed by the waiving party, and a waiver of any breach is not a waiver of any subsequent breach.

### 16.8 Entire agreement

The Agreement constitutes the entire agreement between the parties regarding its subject matter and supersedes all prior or contemporaneous communications, whether oral or written. The applicable open-source license for OpenTrace Open-Source Components governs Customer's use of those components in standalone, local-only configurations and is not superseded by these Terms.

### 16.9 Modifications to these Terms

OpenTrace may update these Terms from time to time. For material changes affecting Paid Service Plans, OpenTrace will provide at least thirty (30) days' advance notice by email or through the Service. Continued use of the Service after the effective date of a change constitutes acceptance of the updated Terms. If Customer does not agree to a change, Customer's sole remedy is to terminate the affected Service Plan before the effective date of the change.

### 16.10 U.S. Government end users

The Service is "commercial computer software" and the Documentation is "commercial computer software documentation," each as defined in 48 C.F.R. § 2.101. Use, duplication, and disclosure by U.S. Government end users are subject to the restrictions in these Terms.

### 16.11 Export and sanctions

Customer must comply with all applicable export control and economic sanctions laws. Customer represents that it is not located in, and is not a national of, any country subject to comprehensive U.S. sanctions, and is not on any U.S. or other applicable restricted-party list.

### 16.12 Limitation of actions

Except for claims relating to either party's intellectual property rights, claims arising from a violation of Section 5 (Acceptable Use), or claims that under applicable law cannot be subject to a contractual limitation period, no action, regardless of form, arising out of or relating to the Agreement may be brought by either party more than one (1) year after the cause of action accrued.

### 16.13 Notice of dispute and cure period

Before initiating any legal proceeding arising out of or relating to the Agreement, the party with the claim will give the other party written notice describing the claim in reasonable detail and a period of thirty (30) days from receipt of that notice to cure or otherwise resolve the matter. This Section 16.13 does not apply to actions for injunctive, equitable, or other emergency relief, or to proceedings to enforce indemnification obligations once the underlying third-party claim has been finally resolved. Notices under this Section must be sent in accordance with Section 16.2 (Notices).

### 16.14 Class action waiver

Each party agrees that any dispute arising out of or relating to the Agreement will be brought solely on an individual basis, and not as a plaintiff or class member in any purported class, collective, consolidated, or representative proceeding. To the extent permitted by applicable law, each party waives any right to participate in any class, collective, consolidated, or representative action.

### 16.15 Survival

Sections of these Terms that by their nature should survive termination or expiration of the Agreement will so survive, including without limitation Section 4 (Customer Code, Derived Artifacts, and Outputs), Section 8.5 (Effect of termination), Section 8.6 (Data export and deletion), Section 9 (Confidentiality), Section 10 (Intellectual Property), Section 12 (Limitation of Liability), Section 13 (Indemnification), Section 14 (Data Protection and Security), and Section 16 (General).

_— End of Terms of Service —_
