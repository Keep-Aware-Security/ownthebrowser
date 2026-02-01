Arc does not ship with a dedicated enterprise deployment and management stack. It is installed and updated like a consumer application, with limited documentation on configuration for managed environments. On macOS, The Browser Company documents that Arc policies are stored in a property list (plist), and administrators can adjust settings by editing that file or deploying managed preferences. On Windows, Arc is delivered as a native WinUI application, and deployment relies on standard software distribution tools and built-in auto-update.

### Deployment Options

| Method | Best For | Key Features |
|--------|----------|-------------|
| Manual or MDM-based install on macOS | Small teams with limited Arc usage | Install from vendor site; manage basic settings via plist-based preferences |
| Software distribution on Windows | Organizations permitting Arc as secondary browser | Package installer and deploy to targeted devices; rely on auto-update |
| End-user installation | BYOD or lightly managed environments | Users install directly; IT relies on endpoint and network security tools |

### Update Channels

- **Stable builds with auto-update**: Arc provides stable releases with integrated auto-update; no ESR-style channel or enterprise release track exists
- **Maintenance mode**: With Arc's shift to maintenance status, updates focus on stability and security rather than new features

### Extension Management

Arc runs Chrome-compatible extensions via Chromium's extension framework, but there is no enterprise extension governance guide. Governance typically relies on external controls (EDR, CASB, proxy filtering) rather than Arc-native extension policies.