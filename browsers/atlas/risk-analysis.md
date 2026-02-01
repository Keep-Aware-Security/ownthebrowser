Atlas significantly expands the traditional browser threat model by introducing browser memory and agent mode capabilities that allow ChatGPT to observe and act on user activity across sessions.

### Security Architecture

Atlas's architecture uses OWL to separate the UI from Chromium and isolate agent sessions:

- **Chromium sandbox and StoragePartition isolation**: Chromium renders web content in sandboxed processes, and agent sessions run in temporary storage partitions
- **Agent constraints**: Agent mode cannot run code in the browser, download files, install extensions, or access other applications or the file system
- **Composited page view for the agent**: OWL composites off-screen UI elements into a unified frame so the agent receives a full page representation

### Browser Memory and Agent Mode Risks

Browser memory and agent mode are central to Atlas's value proposition and risk profile:

- Browser memories allow ChatGPT to remember which sites users visit and patterns across sessions
- Agent mode gives ChatGPT the ability to open tabs, navigate, complete forms, and place orders
- Compromise of the agent via prompt injection can lead to persistent, cross-session misuse of privileges

### Privacy and Telemetry Considerations

| Feature | Data Sent | Can Disable? |
|---------|-----------|--------------|
| Browser memory | Records visited sites and interaction patterns | Can be turned off in settings |
| Agent mode | Sends page context and action results to ChatGPT | Can be disabled via admin controls |
| Telemetry | Data used to improve Atlas and ChatGPT | Configure via enterprise settings |

### Vendor Dependency

Adopting Atlas deepens dependency on OpenAI for both AI capabilities and the browser surface. Security teams should evaluate Atlas in the context of broader ChatGPT Enterprise agreements and data-processing terms.