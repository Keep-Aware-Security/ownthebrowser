Opera's Chromium base provides a familiar security foundation, but its consumer focus, built-in VPN/proxy, and private browser APIs introduce distinct enterprise risk considerations.

### Security Architecture

Opera benefits from Chromium's multi-process sandboxing. Key aspects include:

- **Chromium-derived sandboxing**: Isolated renderer and GPU processes with reduced privileges
- **Frequent updates**: Security updates as Chromium vulnerabilities are addressed
- **Private browser APIs**: Opera exposes private APIs that can become high-value targets for extensions

### Extension and VPN Risks

- **Extension-related risks**: The CrossBarking attack demonstrated malicious extensions could access Opera's private APIs for screenshots and DNS manipulation
- **Built-in VPN/proxy**: Routes traffic through Opera-controlled endpoints; cannot be centrally disabled via corporate policies
- **Policy gaps**: Enterprises may struggle to ensure all traffic passes through approved inspection points

### Privacy & Telemetry Considerations

| Feature | Data Sent | Can Disable? |
|---------|-----------|-------------|
| Built-in VPN/proxy | Traffic may route through Opera servers | No official enterprise policy documented |
| Sync services | Bookmarks, history synced to Opera cloud | Users can disable; no central enforcement |
| Extensions | May communicate with third-party services | No Opera-specific governance documented |

### Vendor Dependency

Opera is developed by an independent vendor (owned by Beijing Kunlun Tech since 2016) without a large enterprise platform ecosystem. Security architects should treat Opera as a consumer browser that may be allowed in controlled ways rather than as a core enterprise browser.