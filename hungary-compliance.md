Okay, based on the information provided, here's a detailed summary of e-invoicing in Hungary, covering format guides, compliance requirements, and other relevant aspects:

**Overview:**

Hungary operates a real-time invoice reporting system managed by the **Nemzeti Adó- és Vámhivatal (NAV)**, the National Tax and Customs Administration.  The primary goal is to increase transparency, combat tax fraud, and facilitate VAT-related data reporting.  This system mandates that businesses report invoice data to NAV in real-time.

**Key Features and Requirements:**

*   **Mandatory Real-Time Reporting (RTIR):**  All VAT-registered businesses in Hungary are required to report invoice data to NAV in real-time. This applies to both B2B and B2C transactions.
*   **Scope:**
    *   **Transactions Covered:**  Generally, all B2B and B2C sales invoices, including VAT or VAT-exempt transactions, must be reported.
    *   **Exclusions:** Initially, exports and EU dispatches were excluded, but the system has evolved to include more transaction types.  It's crucial to verify the current scope with the latest NAV regulations.
*   **Governing Entity:** Nemzeti Adó- és Vámhivatal (NAV)
*   **Effective Date:** Real-time reporting has been in effect since July 1, 2018.
*   **Format:**
    *   **Reporting Format:**  Data must be submitted to NAV in a specific **XML format**. This is the critical format for compliance.
    *   **Invoice Exchange Format:** While the reporting to NAV is XML, the actual invoice exchanged between businesses can be in various formats, including:
        *   XML
        *   PDF
        *   Paper
*   **Platform:** NAV Online Számla (NAV Online Invoice System) is the platform used for reporting.

**Compliance Requirements and Process:**

1.  **Invoice Generation:**  Create an invoice that includes all mandatory information.
2.  **Data Extraction:** Extract the required data from the invoice.
3.  **XML Conversion:** Convert the extracted data into the NAV-specified XML format.
4.  **Real-Time Reporting:** Submit the XML data to the NAV Online Számla system in real-time.
5.  **Archiving:**  Maintain proper digital archiving of invoices.

**Mandatory Invoice Information:**

Hungarian invoices must contain the following information:

*   **Document Title:** Clearly identify the document as an "Invoice," "Credit Note," etc.
*   **Supplier Information:**
    *   Supplier's Name and Address
    *   Tax Number/VAT Identification Number
*   **Invoice Details:**
    *   Invoice Number (unique and sequential)
    *   Invoice Date
*   **Customer Information:**
    *   Correct Billing Address of the Recipient
*   **Transaction Details:**
    *   Date of Delivery of Goods or Services (if different from invoice date)
    *   Description of Goods or Services
    *   Quantity
    *   Unit Price
    *   Net Amount
    *   VAT Amount (if applicable)
    *   Applicable Tax Rates
    *   Total Gross Amount
*   **Additional Information (if applicable):**
    *   Discounts and Price Reductions
    *   Prepayments
    *   Exchange Rate (for invoices in non-local currency)
    *   VAT Exemption Reason (if applicable)
    *   Indications for Intra-Community Supply or Delivery

**Format Guidelines (XML):**

The most critical aspect of compliance is adhering to the NAV-specified XML format.  This format dictates the structure and content of the data submitted to NAV.  Specific details about the XML schema can be found on the NAV website.  Key considerations include:

*   **Data Types:**  Using the correct data types (e.g., dates, numbers, strings) as defined in the schema.
*   **Mandatory Fields:**  Ensuring all mandatory fields are populated with valid data.
*   **XML Structure:**  Following the exact hierarchical structure defined by the NAV schema.
*   **Versioning:**  Using the correct version of the XML schema, as NAV may update it periodically.

**Other Important Considerations:**

*   **Digital Archiving:**  Invoices must be digitally archived in a VAT-compliant manner.  PDF/A-3 is a common format used for digital preservation.
*   **European Norm 16931:**  This standard supports e-invoicing in public procurement and is relevant if you are doing business with Hungarian government entities.
*   **Common Standards:**  UBL (Universal Business Language) and UN/CEFACT are common e-invoicing standards, although the NAV system requires a specific XML format.
*   **Service Providers:**  Companies like EDITEL, Comarch, and ecosio offer e-invoicing solutions that can help businesses comply with Hungarian regulations.  These solutions often handle the XML conversion and real-time reporting process.
*   **Language:**  While the invoice itself can be in multiple languages, the data submitted to NAV must adhere to the specified data requirements.

**Consequences of Non-Compliance:**

Failure to comply with Hungarian e-invoicing regulations can result in penalties and fines.

**Recommendations:**

*   **Consult the NAV Website:**  The official NAV website is the definitive source for the latest regulations, XML schemas, and technical documentation.
*   **Use Certified Software:**  Implement e-invoicing software that is certified to comply with Hungarian regulations.
*   **Seek Expert Advice:**  Consult with a tax advisor or e-invoicing specialist to ensure full compliance.
*   **Stay Updated:**  Keep abreast of any changes to the regulations or XML schema.

This detailed summary should provide a comprehensive understanding of e-invoicing in Hungary. Remember to always refer to the official NAV documentation for the most up-to-date and accurate information.