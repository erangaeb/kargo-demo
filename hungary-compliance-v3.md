Okay, based on the provided information, here's a detailed summary of e-invoicing in Hungary, covering format guides, compliance requirements, and other relevant details:

**I. Overview:**

* **System Name:** NAV Online Számla (operated by Nemzeti Adó és Vámhivatal - NAV, the Hungarian Tax and Customs Authority)
* **Mandate:** Real-Time Invoice Reporting (RTIR) is mandatory for B2B and B2C transactions. While *mandatory e-invoicing* (in the sense of requiring structured electronic invoices to be exchanged between businesses) isn't universally mandated *yet*, real-time reporting to NAV effectively necessitates electronic invoice creation.
* **Scope:** Applies to all VAT-registered businesses in Hungary.
* **Transactions Covered:** Primarily B2B and B2C transactions, including cross-border transactions. Initially, reporting focused on invoices with a VAT amount exceeding HUF 100,000 (approximately EUR 250), but this threshold has been removed.
* **Governing Entity:** NAV (Nemzeti Adó és Vámhivatal)

**II. Compliance Requirements:**

* **Real-Time Reporting:** The core requirement is real-time reporting of invoice data to NAV's Online Számla system. This means invoice data must be submitted to NAV immediately after issuance.
* **Registration:** Businesses must register on the Online Számla platform.
* **Technical User & Keys:** Creation of a technical user and associated keys is required to establish a secure connection between the business's ERP system and the NAV system.
* **Automated Submission:** Invoice data must be submitted automatically via the KOBAK online portal (or a direct API connection).
* **Data Retention:** Invoices must be archived for 8 years from the end of the annual financial statement.

**III. Invoice Format and Data Requirements:**

* **Format for NAV Submission:** **XML** is the required format for submitting invoice data to the NAV Online Számla system. NAV supports XML version 3.0.
* **Format for Exchange with Buyer/Recipient:** While the submission to NAV must be in XML, the invoice exchanged with the buyer/recipient can be in various formats, including:
 * Paper
 * PDF
 * XML
* **Required Invoice Data:** The invoice must contain the following information:
 * Document Title (e.g., "Invoice," "Credit Note")
 * Supplier Data:
 * Name
 * Address
 * Tax/VAT Number
 * Invoice Number
 * Invoice Date
 * Customer Data:
 * Name
 * Address
 * Date of Supply (Delivery of goods/services)
 * Description of Goods/Services
 * Quantity
 * Unit Price
 * Net Amount
 * VAT Rate
 * VAT Amount
 * Gross Amount (Total)
 * Additional Information (if applicable):
 * Discounts
 * Prepayments
 * Exchange Rates
 * VAT Exemptions (with appropriate justification)
 * Intra-Community Supply Details
* **XML Structure:** The XML structure must conform to the specifications defined by NAV. This includes specific elements, attributes, and data types. Refer to the official NAV documentation for the precise XML schema.

**IV. Penalties for Non-Compliance:**

* Significant penalties can be imposed for failing to comply with the e-invoicing regulations.
* Penalties can be up to HUF 500,000 (per invoice) for unreported or incorrectly reported invoices.

**V. Future Requirements:**

* Mandatory e-invoicing for the electricity and natural gas sectors is planned for January 2025. This suggests a potential broader move towards mandatory e-invoicing in the future.

**VI. Key Considerations and Best Practices:**

* **Accuracy:** Ensure all invoice data is accurate and complete to avoid rejection by the NAV system and potential penalties.
* **Automation:** Implement automated solutions to streamline the invoice creation and submission process. This reduces the risk of errors and improves efficiency.
* **Integration:** Integrate your ERP system with the NAV Online Számla system to enable seamless data exchange.
* **Compliance Monitoring:** Stay up-to-date with the latest regulations and guidelines issued by NAV.
* **Testing:** Thoroughly test your e-invoicing solution before going live to ensure it meets all requirements.
* **Seek Expert Advice:** Consider consulting with e-invoicing experts or solution providers to ensure compliance and optimize your e-invoicing processes.

**VII. E-Invoicing Service Providers:**

* Several providers offer solutions to help businesses comply with Hungarian e-invoicing regulations. Examples include:
 * EDITEL
 * Comarch
 * Storecove
 * Avalara
 * INFINITE IT SOLUTIONS
* These providers offer services such as:
 * VAT compliance
 * Digital archiving
 * Supply chain finance
 * Data format verification
 * EDI (Electronic Data Interchange)
 * E-archiving

**VIII. Standards and Formats (General E-Invoicing Context):**

* While Hungary mandates XML for NAV submission, it's worth noting general e-invoicing standards:
 * **European Norm 16931:** Supports e-invoicing in public procurement.
 * **UBL (Universal Business Language):** A common XML-based standard.
 * **UN/CEFACT:** Another widely used standard.
 * **PDF/A-3:** Used for digital preservation of electronic documents.

**In summary, Hungarian e-invoicing is characterized by its real-time reporting requirement to the NAV Online Számla system using XML. Businesses must register, establish a secure connection, and submit invoice data electronically. Compliance is crucial to avoid penalties. While the invoice exchanged with the buyer can be in various formats, the XML submission to NAV is the key compliance aspect.**