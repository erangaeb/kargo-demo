Okay, here's a detailed summary of the Hungarian e-invoicing system based on the provided information, including format guides, compliance requirements, and other relevant details:

**Overview:**

Hungary has a mandatory real-time invoice reporting system called **NAV Online Számla** (Online Invoice System) operated by the **NAV (Nemzeti Adó és Vámhivatal)**, the Hungarian Tax and Customs Administration. This system requires businesses to report invoice data to the NAV in real-time.

**Key Features and Requirements:**

* **Mandate:** Real-time reporting of invoice data to NAV is mandatory for **all VAT-registered and resident taxpayers in Hungary.**
* **Scope:**
 * **B2B and B2C transactions** are generally included.
 * Initially, the mandate focused on invoices with a minimum VAT amount of **100,000 HUF (approximately 250 EUR)**. The threshold has likely changed since the initial implementation.
 * **All B2B Sales invoices, with VAT or exempt** are included.
* **Exclusions (Historically - Verify Current Status):**
 * Exports and EU dispatches were initially excluded.
 * B2C transactions were initially excluded (until 2021). **Important: Confirm if B2C reporting is now mandatory.**
* **Real-Time Information Reporting (RTIR):** The system is based on real-time reporting, meaning invoice data must be submitted to NAV as it is issued. This has been in effect since **July 1st, 2018.**
* **Format:**
 * **XML:** The required format for sending invoice data to the NAV Online Számla platform is **XML**.
 * **Exchange with Buyer/Recipient:** For exchange with the buyer/recipient, invoices can be in **Paper, PDF, or XML format.**
* **Compliance:** VAT compliant e-invoice processing is a key requirement.
* **Languages:** Supported languages include Hungarian, English, and potentially others.
* **European Standards:** The European Norm 16931 supports e-invoicing in public procurement. Syntax formats approved by CEN include UBL and UN/CEFACT.

**Detailed Invoice Content Requirements (General):**

While the specific XML schema required by NAV is not provided in the source material, here's a general list of information that is typically required on an invoice and likely needs to be included in the XML data submitted to NAV:

1. **Basic Information:**
 * Document Title (e.g., "Invoice," "Credit Note")
 * Supplier's Name and Address
 * Supplier's Tax Number/VAT Identification Number
 * Invoice Number (Unique and Sequential)
 * Invoice Date
 * Recipient's Name and Billing Address
 * Date of Delivery of Goods or Services (if different from invoice date)
 * Description of Goods or Services
 * Quantity of Goods or Services
 * Unit Price (Net)
 * Net Amount (Quantity x Unit Price)
 * VAT Rate(s) Applied
 * VAT Amount(s)
 * Total Gross Amount (Including VAT)

2. **Additional Information (If Applicable):**
 * Discounts and Price Reductions
 * Related Prepayments
 * Exchange Rate (if invoice is in a foreign currency)
 * Reason for VAT Exemption or Zero Rate (if applicable)
 * Indication of Reverse Charge Procedure (if applicable, e.g., for intra-Community supply)

3. **Processing Information (Potentially Required by the Buyer):**
 * Purchase Order (PO) Number
 * Line Item Number (within the PO)
 * Contact Person for PO-related Queries
 * Payment Information (Supplier's Bank Details)

**Important Considerations and Recommendations:**

* **Consult Official NAV Documentation:** The information provided is a summary. It is crucial to consult the official documentation provided by the NAV (Nemzeti Adó és Vámhivatal) for the most up-to-date and accurate requirements, including the specific XML schema and any changes to thresholds or reporting obligations.
* **Verify B2C Reporting Requirements:** Confirm whether B2C transactions are now subject to mandatory real-time reporting.
* **Software and Service Providers:** Consider using e-invoicing software or service providers that are compliant with Hungarian regulations. Companies like EDITEL and INFINITE IT SOLUTIONS are mentioned as providers.
* **XML Schema Validation:** Ensure that the XML data submitted to NAV conforms to the required schema. NAV likely provides tools for validating the XML before submission.
* **Archiving:** Implement a system for digitally archiving invoices in compliance with Hungarian regulations.
* **Stay Updated:** E-invoicing regulations can change. Stay informed about any updates or amendments to the Hungarian e-invoicing rules.

**In summary, Hungary has a robust real-time e-invoicing system. Compliance requires submitting invoice data in XML format to the NAV Online Számla platform. Businesses must carefully review the official NAV documentation to ensure they meet all requirements.**