# IA-5 Implementation Plan — Authenticator Management

## 1. Document Control
- **Title:** IA-5 Authenticator Management Implementation Plan
- **System Name:** [Red Hat IdM (FreeIPA)]
- **Version:** [Version Number]
- **Date:** [Date]
- **Prepared by:** [Author/Team/AI Agent]
- **Approval:** [Approving Authority]

---

## 2. Purpose and Scope
**Purpose:**
Define how the organization configures and operates authenticator management in line with **NIST SP 800-53 Rev. 5, IA-5**. This plan operationalizes password policies, MFA, credential issuance/reset, service account rotation, and audit logging for [Red Hat IdM (FreeIPA)].

**Scope:**
All human and service accounts managed by [Red Hat IdM (FreeIPA)] including administrators, remote users, and users of external-facing apps integrated with the IdM.

---

## 3. References
- NIST SP 800-53 Rev. 5 — IA-5 Authenticator Management
- CIS Password Policy Recommendations
- Organization’s Credential/Authenticator Policy & SOPs
- [Red Hat IdM (FreeIPA)] Admin Guides

---

## 4. Roles and Responsibilities

| Role                     | Responsibility                                                                 |
|--------------------------|---------------------------------------------------------------------------------|
| System Owner             | Accepts risk, approves policy & changes                                         |
| IdM Administrator        | Implements IA-5 settings, manages issuance/resets, integrates MFA               |
| Security Officer         | Oversees compliance, reviews monthly logs, coordinates audits                   |
| Help Desk / Service Desk | Executes controlled resets, identity proofing, tracks tickets                   |
| Application Owners       | Ensure app integrations inherit IdM/MFA policies                                |
| HR                       | Triggers joiner/mover/leaver events affecting authenticators                   |

---

## 5. IA-5 Objective and Enhancements (Summary)
Ensure authenticators are securely issued, protected, rotated, and revoked. Apply strong password policy, integrate MFA (esp. for admin/remote/external access), enforce initial resets, protect service account secrets (e.g., vault), and maintain auditable records.

**Key focus areas:**
- Strong password rules (CIS aligned) — **≥14 chars without MFA**; **≥8 chars with MFA**
- MFA for admin, remote access, and external-facing applications (e.g., FreeIPA OTP or Duo)
- Initial credential reset on first use
- Documented issuance workflows (in-person onsite; encrypted remote)
- Regular rotation of service account credentials (vaulting if available)
- **Monthly** review and retention of authenticator logs

---

## 6. Implementation Approach (High-Level)
- Enforce password complexity and length per CIS and MFA context.
- Integrate [Red Hat IdM (FreeIPA)] with FreeIPA OTP or Duo for admin, remote, and external app access.
- Require password reset on first login / issuance.
- Formalize identity proofing & issuance channels (in-person onsite; encrypted remote).
- Rotate service account credentials periodically; store in a vault (e.g., HashiCorp Vault).
- Centralize authenticator change logs; review **Monthly**; retain per policy.
- Maintain SOPs and evidence for audits.

---

## 7. Implementation Details (Main Section)

### Password Policy Enforcement

**Implementation Procedure:**
**IA-5 Authenticator Management: Password Policy Enforcement Implementation**

1.  **Define Password Policy:** Using FreeIPA's `ipa pwpolicy-mod` command, set a default password policy requiring a minimum length of 14 characters for users without MFA and 8 characters for users with MFA enabled. (Ref: User Manual - Password Policy Management).
2.  **Enable MFA Enforcement:** Configure FreeIPA to require MFA for administrative users, remote access, and external applications. Integrate with Duo or similar MFA provider using FreeIPA's plugin framework. (Ref: User Manual - MFA Configuration).
3.  **Implement First-Login Password Reset:** Enforce password reset upon initial login for all new user accounts. This is typically a default setting but verify within FreeIPA configuration.
4.  **Configure Password History:** Use `ipa pwpolicy-mod` to prevent password reuse by storing password history.
5.  **Service Account Rotation:** Implement automated password rotation for service accounts using a vault (e.g., HashiCorp Vault) and FreeIPA's API.
6.  **Monthly Authenticator Review:** Schedule monthly reviews of user authenticators (passwords, MFA devices) to identify and remediate any anomalies or outdated configurations. Document review process.
7.  **Issuance Proofing:** Implement strong identity proofing procedures during account creation (onsite verification preferred; encrypted remote verification as alternative). Document proofing method.
8.  **SSSD Configuration:** Ensure SSSD is configured on client machines to properly enforce the FreeIPA password policies. Verify `ldap_pwd_policy` is enabled in `sssd.conf`.

**Responsible Party:** IdM Administrator
**Evidence/Artifact:** IdM password policy export, config screenshots
**Frequency:** Ongoing

---
### MFA Integration (Admin Access)

**Implementation Procedure:**
**IA-5 Authenticator Management Implementation Plan Entry: MFA Integration (Admin Access) - Implementation Procedure**

1.  **Enable MFA for Admin Users:** Configure FreeIPA to require MFA for all users with administrative privileges (e.g., those in the `ipaadmins` group). Use `ipa user-mod --mfa_enabled=TRUE <username>` for individual users or implement an authentication indicator policy. (User Manual: Authentication Indicators)
2.  **Choose MFA Method:** Select a supported MFA method (e.g., FreeIPA OTP, Duo Security via FreeIPA integration). Evaluate options based on organizational issuance proofing standards (onsite preferred, encrypted remote acceptable). (User Manual: MFA Configuration)
3.  **Configure MFA Provider:** Integrate the chosen MFA provider with FreeIPA. For Duo, follow the official Duo FreeIPA integration guide. (User Manual: External Authentication)
4.  **Enforce Password Policy:** Ensure the password policy meets organizational requirements (≥8 characters with MFA enabled). Use `ipa pwpolicy-mod` to adjust password complexity and length. (User Manual: Password Policies)
5.  **Implement First-Login Reset:** Enforce password reset on first login for new admin accounts. This is typically a default FreeIPA setting but verify using `ipa config-show`. (User Manual: Account Lifecycle)
6.  **Service Account Rotation:** Rotate service account passwords regularly using a vault (e.g., HashiCorp Vault) and automate updates to FreeIPA using the FreeIPA API or command-line tools. (User Manual: Service Account Management)
7.  **Monthly Authenticator Review:** Implement a process for monthly review of enrolled authenticators. This can be a manual review of FreeIPA user attributes or automated reporting. (User Manual: Reporting and Auditing)
8.  **Test MFA:** Thoroughly test MFA functionality for admin users in a staging environment before deploying to production.

**Responsible Party:** IdM Administrator / Security Officer
**Evidence/Artifact:** MFA policy config, enrollment logs
**Frequency:** Ongoing

---
### MFA Integration (Remote Access)

**Implementation Procedure:**
**IA-5 Authenticator Management: MFA Integration (Remote Access) - Implementation Procedure**

1.  **Enable MFA:** Configure FreeIPA to require MFA for remote access logins. Leverage FreeIPA's HBAC rules to enforce MFA based on user groups or host access policies.
2.  **Duo Integration:** Integrate FreeIPA with Duo Security (or similar MFA provider) using the FreeIPA's PAM integration capabilities. Configure PAM modules to enforce Duo authentication for SSH and other remote access services.
3.  **Password Policy Update:** Modify the FreeIPA password policy to enforce a minimum password length of 8 characters when MFA is enabled, and 14 characters when MFA is not enabled. Implement first-login password reset.
4.  **Admin MFA Enforcement:** Create a specific HBAC rule requiring MFA for all members of the `admins` group when accessing systems remotely.
5.  **Authenticator Enrollment:** Implement a secure authenticator enrollment process. Prioritize onsite enrollment with issuance proofing. For remote enrollment, ensure encrypted communication channels are used.
6.  **Service Account Rotation:** Rotate service account passwords monthly using a vault (e.g., HashiCorp Vault) and integrate with FreeIPA for automated password updates.
7.  **Monthly Review:** Schedule a monthly review of user authenticators to identify and remediate any potential issues (e.g., inactive tokens, unauthorized enrollments).

**Responsible Party:** IdM Administrator / Network Security
**Evidence/Artifact:** VPN/SSO policy with MFA, access logs
**Frequency:** Ongoing

---
### MFA Integration (External-Facing Apps)

**Implementation Procedure:**
1.  **Enable MFA:** Configure FreeIPA to require MFA for external-facing applications using the `ipa service-mod` command and defining a service-specific authentication indicator.
2.  **Authenticator Enrollment:** Enforce first-login password reset. Implement issuance proofing based on risk (onsite preferred, encrypted remote acceptable).
3.  **Password Policy:** Set password policy: ≥14 characters without MFA, ≥8 characters with MFA (using FreeIPA password policy).
4.  **Duo Integration (Example):** Integrate FreeIPA with Duo Security (or similar) for MFA using FreeIPA's external authentication mechanism. Refer to Red Hat documentation for Duo integration steps.
5.  **Service Account Rotation:** Rotate service account passwords monthly using a vault (e.g., HashiCorp Vault) and automate with Ansible.
6.  **Authenticator Review:** Conduct monthly reviews of enrolled authenticators and disable inactive/compromised authenticators.
7.  **SSSD Configuration:** Configure SSSD on client systems to enforce MFA policies defined in FreeIPA.

**Responsible Party:** Application Owner / IdM Administrator
**Evidence/Artifact:** SP/OIDC configs, MFA enforcement tests
**Frequency:** Ongoing

---
### Initial Credential Reset on First Login

**Implementation Procedure:**
**IA-5 Authenticator Management: Initial Credential Reset on First Login - Implementation Procedure**

1.  **Enable Password Expiration:** Configure the FreeIPA password policy to force password change on first login. Use `ipa pwpolicy-mod --pwdmaxlife=unlimited --pwdmustchange=TRUE` (User Manual Section: Password Policies).
2.  **Communicate Password Complexity Requirements:** Inform new users of password complexity requirements (≥14 characters without MFA, ≥8 characters with MFA) during account provisioning.
3.  **Issue Initial Credentials Securely:** Provide initial credentials through a secure channel (onsite issuance or encrypted communication) to ensure proofing.
4.  **Test First Login Reset:** Verify that users are prompted to change their password upon initial login.

**Responsible Party:** Help Desk / IdM Administrator
**Evidence/Artifact:** First-login reset flags, tickets
**Frequency:** Per issuance

---
### Credential Issuance Workflow (Onsite & Remote)

**Implementation Procedure:**
**IA-5 Authenticator Management: Credential Issuance Workflow (Onsite & Remote) - Implementation Procedure**

1.  **Initial Password Policy:** Enforce a minimum password length of 14 characters (without MFA) or 8 characters (with MFA) via `ipa pwpolicy-mod`. Mandate first-login password reset.
2.  **Onsite Credential Issuance:** Verify user identity in person. Issue temporary credentials. Guide user through first login and password change.
3.  **Remote Credential Issuance:** Utilize encrypted channels (e.g., secure email with one-time password delivered via separate channel) for temporary credential delivery. Require immediate password change upon first login.
4.  **MFA Enrollment:** Mandate MFA enrollment (e.g., Duo Security integration) for all remote access, administrative accounts, and external applications. Configure via FreeIPA's OTP policies.
5.  **Service Account Management:** Implement automated password rotation for service accounts using a vault (e.g., HashiCorp Vault).
6.  **Periodic Review:** Conduct monthly authenticator reviews to identify and disable inactive or compromised accounts.
7.  **SSSD Configuration:** Ensure SSSD is properly configured on client machines to authenticate against FreeIPA. Refer to Red Hat documentation for SSSD configuration details.

**Responsible Party:** Help Desk / HR / IdM Administrator
**Evidence/Artifact:** Identity proofing records, issuance tickets
**Frequency:** Per issuance

---
### Service Account Credential Rotation & Vaulting

**Implementation Procedure:**
1.  **Vault Selection:** Choose a supported vault (e.g., HashiCorp Vault) for storing service account credentials.
2.  **Credential Generation:** Generate strong, unique passwords (≥14 chars without MFA, ≥8 chars with MFA if applicable) for each service account.
3.  **Vault Storage:** Store the generated credentials securely within the chosen vault, associating them with the respective service accounts.
4.  **Service Configuration:** Configure services to retrieve credentials from the vault instead of storing them locally.
5.  **Rotation Policy:** Implement a password rotation policy for service accounts. Automate rotation using vault features and IdM tools.
6.  **Testing:** Thoroughly test service functionality after each credential rotation to ensure proper operation.
7.  **Monitoring:** Implement monitoring to detect failed authentication attempts or other anomalies related to service accounts.
8.  **Documentation:** Document the entire process, including vault configuration, service integration, and rotation procedures.
9.  **Monthly Review:** Conduct monthly reviews of service account authenticators and access privileges.

**Responsible Party:** IdM Administrator / App Owner
**Evidence/Artifact:** Vault logs, rotation runbooks, change tickets
**Frequency:** Per schedule (e.g., quarterly)

---
### Authenticator Revocation / Recovery / Reset

**Implementation Procedure:**
**IA-5 Authenticator Revocation / Recovery / Reset Implementation Procedure:**

1.  **Revocation:** Immediately disable compromised user accounts in FreeIPA (`ipa user-disable <username>`). This revokes all associated Kerberos tickets and prevents authentication.
2.  **Recovery (Password Reset):**
    *   **First-Login Reset:** Enforce password reset on first login via FreeIPA password policy (see IdM documentation on password policies).
    *   **Standard Reset:** Users can initiate password reset via the FreeIPA web UI or command line (`ipa passwd`). Admins can reset passwords using `ipa user-mod --password`.
    *   **MFA Considerations:** If MFA is enabled, password reset should trigger MFA re-enrollment.
3.  **Authenticator Reset (MFA):**
    *   **Duo Integration:** If using Duo, administrators can reset Duo MFA factors for users via the Duo Admin Panel.
    *   **FreeIPA OTP:** If using FreeIPA OTP, administrators can remove and re-enroll OTP tokens for users (`ipa user-mod --otpkey`).
4.  **Post-Reset:**
    *   Require users to create new passwords adhering to complexity requirements (≥14 characters without MFA, ≥8 characters with MFA).
    *   Enforce MFA re-enrollment where applicable.
5.  **Service Accounts:** Rotate service account passwords regularly using a vault and update associated configurations.
6.  **Auditing:** Review authenticator usage and reset events monthly to identify suspicious activity.

**Responsible Party:** Help Desk / Security Officer
**Evidence/Artifact:** Revocation tickets, reset logs, approvals
**Frequency:** Per event

---
### Monthly Authenticator Review & Audit Logging

**Implementation Procedure:**
**IA-5 Authenticator Management Implementation Plan Entry**

**Activity:** Monthly Authenticator Review & Audit Logging

**Field:** Implementation Procedure

1.  **Generate Authenticator Report:** Monthly, generate a report of all user authenticators (passwords, MFA devices) using `ipa user-find --all --raw | grep "userpassword:"` and `ipa user-find --all --raw | grep "ipaotpkey:"`.
2.  **Review Password Compliance:** Identify accounts with passwords not meeting complexity requirements (≥14 chars without MFA, ≥8 chars with MFA). Use `ipa user-show <username>` to check password policy applied.
3.  **Verify MFA Enforcement:** Confirm MFA is enabled for admin accounts, remote access, and external applications. Use `ipa user-show <username>` to verify `ipaotpkey` attribute presence for required users.
4.  **Audit Service Account Rotation:** Review logs for service account password rotations performed via vault integration. Check vault logs and FreeIPA audit logs (`/var/log/httpd/error_log` or `journalctl -u ipa.service`) for rotation events.
5.  **Investigate Anomalies:** Investigate any unexpected authenticator changes or non-compliance.
6.  **Log Review Actions:** Document all review actions, findings, and remediation steps in a designated audit log.
7.  **Address Weak Authenticators:** Enforce password resets or MFA enrollment for accounts failing compliance checks. Use `ipa user-mod --password` or `ipa user-mod --otpkey` commands.
8.  **Monitor Audit Logs:** Regularly monitor FreeIPA audit logs for suspicious activity related to authenticator management.

**Responsible Party:** Security Officer
**Evidence/Artifact:** Monthly review report, SIEM exports
**Frequency:** Monthly

---

---

## 8. Dependencies and Pre-requisites
- Working [Red Hat IdM (FreeIPA)] deployment with admin privileges
- MFA integration access (e.g., FreeIPA OTP / Duo admin)
- Ticketing system for issuance/reset records
- Central logging (SIEM) and/or IdM audit trails
- (Optional) Secrets vault (e.g., HashiCorp Vault)

---

## 9. Testing and Validation
- Validate password policy enforcement (length/complexity/history).
- Test MFA enrollment, prompts, and enforcement paths (admin/remote/external).
- Verify first-login/issuance reset flows and help-desk reset SOP.
- Execute service account rotation dry-runs; confirm app continuity.
- Confirm logs contain issuance/reset/rotation records; perform **Monthly** review.

---

## 10. Documentation and Evidence Collection
- Policy/SOPs for issuance & reset, identity proofing records
- Ticketing artifacts and approval trails
- IdM audit logs, SIEM dashboards, MFA enrollment reports
- Vault rotation logs and access reviews
- Monthly authenticator review minutes and findings

---

## 11. Issues and Risk Management
- MFA enrollment friction → provide self-service enroll + fallback with strong proofing
- App breakage during svc-acct rotation → stage, pilot, back-out plans
- Insufficient logging → enable detailed IdM audit; ship to SIEM; set retention
- Drift from policy → Monthly reviews; corrective actions tracked

---

## 12. Schedule/Timeline
| Milestone                                      | Target Date |
|------------------------------------------------|-------------|
| Finalize IA-5 policies & SOPs                  | [Date]      |
| Password policy + MFA enforcement configured   | [Date]      |
| Issuance/reset workflows live                  | [Date]      |
| Service account rotation + vault onboarded     | [Date]      |
| First Monthly authenticator review completed | [Date]      |

---

## 13. Approval and Revision History
| Date   | Version | Description                         | Approved By |
|--------|---------|-------------------------------------|-------------|
| [Date] | 1.0     | Initial IA-5 Implementation Plan    | [Name]      |
| [Date] | 1.1     | Updates after pilot                 | [Name]      |

---
