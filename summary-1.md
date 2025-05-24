Okay, here's a detailed summary of e-invoicing in Hungary, combining information from all the provided sources, focusing on format guides, compliance requirements, and practical implementation:

**I. Overview of E-Invoicing and Digital Reporting in Hungary**

*   **Not Fully Mandatory, but Real-Time Reporting is Key:** While true e-invoicing (requiring electronic issuance and receipt) isn't fully mandated for B2B transactions, Hungary has a robust real-time reporting system (RTIR) that effectively makes electronic data submission essential.
*   **Centralized System:** Hungary uses a centralized system managed by the National Tax and Customs Administration of Hungary (NAV).
*   **NAV Online Számla:** The core platform is the NAV Online Számla (Online Invoice System). This is a web portal where businesses submit invoice data in real-time.
*   **Continuous Transaction Controls (CTC):** Hungary employs a Continuous Transaction Controls model.
*   **Post-Audit:** Electronic invoices are subject to post-audit.

**II. Legal and Regulatory Framework**

*   **Key Legislation:**
    *   Act CXXVII of 2007 on Value Added Tax (allows for electronic invoices).
    *   Act LXXXIII of 2018 (introduced real-time invoice reporting).
    *   Directive 2014/55/EU (transposed into Hungarian law).
*   **Real-Time Information Reporting (RTIR):**
    *   Introduced in July 2018 for invoices with VAT amounts ≥ HUF 100,000.
    *   Expanded in April 2021 to include *all* B2B and B2C transactions, regardless of the amount.
*   **Governing Entity:** NAV (Nemzeti Adó- és Vámhivatal)

**III. Scope and Applicability**

*   **Taxpayers Affected:**
    *   All VAT-registered and resident taxpayers in Hungary.
    *   Foreign companies with tax residence in Hungary.
    *   Foreign companies with VAT registration in Hungary.
    *   Anyone sending an invoice to domestic taxable persons for transactions in Hungary.
*   **Transactions Covered:**
    *   Domestic B2B and B2C transactions.
    *   Cross-border transactions (exports and intra-EU).
*   **Documents Covered:** Invoices, Credit notes, Debit Notes

**IV. Technical Requirements and Formats**

*   **Mandatory Format for Reporting:** XML (NAV XML version 3.0). This is the *only* accepted format for submitting data to the NAV Online Számla system.
*   **Format for Exchange with Buyer/Recipient:**
    *   Paper, PDF, or XML for electronic invoices.  The choice is up to the trading partners.
*   **eSignature/Seal:**
    *   Not required when reporting via XML to NAV.
    *   Mandatory if you send an invoice in PDF format.
*   **NAV Online 3.0 and Later:**
    *   Mandatory since June 1, 2021.
    *   Version 3.17 (March 31, 2022): Introduced error validations and browser limitations.
    *   Version 3.2 (November 2, 2022): Amended technical cancellation processes and personal data display requirements.
*   **Information Required on Invoices (for reporting):**
    *   Issuance date
    *   Unique sequential number
    *   Supplier’s VAT number
    *   Supplier’s and customer’s full names and addresses
    *   Clear description of goods or services
    *   Quantity of goods
    *   Date of supply if different from the date of issuance
    *   Total taxable value of the supply
    *   VAT rate
    *   Full details supporting zero VAT
    *   Gross value of the invoice
    *   Customer info field adapted to differentiate between invoices sent to Hungary, EU, or non-EU countries.
    *   Only one VAT ID (Hungarian, European, or non-European) may be used.
    *   B2C invoices must not contain personal data (neither name nor address).

**V. Implementation and Process**

1.  **Registration:** Register on the Online Számla platform. This requires a Hungarian Electronic Government Gate, personal tax number, and business’s tax number.
2.  **Technical User:** Create a technical user and technical keys within the Online Számla system. This is how your accounting software will connect.
3.  **ERP Connection:** Connect your ERP (or accounting software) to the NAV system using the technical user details.
4.  **Invoice Issuance:** Create and issue invoices using your ERP system.
5.  **Real-Time Reporting:** Report the invoice data to NAV in real-time, in the required XML format. This can be done directly or through a service provider.

**VI. Archiving**

*   **Archiving Period:**
    *   Standard: 5 years
    *   Accounting purposes: 8 years from the issuance of the document.
*   **Archiving Abroad:** Allowed under certain conditions.

**VII. Penalties for Non-Compliance**

*   The Hungarian Tax Authority can penalize taxpayers up to HUF 500,000 (approximately EUR 1,280) per unreported or incorrectly reported invoice.

**VIII. Key Considerations and Best Practices**

*   **Accounting Software:** Use reliable accounting software that supports XML export in the NAV-required format.
*   **E-Invoicing Service Provider:** Consider partnering with a reliable e-invoicing service provider to ensure compliance and streamline the reporting process.
*   **Data Accuracy:** Ensure the accuracy and completeness of invoice data to avoid penalties.
*   **Stay Updated:** Keep abreast of any changes to the NAV Online Számla system and reporting requirements.
*   **NAV Resources:** Utilize the resources available on the NAV website (legislation, technical documentation, guidelines, FAQs).

**IX. SAF-T**

*   SAF-T is currently *not* required in Hungary, but it is expected to be introduced in the near future.

**X. EKAER**

*   **EKAER (Electronic Public Road Trade Control System):** Specific data on risky goods transported by road domestically or to and from the EU should be reported electronically. Some exceptions apply.

**In summary, while e-invoicing itself isn't fully mandated, the real-time reporting requirement via the NAV Online Számla system effectively necessitates electronic data submission in a specific XML format. Compliance with these regulations is crucial for all VAT-registered businesses in Hungary.**