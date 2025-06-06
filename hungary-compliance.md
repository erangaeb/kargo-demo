Okay, based on the provided summaries and previews, here's a detailed summary of the Hungarian e-invoicing specification, including format guides and compliance requirements:

**Overview:**

Hungary has implemented a Real-Time Invoice Reporting (RTIR) system, known as NAV Online Számla, mandated by the National Tax and Customs Administration of Hungary (NAV). The primary objective is to facilitate VAT-related data reporting, increase transparency, and combat tax fraud.  This system requires businesses to report invoice data electronically and in real-time to NAV.

**Key Aspects:**

*   **Governing Body:** National Tax and Customs Administration of Hungary (NAV)
*   **Legislation:** Primarily based on Act CXXVII of 2007 on VAT.
*   **Scope:**
    *   Applies to all VAT-registered and resident taxpayers in Hungary.
    *   Initially focused on B2B transactions, but now includes B2C transactions.
    *   Covers both VAT and VAT-exempt sales invoices.
    *   Includes cross-border transactions.
*   **Mandate Timeline:**
    *   Real-Time Information Reporting (RTIR) was effective from July 1st, 2018.
    *   Mandatory real-time reporting for all B2C and B2B transactions from April 1st, 2021.
*   **System:** NAV Online Számla (Online Invoice System)
*   **Format:** XML is the required format for electronic invoices.
*   **Transmission:** Invoices must be transmitted electronically to the NAV system in real-time.

**Compliance Requirements:**

*   **Registration:** Businesses must register with NAV to use the Online Számla system.
*   **Real-Time Reporting:**  Invoice data must be reported to NAV in real-time. This means immediately after the invoice is issued.
*   **Data Requirements:**  Specific data elements are required in the XML format, as defined by NAV.  This includes details about the supplier, customer, invoice date, invoice number, items, quantities, prices, VAT rates, and VAT amounts.
*   **XML Schema:**  Businesses must adhere to the XML schema defined by NAV.  This schema specifies the structure and content of the XML file.
*   **Digital Signature (Likely):** While not explicitly stated in the summaries, it's highly probable that a digital signature is required for authentication and non-repudiation of the submitted invoices.  This is a common practice in e-invoicing systems.  *Further research is needed to confirm this.*
*   **Archiving:**  Businesses are responsible for archiving the electronic invoices according to Hungarian regulations.
*   **Error Handling:**  Businesses must have processes in place to handle errors during the transmission and processing of invoices.
*   **Exemptions (Limited):**  While the summaries don't explicitly detail exemptions, it's possible that certain types of transactions or businesses may be subject to different rules or thresholds.  *Further research is needed to confirm this.*

**Format Guides (Based on XML):**

*   **XML Structure:** The XML file must conform to the NAV-defined schema. This schema dictates the elements, attributes, and data types that are allowed in the XML file.
*   **Data Elements:**  The XML file must include specific data elements, such as:
    *   Supplier Information: Name, address, VAT number
    *   Customer Information: Name, address, VAT number (if applicable)
    *   Invoice Details: Invoice number, invoice date, due date
    *   Item Details: Description, quantity, unit price, VAT rate, VAT amount
    *   Totals: Net amount, VAT amount, gross amount
*   **Encoding:**  The XML file must be encoded in a specific character encoding (e.g., UTF-8).
*   **Validation:**  Before submitting the XML file to NAV, businesses should validate it against the NAV schema to ensure that it is well-formed and contains all the required data elements.

**Important Considerations and Next Steps:**

*   **Official NAV Documentation:** The most accurate and up-to-date information can be found on the official NAV website.  Businesses should consult the official documentation for the latest requirements, schema definitions, and technical specifications.
*   **Software Solutions:**  Many software vendors offer solutions that can help businesses comply with the Hungarian e-invoicing requirements.  These solutions can automate the process of generating, validating, and transmitting XML invoices to NAV.
*   **Digital Signature:**  Confirm whether a digital signature is required and, if so, the specific requirements for the signature.
*   **Exemptions and Thresholds:**  Investigate whether any exemptions or thresholds apply to your business.
*   **Testing:**  Thoroughly test your e-invoicing solution before going live to ensure that it meets all the requirements.

This summary provides a comprehensive overview of the Hungarian e-invoicing specification based on the provided information.  However, it is essential to consult the official NAV documentation for the most accurate and up-to-date information.