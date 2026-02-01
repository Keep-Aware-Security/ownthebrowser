Mammoth Enterprise Browser is deployed as a managed enterprise browser across desktops and mobile devices, with centralized policy enforcement and no requirement for MDM or VPN on BYOD endpoints. Security and IT teams define policies in a single console to govern data actions, application access, and GenAI usage, while identity and device posture data drive real-time enforcement decisions. Because Mammoth operates at the browser layer, it can secure unmanaged devices and remote users by turning each session into a fully governed, enterprise-controlled experience without installing OS-level agents.

### Deployment Options

| Method | Best For | Key Features |
|--------|----------|--------------|
| Standard desktop deployment (Windows/macOS) | Enterprises standardizing on a secure browser for SaaS and internal web apps | Deploy Mammoth as a primary browser; enforce zero-trust policies, DLP, and GenAI controls for employees, contractors, and remote developers |
| BYOD and unmanaged devices | Organizations with distributed and contractor workforces | Launch apps in an isolated, enterprise-only browser on personal laptops, tablets, and phones; restrict copy/paste, downloads/uploads, print, and screen share; auto-watermark and record high-risk sessions |
| Mobile enterprise browser | Field and mobile use cases requiring secure SaaS/internal access | Provide a mobile Mammoth browser for iOS/Android that routes access to internal and SaaS apps without VPN, enforcing browser-level policies and GenAI restrictions |

### Update Channels

- **SaaS-style releases**: Mammoth follows a SaaS-style release cadence with documented version updates introducing new security and governance capabilities
- **Cloud-delivered policy**: Policy is centrally defined and evaluated at runtime, so many configuration changes can be applied without upgrading the browser itself

### Extension Management

Mammoth focuses on controlling browser behavior and data movement rather than on an extension-centric model. The platform's policy engine allows administrators to:

- Define which SaaS and web applications are allowed, and block shadow IT and unapproved file-sharing tools
- Restrict data-handling actions (downloads, uploads, clipboard, print, sharing) regardless of which extensions are present
- Detect and audit extensions associated with unauthorized AI use or data exfiltration as part of shadow AI defense