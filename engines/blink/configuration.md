## Chromium-Based Browser Configuration

Browsers built on Chromium share a common policy infrastructure derived from the open-source Chromium project. This means many configuration options, policy names, and deployment patterns are similar across browsers like Chrome, Edge, Brave, Opera, and Vivaldi.

### Shared Policy Framework

Most Chromium-based browsers support the same core policy mechanisms:

| Platform | Method | Location |
|----------|--------|----------|
| Windows | Group Policy (ADMX) | Vendor-specific ADMX templates |
| Windows | Registry | `HKLM\SOFTWARE\Policies\{Vendor}\{Browser}` |
| macOS | Managed Preferences | Vendor-specific preference domain |
| Linux | JSON policies | `/etc/{vendor}/policies/` |

The <a href="https://chromeenterprise.google/policies/" target="_blank">Chrome Enterprise Policy List</a> serves as a useful reference, as many Chromium browsers implement the same policy keys. However, each vendor typically maintains their own registry path, preference domain, and policy namespace.

### Browser-Specific Variations

While the underlying policy architecture is shared, each Chromium browser may:

- **Use different registry/preference paths** — Edge uses `Microsoft\Edge`, Brave uses `BraveSoftware\Brave-Browser`, etc.
- **Support a subset of policies** — Not all browsers implement every Chromium policy
- **Add vendor-specific policies** — Browsers often add unique policies for their own features
- **Provide their own ADMX templates** — Download templates from each vendor's enterprise documentation

For specific policy paths, supported policies, and vendor management tools, refer to the individual browser documentation pages on this site.