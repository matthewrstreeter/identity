# Identity

This folder contains PowerShell scripts related to Microsoft Entra ID (formerly Azure AD) identity management tasks.

## Table of Contents

- [EnterpriseApps-GetSamlConfigs.ps1](#enterpriseapps-getsamlconfigsps1)
- [AuthMethods-AuthAppRegistrationStatus.ps1](#authmethods-authappregistrationstatusps1)

---

<h2><u>Scripts</u></h2>

### EnterpriseApps-GetSamlConfigs.ps1

Retrieves SAML configuration details for all enterprise applications configured for SAML single sign-on (SSO) in Microsoft Entra ID. The script collects information such as display name, app ID, login/logout URLs, reply URLs, and token signing key validity, then exports the data to a CSV file.

**Prerequisites:**
- Microsoft.Graph.Applications module
- Microsoft.Graph.Beta.Applications module
- Microsoft.Graph.Identity.SignIns module
- Appropriate permissions: Application.Read.All

**Usage:**
- Run the script to generate a CSV file in the `.\Temp\` directory with a timestamped filename.

---

### AuthMethods-AuthAppRegistrationStatus.ps1

Checks the registration status of the Microsoft Authenticator app as an authentication method for members of a specified security group. The script retrieves user details, manager information, and authentication method status, then exports the results to a CSV file.

**Prerequisites:**
- Microsoft.Graph.Groups module
- Microsoft.Graph.Users.Authentication module
- Appropriate permissions: Group.Read.All, User.Read.All, UserAuthenticationMethod.Read.All, AuditLog.Read.All

**Parameters:**
- `GroupName`: The display name of the security group to check.
- `OutputCsvPath`: The path where the CSV output should be saved.

**Usage:**
- Run the script with the required parameters to generate a report on authenticator registration status.
