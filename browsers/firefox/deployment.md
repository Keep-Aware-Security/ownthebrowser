The [Firefox Enterprise Policy Engine](https://mozilla.github.io/policy-templates/) and related tooling form the core management surface for Firefox in organizations. Administrators configure Firefox using Group Policy on Windows, configuration profiles on macOS, or `policies.json` files on Linux, all of which consume the same underlying policy definitions.

### Deployment Options

| Method | Best For | Key Features |
|--------|----------|-------------|
| MSI installers + GPO | Windows environments using Active Directory | MSI packages for deployment, ADMX templates for policy control, ability to enforce settings such as updates, extensions, and home pages. |
| macOS configuration profiles | Mac fleets managed via MDM (for example, Jamf) | Support for configuration profiles specifying Firefox policies, packaged in `.mobileconfig` for deployment via standard macOS management tools. |
| `policies.json` on Linux | Linux desktops managed via configuration management (for example, Ansible, Puppet) | Cross-platform Enterprise Policy Engine configuration via a JSON file in the `distribution` directory. |

### Update Channels

- **Rapid Release**: Default Firefox release channel with feature updates approximately every four weeks, suitable for environments that can handle more frequent change
- **Extended Support Release (ESR)**: Firefox ESR provides long-term stability, with annual major releases and regular security updates, designed for organizations that want predictable behavior

### Extension Management

Firefox's add-on model is governed through the same Enterprise Policy Engine used for other settings. Administrators can:

- **Allow or block specific add-ons**: Policies exist to define allowed and blocked add-on IDs
- **Control automatic updates**: Policies can determine whether add-ons update automatically
- **Lock down installation sources**: Organizations can restrict add-on installation to the official Mozilla Add-ons site or internal repositories