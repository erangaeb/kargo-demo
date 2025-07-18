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

1.  **App Registration:** Register the application within Okta as an app integration, selecting OIDC - OpenID Connect as the sign-in method. Save the generated Client ID and Client secret. (See: Implement Authorization by Grant Type | Okta Developer)
2.  **Workflow Automation (Optional):** Leverage Okta Workflows templates for automated account creation tasks, such as assigning group memberships or sending welcome emails. (See: Available Workflows Templates | Okta Workflows)
3.  **API or SDK Integration:** Utilize Okta's APIs or SDKs to programmatically create accounts, following the recommended OAuth 2.0 helper methods. (See: Implement Authorization by Grant Type | Okta Developer)

                        **Responsible Party:** IDM Administrator
                        **Evidence/Artifact:** Access Request Form, Okta audit log
                        **Frequency:** Per request

                        ---
                        ### Account Modification
                        **Implementation Procedure:**
                        **Implementation Procedure:**

1.  **Initiate Modification:** Trigger account modification via the IDM system's user interface or API (refer to User Manual Section on Account Management).
2.  **Authentication & Authorization:** System verifies the requestor's identity and permissions to modify the specified account.
3.  **Attribute Update:** Modify the account attributes (e.g., username, email, group memberships) as per the request.
4.  **System Synchronization:** Propagate changes to all connected systems and applications.
5.  **Auditing:** Log all modification details, including the requestor, timestamp, and modified attributes (refer to User Manual Section on Audit Logging).
6.  **Confirmation:** Provide confirmation of successful modification to the requestor.

                        **Responsible Party:** IDM Administrator
                        **Evidence/Artifact:** Change Request Form, Okta audit log
                        **Frequency:** Per request

                        ---
                        ### Account Disabling
                        **Implementation Procedure:**
                        **Implementation Procedure:**

1.  **Initiate Account Disabling:** Trigger account disabling via the IDM system's user interface or API.
2.  **Deactivate User:** Utilize the Okta Users API to deactivate the user account. (Okta Developer: Users API - Lifecycle Operations).
3.  **Suspend User (Optional):** Optionally suspend the user account for temporary disabling. (Okta Developer: Users API - Lifecycle Operations).
4.  **Log Activity:** Record the account disabling event with relevant details (timestamp, user ID, administrator ID) in the audit logs.
5.  **Notify User (Optional):** Send a notification to the user (if appropriate) regarding the account disabling.
6.  **Test:** Verify the account is disabled by attempting to log in.

                        **Responsible Party:** HR/IDM Administrator
                        **Evidence/Artifact:** HR notification, Okta audit log
                        **Frequency:** Per event

                        ---
                        ### Account Deletion
                        **Implementation Procedure:**
                        1.  **Deactivate Account:** Upon receiving a deletion request, immediately deactivate the user account within the IDM system. This prevents further access while preserving the account data for a defined period. See "Edit the Okta Account Management Policy" for deactivation procedures.
2.  **Data Retention Period:** Maintain a defined data retention period (e.g., 30 days) after deactivation before permanent deletion. This allows for potential account recovery or data retrieval if needed.
3.  **Permanent Deletion:** After the retention period, permanently delete the account and associated data from the IDM system. Ensure this process complies with data privacy regulations.
4.  **Audit Logging:** Log all account deletion activities, including the user ID, timestamp, and administrator who initiated the deletion. Reference "Event Types" for available event types to log.
5.  **Rule Deletion:** Delete any deactivated rules by navigating to `Actions > Delete` within the Okta account management policy (see "Edit the Okta Account Management Policy").

                        **Responsible Party:** IDM Administrator
                        **Evidence/Artifact:** Deletion report, Okta audit log
                        **Frequency:** Per schedule

                        ---
                        ### Account Review
                        **Implementation Procedure:**
                        *   **Automated Review Scheduling:** Schedule regular, automated account reviews based on role, access level, or last review date.
*   **Reviewer Assignment:** Assign account reviews to designated personnel (e.g., manager, security team) based on defined criteria.
*   **Review Process:** Review user access rights, permissions, and group memberships against current job responsibilities and security policies.
*   **Documentation:** Document the review process, findings, and any remediation actions taken.
*   **Integration with HR System:** Integrate with HR systems to trigger account reviews upon job changes, promotions, or terminations (see Cloud Identity and Access Management documentation on integration with HR systems).
*   **Remediation:** Implement a process for addressing discrepancies identified during the review, including access revocation, permission adjustments, and account termination.
*   **Audit Trail:** Maintain an audit trail of all account reviews, including reviewer, review date, findings, and remediation actions.

                        **Responsible Party:** Security Officer
                        **Evidence/Artifact:** Review report, Okta user listing
                        **Frequency:** Quarterly

                        ---
                        ### Temporary/Emergency Accounts
                        **Implementation Procedure:**
                        **Implementation Procedure:**

1.  **Account Creation:** Create temporary/emergency accounts using the IDM system's standard account creation process, ensuring to set a clear expiration date (refer to User Manual Section on Account Creation).
2.  **Privilege Assignment:** Assign only the minimum necessary privileges required for the specific emergency task. Document the justification for these privileges.
3.  **Monitoring:** Implement enhanced monitoring on temporary/emergency accounts.
4.  **Expiration Enforcement:** Ensure the IDM system automatically disables/removes the account upon expiration.
5.  **Auditing:** Log all actions performed by the temporary/emergency account for audit purposes (refer to User Manual Section on Audit Logging).

                        **Responsible Party:** IDM Administrator
                        **Evidence/Artifact:** Temporary account log
                        **Frequency:** As needed

                        ---
                        ### Automated/Manual Controls
                        **Implementation Procedure:**
                        1.  **Automated Provisioning/Deprovisioning:** Implement automated workflows for provisioning and deprovisioning user accounts and service accounts based on defined roles and policies. (See Okta Implementation Steps, Zluri Automated Provisioning and Deprovisioning)
2.  **Role-Based Access Control (RBAC):** Define and enforce RBAC policies to grant users and service accounts the minimum necessary privileges required to perform their tasks. (See Zluri Role-Based Access Control)
3.  **Password Management:** Implement automated password rotation and management for service accounts. (See Zluri Password Rotation and Management)
4.  **Auditing and Monitoring:** Enable comprehensive auditing and monitoring of all user and service account activities. (See Okta Auditing and Compliance, Zluri Audit Trails and Reporting)
5.  **Integration with Identity Providers:** Integrate the IDM system with existing identity providers (e.g., Active Directory, Okta) to centralize identity management. (See ManageEngine, Okta Identity Cloud)
6.  **Regular Review and Updates:** Conduct regular reviews of access rights and policies to ensure they remain aligned with business needs and security requirements.
7.  **Documentation:** Document all implementation procedures, configurations, and policies related to automated/manual controls.

                        **Responsible Party:** IDM Administrator
                        **Evidence/Artifact:** System config, workflow logs
                        **Frequency:** Ongoing

                        ---
                        ### Notification Procedures
                        **Implementation Procedure:**
                        Configure event hooks to trigger notifications for critical IDM events (e.g., account creation, modification, deletion). Ensure notifications are sent to relevant personnel (e.g., security team, system administrators) via email or other communication channels. See Okta Developer - Event Hooks Concepts for details on setting up event hooks. Configure Okta Verify for MFA enrollment policies (Configure Okta Verify | Okta Classic Engine).

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
