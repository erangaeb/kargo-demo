Okay, here's a detailed summary of e-invoicing in Hungary, combining information from all the provided sources, focusing on format guides, compliance requirements, and key aspects of the NAV system:

**I. Overview**

*   **E-Invoicing Status:**  E-invoicing itself is *not mandatory* in Hungary for B2B or B2G transactions. However, *real-time invoice reporting (RTIR) is mandatory* for nearly all transactions.
*   **RTIR Purpose:** The RTIR system, managed by the National Tax and Customs Administration of Hungary (NAV), is designed to combat VAT fraud and improve tax compliance.
*   **Platform:** The central platform is the **NAV Online Invoicing System (Online Számla)**.
*   **Key Legislation:** Act CXXVII of 2007 on Value Added Tax allows for electronic invoices.  The implementation of real-time reporting is the key driver.
*   **Directive Transposed:** 2014/55/EU (European standard on eInvoicing is fully implemented).

**II. Real-Time Invoice Reporting (RTIR)**

*   **Mandatory Since:**
    *   July 1, 2018: Initially for invoices with VAT ≥ HUF 100,000.
    *   January 2021: Extended to *all* B2B and B2C transactions, regardless of amount.
*   **What to Report:**  Data from all invoices, credit notes, and debit notes must be reported.
*   **Who Must Report:**
    *   All VAT-registered taxpayers resident in Hungary.
    *   Foreign companies with tax residence in Hungary.
    *   Foreign companies with VAT registration in Hungary.
    *   Anyone sending an invoice to domestic taxable persons for transactions in Hungary.
    *   Non-VAT liable persons or organizations.
*   **Exemptions:** Foreign distance sellers joining the OSS regime in July 2021 were initially exempt, but this should be verified for current status.
*   **Reporting Frequency:** Real-time.  Data must be transmitted to NAV immediately upon invoice issuance.

**III. NAV Online Invoicing System (Online Számla)**

*   **Centralized System:** NAV is the single platform for e-invoicing and reporting.
*   **Versions:**
    *   NAV Online 3.0: Mandatory from June 1, 2021.
    *   NAV Online 3.2: Released in November 2022 (current version as of the provided information). Includes error validations and technical cancellations.
    *   NAV Online 3.17: Released in March 31, 2022.
*   **Functionality:**
    *   Receives and validates invoice data in real-time.
    *   Makes reported invoice data available to customers as electronic invoices.
    *   Allows the Tax Authority to prepare draft VAT returns based on VAT data.
*   **Access:** Requires a Hungarian Electronic Government Gate, personal tax number, and business's tax number.

**IV. Invoice Format and Data Requirements**

*   **Mandatory Format for Reporting:** **XML** (NAV XML version 3.0). This is the *only* accepted format for submitting data to the NAV Online Invoicing System.
*   **Format for Invoice to Customer:** While XML is used for reporting, the actual invoice delivered to the customer can be in paper, PDF, or XML format.
*   **Required Information (Minimum):**
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
*   **Customer Info Field:** Must differentiate between invoices sent to Hungary, EU, or non-EU countries.
*   **VAT IDs:** Only one VAT ID (Hungarian, European, or non-European) can be provided.
*   **B2C Invoices:** Must *not* contain personal data (neither name nor address).

**V. Technical Implementation**

*   **Registration:** Register on the Online Számla platform.
*   **Technical User:** Create a technical user and keys within the NAV system. This is essential for connecting accounting software to the NAV system.
*   **ERP Integration:** Connect your ERP (Enterprise Resource Planning) or accounting software to the NAV system using the technical user details.
*   **Data Conversion:**  The ERP system's exported data must be treated and converted to the NAV-required XML format.  This often involves using a technology provider or developing custom integration.

**VI. eSignature and Archiving**

*   **eSignature:** *Not required* for XML invoices submitted through the NAV system.  Required if sending an invoice in PDF format.
*   **Archiving Period:**
    *   Standard: 5 years
    *   Accounting purposes: 8 years
*   **Archiving Location:** Archiving abroad is allowed under certain conditions.

**VII. Penalties for Non-Compliance**

*   A fine of up to HUF 500,000 (approximately EUR 1,280) *per invoice* for non-reporting or incorrect reporting.

**VIII. How to Prepare for E-Invoicing in Hungary**

1.  **Choose Compliant Software:** Select accounting or ERP software that supports the NAV XML format and real-time reporting requirements.
2.  **Partner with a Service Provider:** Consider using an e-invoicing service provider to handle the technical complexities of XML conversion and NAV integration.
3.  **Register with NAV:** Register on the Online Számla platform and create the necessary technical user credentials.
4.  **Test Thoroughly:**  Thoroughly test the integration between your system and the NAV system to ensure accurate and timely reporting.
5.  **Stay Updated:**  Monitor NAV's website and announcements for any changes to the regulations or XML schema.

**IX. Additional Information**

*   **SAF-T:** While not currently required, SAF-T (Standard Audit File for Tax) may be introduced in the future.
*   **EKAER:** Electronic reporting for risky goods transported by road is a separate requirement.
*   **VAT Gap Reduction:** Hungary has seen a significant reduction in its VAT gap since implementing these measures.

**X. Disclaimer**

*   This summary is based on the provided information and should not be considered legal or tax advice. Always consult with a qualified professional to ensure compliance with the latest regulations.

This detailed summary should provide a comprehensive understanding of e-invoicing and real-time reporting requirements in Hungary. Remember to always verify the latest information with the NAV and consult with tax professionals.
