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

1.  Register the application in Okta as an app integration, selecting OIDC - OpenID Connect as the sign-in method. Save the generated Client ID and Client secret.
2.  Redirect the user to the authorization server's `/authorize` endpoint to request an authorization code.
3.  Upon receiving the authorization code, exchange it for tokens by passing the code and client secret to the authorization server's `/token` endpoint.
4.  Leverage Okta Workflows templates for account creation automation, such as sending a welcome email or activating/deactivating Okta accounts.
5.  Utilize Okta SDKs and OAuth 2.0 helper methods for implementation.

                        **Responsible Party:** IDM Administrator
                        **Evidence/Artifact:** Access Request Form, Okta audit log
                        **Frequency:** Per request

                        ---
                        ### Account Modification
                        **Implementation Procedure:**
                        **Implementation Procedure:**

1.  Modify user attributes in the IDM system.
2.  The system will then update the corresponding attributes in the target SCIM application using a PUT or PATCH request (SCIM 2.0 Protocol Reference). PUT is used for full updates, while PATCH is used for partial updates (e.g., activating/deactivating users or syncing passwords).
3.  Verify the successful modification by retrieving the user object from the SCIM server using a GET request.

                        **Responsible Party:** IDM Administrator
                        **Evidence/Artifact:** Change Request Form, Okta audit log
                        **Frequency:** Per request

                        ---
                        ### Account Disabling
                        **Implementation Procedure:**
                        Disable accounts using the "Deactivate User" operation in the User Lifecycle API (see [Deactivate a User](https://developer.okta.com/docs/reference/api/users/#deactivate-user)). This action suspends the user's access.

                        **Responsible Party:** HR/IDM Administrator
                        **Evidence/Artifact:** HR notification, Okta audit log
                        **Frequency:** Per event

                        ---
                        ### Account Deletion
                        **Implementation Procedure:**
                        **Implementation Procedure:**

1.  Deactivate the user account in Okta. See "Edit the Okta account management policy" for instructions on deactivating rules.
2.  Delete the deactivated rule. See "Edit the Okta account management policy" for instructions on deleting deactivated rules.
3.  Monitor the System Log API for `user.lifecycle.delete` event types to confirm successful deletion. See "Event Types" for event type details.

                        **Responsible Party:** IDM Administrator
                        **Evidence/Artifact:** Deletion report, Okta audit log
                        **Frequency:** Per schedule

                        ---
                        ### Account Review
                        **Implementation Procedure:**
                        **Implementation Procedure:**

1.  **Define Review Scope:** Identify user populations and applications subject to review based on risk and compliance requirements.
2.  **Establish Review Frequency:** Determine review cycles (e.g., quarterly, annually) based on user roles and data sensitivity.
3.  **Implement Automated Review Tools:** Utilize IDM system features (if available) or integrate with existing tools to automate user access reviews.
4.  **Configure Reviewer Roles:** Assign appropriate personnel (e.g., managers, application owners) as reviewers.
5.  **Develop Review Process:** Define clear steps for reviewers to validate user access, including justification requirements and escalation procedures.
6.  **Document Review Results:** Record review decisions, justifications, and any access modifications made.
7.  **Remediate Access Discrepancies:** Revoke or modify access based on review findings, ensuring timely resolution of unauthorized access.
8.  **Audit Review Process:** Regularly audit the account review process to ensure effectiveness and compliance.

                        **Responsible Party:** Security Officer
                        **Evidence/Artifact:** Review report, Okta user listing
                        **Frequency:** Quarterly

                        ---
                        ### Temporary/Emergency Accounts
                        **Implementation Procedure:**
                        **Implementation Procedure:**

1.  **Account Creation:** Create temporary/emergency accounts using the IDM system's standard account creation process, ensuring to set a clear expiration date (refer to User Manual Section on Account Creation).
2.  **Privilege Assignment:** Assign only the minimum necessary privileges required for the specific emergency or temporary task. Document the justification for these privileges.
3.  **Monitoring:** Implement enhanced monitoring for all temporary/emergency accounts.
4.  **Expiration Enforcement:** Ensure the IDM system automatically disables/removes the account upon expiration.
5.  **Post-Use Review:** Upon account expiration, conduct a review of the account's activity and access logs.

                        **Responsible Party:** IDM Administrator
                        **Evidence/Artifact:** Temporary account log
                        **Frequency:** As needed

                        ---
                        ### Automated/Manual Controls
                        **Implementation Procedure:**
                        **Implementation Procedure:**

1.  **Automated Controls:** Leverage automated provisioning and de-provisioning features within the IDM system (e.g., Okta Identity Cloud, Active Directory Pro) to manage user accounts and access rights.
2.  **Manual Controls:** Implement manual review processes for access requests that fall outside of automated workflows or require special approvals.
3.  **RBAC Implementation:** Define and enforce Role-Based Access Control (RBAC) policies to grant users appropriate permissions based on their roles and responsibilities.
4.  **Integration:** Integrate the IDM system with HR systems and other relevant IT infrastructure to automate user lifecycle management.
5.  **Auditing:** Enable comprehensive auditing and logging of all account actions within the IDM system to maintain an audit trail for compliance purposes.
6.  **Regular Audits:** Conduct regular audits of user access rights and system configurations to ensure compliance with security policies and regulatory requirements.
7.  **Documentation:** Document all implementation procedures, configurations, and policies related to automated and manual controls within the IDM system.

                        **Responsible Party:** IDM Administrator
                        **Evidence/Artifact:** System config, workflow logs
                        **Frequency:** Ongoing

                        ---
                        ### Notification Procedures
                        **Implementation Procedure:**
                        Implementation Procedure:

1.  Configure Okta Event Hooks to trigger notifications for relevant account management events (e.g., account creation, modification, deletion). See Okta Developer documentation on Event Hooks.
2.  Implement a secure web service with an internet-accessible endpoint to receive and process event hook calls from Okta.
3.  Register and verify the endpoint with Okta, configuring appropriate filters to minimize unnecessary calls.
4.  Utilize HTTPS and header-based authentication for secure communication between Okta and the web service.
5.  For user-facing notifications, enable and configure Okta Verify with push notifications (Security > Multifactor in the Admin Console).
6.  Guide users through Okta Verify setup upon initial sign-in.
7.  Monitor the Okta System Log for debugging and troubleshooting event hook issues.

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
