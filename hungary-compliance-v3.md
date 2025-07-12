Okay, based on the provided (limited) information, here's a detailed summary of the Hungarian e-invoicing specification, focusing on format guides, compliance requirements, and key aspects:

**I. Overview:**

*   **Mandatory Real-Time Reporting:** Hungary operates a real-time reporting system for invoices through the NAV Online Számla (Online Invoice System).  This means invoice data must be submitted to the tax authority (NAV - Nemzeti Adó- és Vámhivatal) in real-time or near real-time.
*   **Scope:** The system covers both B2B and B2C transactions, including cross-border transactions involving VAT-registered and resident taxpayers in Hungary.
*   **Governing Entity:** The National Tax and Customs Administration of Hungary (NAV) is the governing authority.
*   **B2G Mandate:**  The provided information indicates that B2G e-invoicing is *not* required.
*   **B2B Mandate:** The provided information indicates that B2B e-invoicing is *not* required. However, *reporting* of B2B invoices *is* required. This is a crucial distinction.
*   **Threshold:** Initially, the real-time reporting obligation applied to invoices with a VAT amount of at least 100,000 HUF (approximately 250 EUR).  It's important to verify if this threshold still exists or if it has been lowered or eliminated.

**II. Format and Transmission:**

*   **Format for Sending to NAV:**  The required format for submitting invoice data to NAV is **XML**.
*   **Format for Exchange with Customers:** While the submission to NAV must be in XML, the invoice exchanged with the customer can be in various formats, including:
    *   Paper
    *   PDF
    *   XML
*   **Platform:** The NAV Online Számla system is the platform for submitting invoice data.

**III. Compliance Requirements:**

*   **Real-Time Reporting (RTIR):**  The core compliance requirement is the real-time reporting of invoice data to NAV. This involves:
    *   Generating invoices with the required data elements.
    *   Converting the invoice data into the specified XML format.
    *   Transmitting the XML data to the NAV Online Számla system.
*   **Data Elements:**  The specific data elements required in the XML submission are crucial for compliance.  These likely include:
    *   Supplier information (name, address, VAT ID)
    *   Customer information (name, address, VAT ID, if applicable)
    *   Invoice number
    *   Invoice date
    *   Supply date
    *   Description of goods or services
    *   Quantity
    *   Unit price
    *   Net amount
    *   VAT rate
    *   VAT amount
    *   Gross amount
    *   Currency
*   **Digital Signature/Authentication:**  It's likely that the XML submission requires a digital signature or other authentication mechanism to ensure the integrity and authenticity of the data.
*   **System Integration:**  Businesses need to integrate their accounting or ERP systems with the NAV Online Számla system to automate the data extraction, conversion, and transmission process.
*   **Archiving:**  Businesses are responsible for archiving their invoices according to Hungarian regulations.

**IV. Key Considerations and Potential Issues:**

*   **XML Schema:**  NAV provides a specific XML schema that defines the structure and data types for the invoice data submission.  Adherence to this schema is critical.
*   **Error Handling:**  Businesses need to implement robust error handling mechanisms to address any issues during the data submission process.
*   **Updates and Changes:**  The Hungarian e-invoicing regulations and the NAV Online Számla system are subject to change.  Businesses need to stay informed about any updates and adapt their systems accordingly.
*   **Penalties:**  Failure to comply with the e-invoicing regulations can result in penalties.
*   **Detailed Documentation:**  NAV provides detailed documentation and guidelines on the NAV Online Számla system and the e-invoicing requirements.  This documentation is essential for compliance.
*   **2025 Requirements:** The mention of "E-Invoicing in Hungary [2025 Requirements]" suggests potential upcoming changes or enhancements to the system.  It's crucial to investigate these requirements further.

**V. Next Steps (To get a complete picture):**

To provide a truly comprehensive summary, you need to:

1.  **Access the Official NAV Documentation:**  The most important step is to access the official documentation and specifications provided by NAV.  This will provide the definitive information on the XML schema, data elements, transmission protocols, and compliance requirements.
2.  **Investigate the 2025 Requirements:**  Research the specific details of the "E-Invoicing in Hungary [2025 Requirements]" to understand any upcoming changes.
3.  **Confirm Thresholds:** Verify if the 100,000 HUF VAT threshold still applies or if it has been modified.
4.  **Clarify B2B Mandate:**  While the provided information states B2B e-invoicing is not required, it's crucial to confirm that *reporting* is mandatory.  This is a common source of confusion.
5.  **Understand Authentication Methods:**  Determine the specific authentication methods required for submitting data to NAV.

Without access to the official NAV documentation, this summary is based on limited information and may not be entirely accurate.  The official documentation is the definitive source for compliance.
