# AC-2 Implementation Plan

## 1. Document Control

- **Title:** AC-2 Account Management Implementation Plan
- **System Name:** [Target IDM System]
- **Version:** [Version Number]
- **Date:** [Date]
- **Prepared by:** [Author/Team/AI Agent]
- **Approval:** [Approving Authority]

---

## 2. Purpose and Scope

**Purpose:**
This implementation plan defines how the organization will ensure all aspects of account management—including creation, modification, disabling, deletion, and review—are implemented in compliance with NIST SP 800-53 AC-2 and its enhancements. The plan aims to safeguard the confidentiality, integrity, and availability of information systems through effective and auditable account management procedures.

**Scope:**
This plan applies to all user and privileged accounts within the [Target IDM System] environment. It covers employees, contractors, vendors, and any user types with access to organizational information systems managed by the IDM platform.

---

## 3. References

- NIST SP 800-53 Rev 5, AC-2 Account Management
- Organization’s Account Management Policy/Procedure Documents
- [IDM System] User Manual

---

## 4. Roles and Responsibilities

| Role              | Responsibility                                                 |
|-------------------|---------------------------------------------------------------|
| System Owner      | Oversees overall IDM implementation and compliance            |
| IDM Administrator | Manages account provisioning, modification, disabling, deletion|
| Security Officer  | Conducts periodic account reviews and audit checks            |
| HR                | Notifies IDM Admin about user onboarding/offboarding events   |
| End Users         | Adhere to account use and security policies                   |

---

## 5. AC-2 Control Objective and Enhancements

The AC-2 control ensures that only authorized users have access to organizational systems through effective account management processes. The objective is to mitigate unauthorized access risks by enforcing controls around the account lifecycle, including timely creation, modification, disabling, and removal of accounts.

**Applicable Enhancements:**
- AC-2(1): Automated system account management
- AC-2(2): Removal of temporary and emergency accounts
- AC-2(3): Disable accounts after defined periods of inactivity
- AC-2(4): Automated audit actions
- AC-2(5): Notifications of account changes
- AC-2(6)-(13): [List other enhancements as applicable to your environment]

---

## 6. Implementation Approach

The organization will meet AC-2 requirements by:
- Integrating IDM processes with HR onboarding/offboarding notifications.
- Automating account provisioning and deprovisioning workflows using [Target IDM System] capabilities.
- Conducting quarterly account reviews and leveraging audit logs for compliance.
- Utilizing role-based access controls and automated alerts for unauthorized changes.
- Maintaining documentation and evidence for all account management activities.

---

## 7. Implementation Details (Main Section)

### Account Creation
                        **Implementation Procedure:**
                        **Implementation Procedure:**

1.  **App Registration:** Register the application within Okta's Admin Console to create an app integration (Okta Developer Guide).
2.  **Workflow Selection (Optional):** Explore Okta Workflows templates for account creation automation (Okta Workflows Templates).
3.  **Authorization Code Flow (If Applicable):** Implement the Authorization Code flow if the application requires user authentication (Okta Developer Guide).
    *   Request authorization code.
    *   Handle user authentication and consent.
    *   Exchange code for tokens.
4.  **Account Creation:** Utilize Okta APIs or SDKs to programmatically create the account.
5.  **Attribute Population:** Populate required account attributes during creation.
6.  **Group Assignment (Optional):** Assign the new account to appropriate Okta groups.
7.  **Testing:** Verify successful account creation and access.

                        **Responsible Party:** IDM Administrator
                        **Evidence/Artifact:** Access Request Form, Okta audit log
                        **Frequency:** Per request

                        ---
                        ### Account Modification
                        **Implementation Procedure:**
                        **Implementation Procedure:**

1.  **Initiate Account Modification:** Trigger account modification via the Okta API using SCIM 2.0 protocol (see: [SCIM 2.0 Protocol Reference](https://developer.okta.com/docs/api/openapi/okta-scim/guides/scim-20/)).
2.  **Identify Target Account:** Use the unique user ID to specify the account to be modified.
3.  **Define Modifications:** Construct a SCIM PATCH request containing the attributes to be changed (e.g., `userName`, `emails`, `active`).
4.  **Execute Modification:** Send the PATCH request to the `/Users/{id}` endpoint.
5.  **Verify Modification:** Confirm successful modification by checking the HTTP response code (200 OK) and verifying the updated account details via a GET request to the same endpoint.
6.  **Audit Logging:** Record all account modifications, including the user ID, attributes changed, timestamp, and initiating administrator.

                        **Responsible Party:** IDM Administrator
                        **Evidence/Artifact:** Change Request Form, Okta audit log
                        **Frequency:** Per request

                        ---
                        ### Account Disabling
                        **Implementation Procedure:**
                        **Implementation Procedure:**

1.  **Initiate Account Disabling:** Trigger account disabling via the IDM system based on defined criteria (e.g., termination date, inactivity).
2.  **Okta API Call:** Utilize the Okta Users API to deactivate the user account. Refer to the Okta Developer documentation for the specific API endpoint and request parameters for deactivation.
3.  **Status Verification:** Confirm successful deactivation through the Okta API response.
4.  **Logging:** Record the deactivation event in the IDM system's audit log, including timestamp, user ID, and disabling reason.
5.  **Notification (Optional):** Send a notification to relevant parties (e.g., user's manager, help desk) regarding the account deactivation.

                        **Responsible Party:** HR/IDM Administrator
                        **Evidence/Artifact:** HR notification, Okta audit log
                        **Frequency:** Per event

                        ---
                        ### Account Deletion
                        **Implementation Procedure:**
                        **Implementation Procedure:**

1.  **Initiate Account Deletion:** Trigger account deletion via the IDM system's user interface or API.
2.  **Okta Account Deletion:** The IDM system will call the Okta API to deactivate and then delete the user account.
3.  **Event Logging:** Okta generates system log events related to account deletion. (See: Event Types | Okta Developer for event types).
4.  **Policy Enforcement:** Okta account management policies are enforced during deactivation/deletion. (See: Edit the Okta Account Management Policy | Okta Identity Engine).
5.  **Verification:** Verify account deletion in Okta Admin Console.

                        **Responsible Party:** IDM Administrator
                        **Evidence/Artifact:** Deletion report, Okta audit log
                        **Frequency:** Per schedule

                        ---
                        ### Account Review
                        **Implementation Procedure:**
                        Regularly review user accounts and access privileges (e.g., quarterly) to ensure alignment with current roles and responsibilities. Revoke or modify access as needed. Document the review process and findings for audit purposes. See "Cloud Identity and Access Management: Security transformed | Okta" for general IAM best practices.

                        **Responsible Party:** Security Officer
                        **Evidence/Artifact:** Review report, Okta user listing
                        **Frequency:** Quarterly

                        ---
                        ### Temporary/Emergency Accounts
                        **Implementation Procedure:**
                        **Implementation Procedure:**

1.  **Request:** Initiate temporary/emergency account requests via [defined channel - e.g., help desk ticket, form].
2.  **Approval:** Obtain approval from [designated authority - e.g., manager, security officer] based on pre-defined criteria.
3.  **Account Creation:** Create the account in IDM with a temporary designation and strong, unique password.
4.  **Access Granting:** Grant only the minimum necessary privileges required for the specific task.
5.  **Monitoring:** Monitor account activity for any anomalies.
6.  **Expiration:** Enforce automatic account expiration after a pre-defined period (e.g., 24-72 hours).
7.  **Revocation:** Upon expiration or completion of the task, immediately revoke access and disable the account.
8.  **Audit:** Log all account creation, modification, and deletion activities for auditing purposes.

                        **Responsible Party:** IDM Administrator
                        **Evidence/Artifact:** Temporary account log
                        **Frequency:** As needed

                        ---
                        ### Automated/Manual Controls
                        **Implementation Procedure:**
                        Implementation Procedure:

1.  **Identify Controls:** Define specific account management controls to be automated or manually enforced within Okta.
2.  **Automate Where Possible:** Implement automated controls using Okta Workflows or similar automation tools for tasks like provisioning/de-provisioning, password resets, and group assignments.
3.  **Document Manual Procedures:** Create detailed, step-by-step documentation for manual controls, including approval workflows and escalation paths.
4.  **Testing:** Rigorously test both automated and manual controls to ensure effectiveness and prevent unintended consequences.
5.  **Training:** Train relevant personnel on both automated system usage and manual control procedures.
6.  **Monitoring & Audit:** Implement monitoring to track the effectiveness of controls and conduct regular audits to ensure compliance.

                        **Responsible Party:** IDM Administrator
                        **Evidence/Artifact:** System config, workflow logs
                        **Frequency:** Ongoing

                        ---
                        ### Notification Procedures
                        **Implementation Procedure:**
                        Configure Okta to send email/SMS notifications for key account management events (e.g., account creation, password reset, MFA enrollment). Customize notification content and triggers based on organizational policy. See Okta User Manual, section on "Event Hooks" for configuration details.

                        **Responsible Party:** IDM Administrator/HR
                        **Evidence/Artifact:** Email notifications, audit logs
                        **Frequency:** Per event

                        ---
                        
---

## 8. Dependencies and Pre-requisites

- Integration with HR systems for onboarding and offboarding events
- Dependency on Active Directory/LDAP directory services
- Up-to-date organizational policies for account management
- Existing audit and logging infrastructure

---

## 9. Testing and Validation

- Periodic review and validation of account management procedures through internal audits
- Verification of automated account disabling and deletion via test cases
- Review of audit logs and account change reports
- Quarterly access recertification and privilege review

---

## 10. Documentation and Evidence Collection

- Artifacts produced: access request forms, change tickets, approval emails, audit logs, review reports
- Evidence is stored in the IDM system, associated ticketing systems, and secure network shares
- All evidence is retained per organizational policy for compliance assessment and audits

---

## 11. Issues and Risk Management

- Potential gaps in IDM system integration with HR or directory services
- Risk of manual errors in provisioning or deprovisioning
- Delays in notification of account status changes
- Mitigation: automated workflows, regular training, periodic audits, and escalation procedures

---

## 12. Schedule/Timeline

| Milestone                          | Target Date   |
|-------------------------------------|---------------|
| Implementation Plan Finalization    | [Date]        |
| IDM System Integration Completed    | [Date]        |
| Staff Training Conducted            | [Date]        |
| Initial Account Review              | [Date]        |
| Ongoing Monitoring and Reporting    | Ongoing       |

---

## 13. Approval and Revision History

| Date       | Version  | Description                   | Approved By      |
|------------|----------|-------------------------------|------------------|
| [Date]     | 1.0      | Initial Implementation Plan   | [Name/Position]  |
| [Date]     | 1.1      | Minor updates                 | [Name/Position]  |

---
