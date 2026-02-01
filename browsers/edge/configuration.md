## Microsoft Edge Configuration for Enterprise Environments

This page provides practical guidance for configuring Microsoft Edge with Group Policies for enterprise environments. It focuses on controls that matter most for security, privacy, and productivity, with concrete policy names and example values IT teams can use as starting points.

### AI and Automation Controls

Edge includes multiple AI-powered features (Copilot, generative themes, AI-enhanced history search, smart actions) that can improve user productivity but may send content, URLs, or other signals to Microsoft services. Organizations with strict data-handling or GenAI policies often constrain these features, while others enable them selectively for Entra ID (work) profiles.

#### AI and Generative Feature Policies

These policies control AI assistants and generative experiences that operate on page content, history, or UI surfaces.

| Policy | Description | Values |
|--------|-------------|--------|
| `EdgeCopilotEnabled` | Controls whether the Copilot experience in Edge is available. | 0 = Disabled, 1 = Enabled |
| `CopilotPageContext` | Controls Copilot access to page content for Microsoft Entra ID profiles in the side pane. | 0 = No page context, 1 = Limited page context, 2 = Full page context allowed |
| `EdgeHistoryAISearchEnabled` | Controls AI-enhanced search in the History page. | 0 = Disabled, 1 = Enabled |
| `AIGenThemesEnabled` | Controls DALL-E-based AI theme generation. | 0 = Disabled, 1 = Enabled |
| `SmartActionsBlockList` | Blocks smart actions for specified services or surfaces. | String list = Service IDs or scopes to block |

#### Recommended Enterprise Configuration

Regulated or highly sensitive environments (limit AI surface, keep content local where possible):

```text
EdgeCopilotEnabled: 0
CopilotPageContext: 0
EdgeHistoryAISearchEnabled: 0
AIGenThemesEnabled: 0
SmartActionsBlockList: ["*"]
```

Knowledge-worker environments with an approved AI usage policy (Copilot for work profiles only, tightly scoped context):

```text
EdgeCopilotEnabled: 1
CopilotPageContext: 1
EdgeHistoryAISearchEnabled: 1
AIGenThemesEnabled: 0
SmartActionsBlockList: []
```

---

### Privacy and Telemetry Controls

Edge sends diagnostic data, security signals, and sometimes URL metadata to Microsoft to improve security, performance, and product quality. Tight privacy settings reduce shared data but may weaken protections (for example, SmartScreen) and reduce troubleshooting visibility. These policies help you tune that tradeoff.

#### Privacy and Telemetry Policies

| Policy | Description | Values |
|--------|-------------|--------|
| `DiagnosticData` | Controls sending required/optional diagnostic data about Edge usage. | 0 = Required data only (if applicable), 1 = Optional + required data, 2 = No diagnostic data (where allowed) |
| `MetricsReportingEnabled` | Controls sending usage statistics and crash reports. | 0 = Do not send, 1 = Send metrics and crash reports |
| `SendSiteInfoToImproveServices` | Controls sending site info to improve Microsoft services (obsolete in newer builds, but relevant in older baselines). | 0 = Disabled, 1 = Enabled |
| `UrlDiagnosticDataEnabled` | Enables URL reporting in Edge diagnostic data. | 0 = URL reporting disabled, 1 = URL reporting enabled |
| `ConfigureDoNotTrack` | Sets the Do Not Track HTTP header. | 0 = Do Not Track header not sent, 1 = Send Do Not Track header |

#### Recommended Enterprise Configuration

Privacy-focused but still leveraging core protection/reporting:

```text
DiagnosticData: 0
MetricsReportingEnabled: 0
SendSiteInfoToImproveServices: 0
UrlDiagnosticDataEnabled: 0
ConfigureDoNotTrack: 1
```

Organizations comfortable with more telemetry to support analytics and incident response:

```text
DiagnosticData: 1
MetricsReportingEnabled: 1
SendSiteInfoToImproveServices: 1
UrlDiagnosticDataEnabled: 1
ConfigureDoNotTrack: 0
```

---

### Security and Hardening Settings

Edge's security posture is influenced by SmartScreen, download restrictions, mixed-content handling, network behaviors, and features like Enhanced Security Mode. Tightening these reduces exposure to malware, phishing, and lateral movement, at the cost of occasionally breaking legacy workflows.

#### Core Security Policies

| Policy | Description | Values |
|--------|-------------|--------|
| `SmartScreenEnabled` | Enables Microsoft Defender SmartScreen for URL and download protection. | 0 = Disabled, 1 = Enabled |
| `SmartScreenPuaEnabled` | SmartScreen protection against potentially unwanted apps (PUA). | 0 = Disabled, 1 = Enabled |
| `DownloadRestrictions` | Controls which file downloads are allowed. | 0 = No extra restrictions, 1 = Block dangerous, 2 = Block potentially dangerous, 3 = Block all downloads |
| `EnhanceSecurityMode` | Controls Enhanced Security Mode (ESM) behavior. | 0 = Disabled, 1 = Balanced protection, 2 = Strict mode |
| `EnhanceSecurityModeEnforceListDomains` | Domains where ESM is always enforced. | String list = Domains with enforced ESM |
| `LocalNetworkAccessRestrictionsEnabled` | Controls blocking public-site requests to local network devices (obsolete in latest channel, but may exist in LTS/older). | 0 = Restrictions disabled, 1 = Restrictions enabled |
| `HttpsOnlyMode` | Allows enabling HTTPS-Only Mode. | 0 = Off, 1 = User can enable, 2 = Forced on |

#### Recommended Enterprise Configuration

Standard corporate environment:

```text
SmartScreenEnabled: 1
SmartScreenPuaEnabled: 1
DownloadRestrictions: 2
EnhanceSecurityMode: 1
EnhanceSecurityModeEnforceListDomains: ["*.sensitive.internal"]
LocalNetworkAccessRestrictionsEnabled: 1
HttpsOnlyMode: 1
```

High-risk / admin workstations:

```text
SmartScreenEnabled: 1
SmartScreenPuaEnabled: 1
DownloadRestrictions: 3
EnhanceSecurityMode: 2
EnhanceSecurityModeEnforceListDomains: ["*"]
LocalNetworkAccessRestrictionsEnabled: 1
HttpsOnlyMode: 2
```

---

### Generative AI and Data-Loss Controls

Edge integrates with Microsoft Purview and other connectors ("EnterpriseConnector" policies) to enforce DLP, compliance, and monitoring for uploads, prints, and other egress channels. For organizations adopting GenAI and SaaS heavily, these policies are key to keeping sensitive data under control.

#### DLP and Connector Policies

| Policy | Description | Values |
|--------|-------------|--------|
| `OnFileAttachedEnterpriseConnector` | Configures DLP connector for file attachments (for example, uploads in browser). | JSON config = Connector settings (tenant, service, rules) |
| `OnPrintEnterpriseConnector` | Configures DLP connector for print jobs. | JSON config = Connector settings |
| `OnBulkDataEntryEnterpriseConnector` | Configures DLP connector for bulk data entry (for example, form submissions). | JSON config = Connector settings |
| `OnSecurityEventEnterpriseConnector` | Configures reporting connector for security events. | JSON config = Connector settings |
| `ClipboardAllowedForUrls` | Allows clipboard use on specific sites. | String list = URL patterns where clipboard is allowed |
| `ClipboardBlockedForUrls` | Blocks clipboard use on specific sites. | String list = URL patterns where clipboard is blocked |

#### Recommended Enterprise Configuration

Enterprise with Purview DLP and strict SaaS controls:

```text
OnFileAttachedEnterpriseConnector: {"enabled": true, "service": "PurviewDLP", "ruleset": "HighSensitivity"}
OnPrintEnterpriseConnector: {"enabled": true, "service": "PurviewDLP", "ruleset": "HighSensitivity"}
OnBulkDataEntryEnterpriseConnector: {"enabled": true, "service": "PurviewDLP", "ruleset": "HighSensitivity"}
OnSecurityEventEnterpriseConnector: {"enabled": true, "service": "SecurityCenter"}
ClipboardBlockedForUrls: ["https://genai.example.com/*", "https://personal-storage.example/*"]
ClipboardAllowedForUrls: ["https://intranet.example.com/*"]
```

Lighter-weight environment without full connector stack, but wanting some in-browser controls:

```text
ClipboardBlockedForUrls: ["https://public-mail.example.com/*", "https://consumer-cloud.example/*"]
ClipboardAllowedForUrls: ["*"]
```

---

### Extensions and Browser Feature Surface

Extensions and certain built-in surfaces (sidebar, shopping, games, etc.) expand attack and data-exfiltration surface. Enterprises often combine allowlists/denylists with forced installs for approved security tools.

#### Extension and Feature Policies

| Policy | Description | Values |
|--------|-------------|--------|
| `ExtensionInstallAllowlist` | Extensions that are allowed to be installed. | String list = Extension IDs |
| `ExtensionInstallBlocklist` | Extensions that cannot be installed. | String list = Extension IDs or "*" for all |
| `ExtensionInstallForcelist` | Extensions that are silently installed and cannot be removed by users. | String list = `extension_id;update_url` pairs |
| `ExtensionSettings` | Fine-grained extension management (per-ID rules, allowed permissions). | JSON = Extension policy object |
| `EdgeSafeHostingExtensionEnabled` | Controls Microsoft Edge Safe Hosting Extension. | 0 = Disabled, 1 = Enabled |
| `EdgeShoppingAssistantEnabled` | Enables/disables shopping assistant surfaces. | 0 = Disabled, 1 = Enabled |
| `AllowGamesMenu` | Allows access to games menu (deprecated). | 0 = Disabled, 1 = Enabled |

#### Recommended Enterprise Configuration

Strongly managed extension posture with only approved add-ons:

```text
ExtensionInstallBlocklist: ["*"]
ExtensionInstallAllowlist: ["aabbccddeeffgghhiijjkkllmmnnoopp"]
ExtensionInstallForcelist: ["aabbccddeeffgghhiijjkkllmmnnoopp;https://edge.microsoft.com/extensionwebstorebase/v1/crx"]
EdgeSafeHostingExtensionEnabled: 1
EdgeShoppingAssistantEnabled: 0
AllowGamesMenu: 0
```

Less restrictive but guided environment:

```text
ExtensionInstallBlocklist: []
ExtensionInstallAllowlist: []
ExtensionInstallForcelist: ["securityextid1234567890;https://edge.microsoft.com/extensionwebstorebase/v1/crx"]
EdgeSafeHostingExtensionEnabled: 1
EdgeShoppingAssistantEnabled: 1
AllowGamesMenu: 0
```

---

### Identity, Profiles, and Work/Personal Separation

Edge supports multiple profiles (work, personal) and automatic switching based on sites. In enterprises, poorly constrained sign-in and profile behavior can lead to data mixing between personal and corporate contexts.

#### Identity and Profile Policies

| Policy | Description | Values |
|--------|-------------|--------|
| `EdgeBlockSignInEnabled` | Blocks sign-in to Edge with any account. | 0 = Sign-in allowed, 1 = Block sign-in |
| `EdgeAllowedAccountOnly` | Restricts sign-in to allowed accounts only. | 0 = Any account, 1 = Only accounts matching `EdgeAllowedAccountUPN` pattern |
| `EdgeAllowedAccountUPN` | Pattern for allowed account UPNs. | String = UPN pattern (for example, `*@example.com`) |
| `SwitchIntranetSitesToWorkProfile` | Automatically switches intranet sites to a work/school profile. | 0 = Disabled, 1 = Enabled |
| `NonRemovableProfileEnabled` | Ensures a default work or school profile that cannot be removed. | 0 = Disabled, 1 = Enabled |

#### Recommended Enterprise Configuration

Single-tenant enterprise where only corporate Entra ID accounts should be used:

```text
EdgeBlockSignInEnabled: 0
EdgeAllowedAccountOnly: 1
EdgeAllowedAccountUPN: "*@example.com"
SwitchIntranetSitesToWorkProfile: 1
NonRemovableProfileEnabled: 1
```

BYOD / mixed-use environments (allow personal profiles but steer work sites):

```text
EdgeBlockSignInEnabled: 0
EdgeAllowedAccountOnly: 0
EdgeAllowedAccountUPN: ""
SwitchIntranetSitesToWorkProfile: 1
NonRemovableProfileEnabled: 0
```

---

### Policy Reference

For the complete and authoritative list of Microsoft Edge policies, including new, deprecated, and obsolete entries and their platform applicability, see the <a href="https://learn.microsoft.com/en-us/deployedge/microsoft-edge-policies" target="_blank">Microsoft Edge Policy Reference</a>.
