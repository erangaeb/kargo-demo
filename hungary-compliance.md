Okay, here's a detailed summary of the eInvoicing landscape in Hungary, compiled from all the provided markdown content. This summary covers legislation, technical specifications, compliance requirements, and practical considerations.

**I. Overview**

* **E-Invoicing is Voluntary, but Digital Reporting is Mandatory:** Hungary doesn't mandate the use of electronic invoices themselves, but it *does* require real-time reporting of invoice data to the National Tax and Customs Administration of Hungary (NAV). This is a Continuous Transaction Control (CTC) model.
* **Real-Time Invoice Reporting (RTIR):** This is the core of the Hungarian system. Virtually all outgoing transactions must be reported to NAV in real-time.
* **NAV Online Számla:** This is the central platform for RTIR. It's the "Online Invoice System" operated by NAV.

**II. Legislation and Regulatory Framework**

* **Responsible Authority:** National Tax and Customs Administration of Hungary (NAV) (Nemzeti Adó- és Vámhivatal).
* **Legal Basis:** Act CXXVII of 2007 on Value Added Tax allows for electronic invoices.
* **EU Directive Transposition:** Hungary has fully implemented the European standard on eInvoicing (Directive 2014/55/EU).
* **No B2B Mandate:** There's no legal requirement for businesses to *receive* e-invoices electronically. Buyer's consent is required.
* **Monitoring Mechanism:** The NAV Online Számla system serves as the monitoring mechanism.

**III. Scope and Applicability**

* **Taxpayers Affected:**
 * All VAT-registered and resident taxpayers in Hungary.
 * Foreign companies with tax residence in Hungary.
 * Anyone sending an invoice to domestic taxable persons.
 * Non-VAT liable persons or organizations.
 * Foreign VAT liable persons.
* **Transactions Covered:**
 * Domestic B2B and B2C transactions.
 * Cross-border transactions (exports and intra-EU sales).
* **Documents Covered:** Invoices, credit notes, and debit notes.

**IV. Technical Specifications**

* **Format for Reporting to NAV:** XML (specifically, NAV XML version 3.0). This is mandatory for reporting via Online Számla.
* **Format for Exchange with Buyer:** Paper, PDF, or XML (for electronic invoices).
* **eSignature:**
 * Not required for XML format (validation is instant).
 * Mandatory for PDF format.
* **Platform:**
 * **RTIR:** NAV Online Számla.
 * **E-Invoice:** No specific infrastructure mandated for the e-invoice itself (the XML is for reporting).

**V. Reporting Process**

1. **Registration:** Register on the Online Számla platform. This requires a Hungarian Electronic Government Gate, personal tax number, and business's tax number.
2. **Technical User:** Create a technical user and technical keys within the Online Számla system. This is how your accounting software will connect.
3. **ERP Connection:** Connect your ERP (or accounting software) to the NAV system using the technical user details.
4. **Invoice Issuance:** Generate the invoice from your ERP system.
5. **Real-Time Reporting:** Report the invoice data to NAV in real-time, in the required XML format. This can be done directly or through a service provider. Manual entry has a five-day grace period.

**VI. Data Requirements for Reporting**

The XML report to NAV must include:

* Issuance date
* Unique sequential number
* Supplier’s VAT number
* Supplier’s and customer’s full names and addresses
* Description of goods or services
* Quantity of goods
* Date of supply if different from the date of issuance
* Total taxable value of the supply
* VAT rate
* Full details supporting zero VAT
* Gross value of the invoice

**VII. Archiving**

* **Archiving Period:**
 * Standard: 5 years.
 * Accounting purposes: 8 years from the issuance of the document.
* **Archiving Abroad:** Allowed under certain conditions.

**VIII. Penalties for Non-Compliance**

* Up to HUF 500,000 (approximately EUR 1,280) per unreported or incorrectly reported invoice.

**IX. Key Dates and Updates**

* **July 1, 2018:** Real-time reporting introduced for invoices with VAT >= 100,000 HUF.
* **January 1, 2021:** Real-time reporting mandated for all B2B and B2C transactions.
* **June 1, 2021:** NAV Online 3.0 became mandatory.
* **November 2, 2022:** Version 3.2 released with technical amendments.

**X. Practical Considerations and Recommendations**

* **Accounting Software:** Use reliable accounting software to minimize manual input and ensure proper XML generation.
* **Service Provider:** Consider partnering with a reliable e-invoicing service provider to ensure compliance and simplify the reporting process.
* **NAV Registration:** Register for the NAV Online Számla system.
* **Data Accuracy:** Ensure the accuracy and completeness of invoice data to avoid penalties.
* **Stay Updated:** Keep abreast of any legislative changes or updates to the NAV Online Számla system.

**XI. SAF-T**

* SAF-T (Standard Audit File for Tax) is currently *not* required in Hungary, but its introduction is expected in the future.

**XII. Disclaimer**

* This information is for informational purposes only and does not constitute tax advice. Consult with a tax professional for specific guidance related to your business.

In summary, while e-invoicing itself is voluntary in Hungary, the mandatory real-time reporting requirements through the NAV Online Számla system necessitate a robust and compliant process for generating and submitting invoice data in the required XML format. Understanding these requirements is crucial for businesses operating in Hungary to avoid penalties and ensure compliance.