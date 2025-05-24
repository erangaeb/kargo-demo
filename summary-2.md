Okay, here's a comprehensive summary of e-invoicing in Hungary, based on all the provided documents, covering format guides, compliance requirements, and other relevant details:

**I. Overview**

*   **Not Mandatory (But Effectively So):** While true *e-invoicing* (in the sense of a structured electronic invoice being the primary document exchanged between buyer and seller) is *not* strictly mandatory in Hungary, *real-time reporting* of invoice data to the National Tax and Customs Administration of Hungary (NAV) is.  This real-time reporting requirement effectively necessitates the use of electronic systems and structured data formats.
*   **Real-Time Reporting (RTIR):** The core of the Hungarian system is Real-Time Invoice Reporting (RTIR) to the NAV. This requires taxpayers to report invoice data *immediately* to the NAV.
*   **Centralized System:** Hungary uses a centralized platform, the NAV Online Invoicing System (Online Számla), for real-time invoice reporting.
*   **Governing Body:** The National Tax and Customs Administration of Hungary (NAV) is the responsible authority.

**II. Legislation and Scope**

*   **Regulation:** Based on Act CXXVII of 2007 on Value Added Tax.
*   **Directive Transposed:** 2014/55/EU (European standard on eInvoicing).
*   **Mandatory For:**
    *   **Reporting:** All VAT-registered and resident taxpayers in Hungary.
    *   **Transactions:**  B2B and B2C transactions.  Cross-border transactions (exports and intra-EU sales) are also included.
*   **Scope Expansion:**
    *   July 2018: Initially mandated for invoices with VAT amount >= 100,000 HUF (approx. 250 EUR).
    *   January 2021: Extended to *all* B2B and B2C transactions, regardless of amount.
*   **Affected Parties:**
    *   Companies located in and doing business in/out of Hungary.
    *   Foreign companies with tax residence in Hungary.
    *   Anyone sending an invoice to domestic taxable persons for transactions in Hungary.
    *   Non-VAT liable persons/organizations.
    *   Foreign VAT liable persons.
    *   Foreign companies with VAT registration in Hungary.
*   **Documents Covered:** Invoices, Credit Notes, Debit Notes.

**III. Technical Details and Format**

*   **Platform:** NAV Online Számla (Online Invoice System).
*   **Format:**
    *   **Mandatory Format for Reporting:** XML (NAV XML version 3.0).  This is the *only* accepted format for reporting to NAV.
    *   **Format for Exchange with Buyer:** Paper, PDF, or XML (for electronic invoices).
*   **European Standard Compliance:** The XML format is fully compliant with the European Standard on eInvoicing (EN).
*   **Digital Signature:** Not required for XML. Mandatory only for PDF format.
*   **NAV Online 3.0 (and later versions):** Became mandatory from June 1, 2021.  NAV Online 3.2 was released in November 2022.
*   **Key Information Required on Invoices (for reporting):**
    *   Issuance date
    *   Unique sequential number
    *   Supplier’s VAT number
    *   Supplier’s and customer’s full names and addresses
    *   Description of goods or services
    *   Quantity of goods
    *   Date of supply if different from the date of issuance
    *   Total taxable value of the supply
    *   VAT rate
    *   Full details supporting zero VAT
    *   Gross value of the invoice
*   **Customer Info Field:** Adapted to differentiate between invoices sent to Hungary, EU, or non-EU countries. Only one VAT ID (Hungarian, European, or non-European) may be used.
*   **B2C Invoices:** Must *not* contain personal data (neither name nor address).

**IV. Implementation and Process**

1.  **Registration:** Register on the Online Számla platform. Requires a Hungarian Electronic Government Gate, personal tax number, and business’s tax number.
2.  **Technical User:** Create a technical user and technical keys to connect accounting software to the NAV system.
3.  **ERP Connection:** Connect your ERP system to the NAV system using the technical user details.
4.  **Invoice Issuance:** Generate invoices with your invoicing software.
5.  **Real-Time Reporting:** Report the electronic invoice in real-time and in XML format to NAV.

**V. Archiving**

*   **Archiving Period:**
    *   Standard: 5 years
    *   Accounting purposes: 8 years
*   **Archiving Abroad:** Allowed under certain conditions.

**VI. Penalties**

*   Up to 500,000 HUF (approximately 1,280 EUR) per unreported or incorrectly reported invoice.

**VII. Other Digital Reporting Obligations**

*   **EKAER (Electronic Public Road Trade Control System):** Reporting of specific data on risky goods transported by road domestically or to/from the EU.

**VIII. Key Considerations for Compliance**

*   **Accounting Software:** Use reliable accounting software to minimize manual input.
*   **E-invoicing Service Provider:** Partner with a reliable e-invoicing service provider to ensure compliance.
*   **NAV System Registration:** Register for the NAV system.

**IX. Future Developments**

*   SAF-T is not currently required but is expected to be introduced in the future.
*   No legislative changes are foreseen for the time being.

**In summary, while Hungary doesn't mandate *true* e-invoicing, the real-time reporting requirement to NAV, using a specific XML format, effectively necessitates electronic processes for most businesses.  Compliance requires registration with the NAV Online Számla system, connection of accounting systems, and immediate reporting of invoice data in the required XML format.**