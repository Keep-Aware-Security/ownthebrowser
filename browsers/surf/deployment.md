SURF is deployed as both a full enterprise browser and an extension, allowing policy enforcement across managed and unmanaged endpoints without requiring hardware-based endpoint security or traditional VPN/VDI. Organizations configure zero-trust authentication and device posture checks, define DLP and access policies, and then require users (including contractors) to access corporate resources through SURF so that every interaction can be observed and controlled.

### Deployment Options

| Method | Best For | Key Features |
|--------|----------|-------------|
| SURF full browser on corporate devices | Enterprises standardizing on a secure browser for SaaS and on-prem web apps | Install the SURF browser on managed endpoints; use it as the main workspace with built-in DLP, posture, and web filtering controls |
| SURF browser on unmanaged / BYOD devices | Organizations with remote workforces and contractors | Require users to authenticate and access corporate apps via SURF; posture is enforced agentlessly, and company data remains within the browser container |
| SURF extension on mainstream browsers | Managed devices where corporate profiles enforce extensions | Deploy the SURF extension to Chrome/Edge/other browsers on managed endpoints, adding zero-trust and DLP controls without switching browsers |

### Update Channels

- **SaaS-style updates**: SURF follows a SaaS-like update model, with browser and extension updates delivered via vendor channels and marketplaces
- **Central policy delivery**: Policy and posture changes can be applied centrally without client updates, while new capabilities may depend on updated binaries

### Extension Management

SURF focuses on controlling browser behavior and data movement rather than on an extension-centric model. The platform's policy engine governs data-handling actions (downloads, uploads, clipboard, print, sharing) regardless of which extensions are present.