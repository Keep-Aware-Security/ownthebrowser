[Microsoft Edge management service](https://learn.microsoft.com/en-us/deployedge/microsoft-edge-management-service) and the Microsoft 365 admin center serve as the primary cloud control plane for Edge for Business deployments. Through this environment, administrators can create configuration policies, set priorities between policies, approve or deny extension requests, and apply organizational branding to work profiles.

### Deployment Options

| Method | Best For | Key Features |
|--------|----------|-------------|
| Edge management service (Microsoft 365 admin center) | Cloud-first or Microsoft 365-standardized organizations | Centralized browser-specific configuration policies, policy prioritization, extension request workflows, organizational branding, and profile scoping. |
| ADMX/GPO | Windows devices joined to on-premises or hybrid Active Directory | Full policy coverage for Edge and Edge updates, including security, privacy, update control, and extension management. |
| MDM (for example, Intune) | Mixed fleets across Windows, macOS, iOS, Android | JSON/OMA-URI and built-in templates to apply Edge policies cross-platform. |

### Update Channels

- **Stable**: Default channel with regular feature and security updates, aligned with the Chromium release train
- **Extended or phased release options**: Organizations can use documented update policies to defer and stage updates, controlling rollout waves and maintenance windows

### Extension Management

Extension governance is a central theme in Edge's enterprise guidance. Edge supports:

- **Allowlists**: Policies that restrict extension installation to a defined set of approved extensions
- **Blocklists**: Policies that block specific extensions by ID, including those identified as unwanted or risky
- **Force-install**: Policies that deploy and lock required extensions directly into user profiles

The Edge management service adds an extension request workflow where users can request extensions and administrators can centrally review and approve or deny them.