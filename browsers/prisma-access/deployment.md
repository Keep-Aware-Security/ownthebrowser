Prisma Access Browser is deployed and managed as part of Prisma SASE, using Strata Cloud Manager and Prisma Access policy constructs rather than a standalone browser console. Security teams onboard the browser by enabling Prisma Browser within their Prisma Access tenant, defining policies that apply across users, apps, and devices, and distributing the Chromium-based client to managed and unmanaged endpoints.

### Deployment Options

| Method | Best For | Key Features |
|--------|----------|-------------|
| Standard managed desktop rollout | Enterprises with managed Windows/macOS fleets and existing Prisma Access deployments | Distribute Prisma Browser via existing endpoint management; enforce that sensitive SaaS/private apps are reachable only through the browser |
| BYOD / contractor access | Organizations enabling third parties and personal devices without full agents | Use Prisma Browser as the secure workspace on unmanaged endpoints; apply identity- and posture-based policies plus last-mile DLP |
| VDI reduction / replacement | Shops seeking to offload web-centric workloads from VDI | Shift SaaS and web apps into Prisma Browser while reserving VDI for non-web legacy apps |

### Update Channels

- **Cloud-driven updates**: Prisma Browser follows Palo Alto's cloud-driven update model layered on Chromium, with browser binaries updated on a cadence aligned to security and feature rollouts
- **Central policy delivery**: Policy, DLP classifiers, and PrecisionAI models are updated centrally via the Prisma SASE control plane, allowing many security enhancements without local client changes

### Extension Management

Because Prisma Browser is Chromium-based, it can run Chrome-compatible extensions, but the security model centers on SASE policies rather than unmanaged extensions. Many traditional extension-based security functions (DLP, URL filtering, malware prevention) instead come from integrated CDSS services, and network-side policies remain enforced even inside the browser.