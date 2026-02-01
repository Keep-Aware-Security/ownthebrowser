[Chrome Enterprise Core](https://chromeenterprise.google/products/chrome-enterprise-core/) (formerly Chrome Browser Cloud Management) serves as the central control plane for enterprise Chrome deployments. Through this cloud-based console, IT administrators can push policies, manage extensions, monitor browser health, and generate compliance reports across their entire fleet.

### Deployment Options

| Method | Best For | Key Features |
|--------|----------|-------------|
| Chrome Enterprise Core | Cloud-first orgs | No on-prem infrastructure required |
| ADMX/GPO Templates | Active Directory environments | 300+ configurable policies |
| MDM Integration | Mixed device fleets | Works with Intune, Jamf, etc. |

### Update Channels

- **Stable**: Updates every 4 weeks, recommended for most deployments
- **Extended Stable**: Updates every 8 weeks, security fixes only between major versions, ideal for organizations needing longer validation windows

### Extension Management

Extension governance deserves particular attention. Chrome supports:

- **Allowlists**: Only approved extensions can be installed
- **Blocklists**: Specific extensions are prohibited
- **Force-install**: Required extensions pushed automatically

Chrome Enterprise Core provides extension risk scoring to help identify potentially dangerous extensions before they become a problem.