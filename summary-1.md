Okay, here's a detailed summary of e-invoicing in Hungary, combining information from all the provided sources, organized for clarity and comprehensiveness:

**I. Overview**

* **Not Mandatory, but Real-Time Reporting is Key:** While e-invoicing itself isn't mandated in Hungary, *real-time invoice reporting (RTIR)* to the National Tax and Customs Administration of Hungary (NAV) is mandatory for nearly all transactions. This effectively makes electronic data transmission crucial.
* **Centralized System:** Hungary uses a centralized model where invoice data is reported live and electronically to the NAV.
* **Platform:** The primary platform is the **NAV Online Számla** (Online Invoice System).
* **Format:** The mandatory format for reporting to NAV is **XML**.
* **Governing Entity:** The **National Tax and Customs Administration of Hungary (NAV)** is the responsible authority.

**II. Legislation and Compliance**

* **Legal Basis:** Act CXXVII of 2007 on Value Added Tax allows for electronic invoices.
* **Directive 2014/55/EU:** Transposed, meaning Hungary complies with the European standard on e-invoicing.
* **Real-Time Reporting Implementation:**
 * Initially introduced on July 1, 2018, for domestic invoices exceeding 100,000 HUF (approx. 250 EUR) in VAT.
 * Expanded on April 1, 2021, to include *all* B2B and B2C transactions, regardless of amount.
 * Since January 1, 2021, almost all outgoing transactions must be reported, including cross-border and B2C sales.
* **Mandatory For:**
 * **Submitting:** All VAT-registered and resident taxpayers in Hungary, foreign companies with tax residence in Hungary, and anyone sending an invoice to domestic taxable persons for transactions in Hungary.
 * **Receiving and Processing:** Central, regional, and local contracting authorities must accept e-invoices if authenticity and integrity are guaranteed.
* **Exemptions:** Foreign distance sellers joining the OSS (One-Stop Shop) regime *may* be exempt from RTIR obligations.
* **Monitoring Mechanism:** The NAV Online Számla system validates transactions in real-time.
* **Versions:** NAV Online 3.0 was mandatory from June 1, 2021. Versions 3.17 and 3.2 introduced error validations and technical cancellations.
* **B2B Mandate:** No explicit B2B e-invoicing mandate, but the RTIR effectively requires electronic data submission.

**III. Technical Details and Process**

* **NAV Online Számla:**
 * Web portal for transmitting data in XML format.
 * Requires registration.
 * Requires creation of a "technical user" and keys to connect accounting software.
* **E-invoicing Process:**
 1. **Register:** Register on the NAV Online Számla platform.
 2. **Create Technical User:** Create a technical user and keys.
 3. **Connect ERP:** Connect your ERP (Enterprise Resource Planning) system to the NAV system using the technical user details.
 4. **Issue Invoice:** Generate the invoice from your ERP system.
 5. **Report:** The invoice data is reported to NAV in real-time in XML format.
* **XML Format:** NAV XML version 3.0 is the mandatory format for reporting via Online Számla.
* **Invoice Data Requirements:** The XML file (or e-invoice) must include:
 * Issuance date
 * Unique sequential number
 * Supplier's VAT number
 * Supplier's and customer's full names and addresses
 * Clear description of goods or services
 * Quantity of goods
 * Date of supply (if different from issuance date)
 * Total taxable value
 * VAT rate
 * Details supporting zero VAT (if applicable)
 * Gross value of the invoice
* **Digital Signature:** Not required for XML submissions to NAV. Required for PDF invoices.
* **Customer Info Field:** Adapted to differentiate between invoices sent to Hungary, EU, or non-EU countries. Only one VAT ID (Hungarian, European, or non-European) can be provided. B2C invoices must not contain personal data (neither name nor address).

**IV. Archiving**

* **Archiving Period:**
 * Standard: 5 years
 * Accounting purposes: 8 years from the issuance of the document.
* **Archiving Abroad:** Allowed under certain conditions.

**V. Penalties**

* Up to 500,000 HUF (approximately 1,280 EUR) per unreported or incorrectly reported invoice.

**VI. Preparation and Best Practices**

* **Accounting Software:** Use reliable accounting software that can generate compliant XML files.
* **E-invoicing Service Provider:** Consider partnering with a reliable e-invoicing service provider to ensure compliance.
* **NAV Registration:** Register for the NAV Online Számla system and understand its functionalities.
* **Stay Updated:** Keep abreast of any changes to the regulations and system requirements.

**VII. Other Digital Reporting Obligations**

* **EKAER (Electronic Public Road Trade Control System):** Specific data on risky goods transported by road domestically or to/from the EU must be reported electronically.

**VIII. SAF-T**

* SAF-T is not currently required but is expected to be introduced in the future.

**IX. Key Takeaways**

* While e-invoicing is technically voluntary, the mandatory real-time reporting to NAV necessitates electronic data transmission.
* Compliance with the NAV Online Számla system and the XML format is crucial.
* Staying informed about regulatory updates is essential.
* Consider using reliable accounting software or an e-invoicing service provider to ensure compliance and streamline the process.