Mammoth's approach, embedding zero-trust, DLP, and AI governance directly into the browser, shifts critical security controls from the network and endpoint agent layers into a single, high-privilege application. This consolidates visibility and enforcement where users actually interact with SaaS and GenAI tools, but it also makes the browser environment a focal point for both defensive and potential offensive activity.

### Security Architecture

Mammoth's security model combines browser-native controls with identity, posture, and AI awareness:

- **Session isolation**: Sensitive sessions, especially GenAI workflows, run in controlled environments where agents cannot reach local files or credentials
- **Browser-level DLP**: Continuous enforcement prevents unauthorized downloads, uploads, clipboard use, document exports, and screen sharing, including attempts by AI agents
- **Identity and posture-based policy**: Policies adapt to user role, device type, and risk signals, enforcing least-privilege access and blocking risky combinations
- **Full audit trails**: Detailed logs correlate identities, session context, and data actions to support compliance, threat detection, and investigations

### Privacy and Telemetry Considerations

| Feature | Data Collected | Implication |
|---------|----------------|-------------|
| Session and action logs | Identity, device posture, visited apps, clipboard/file actions, blocked/allowed events | Enables real-time detection and compliance reporting; requires strong controls over log access and retention |
| AI actions and prompts | AI-driven actions and potentially prompt content, especially in regulated contexts | Supports mandatory AI action auditing but may introduce sensitive content into logs |
| Policy decisions | Records of why policies allowed or blocked data actions and app access | Helps demonstrate regulatory adherence and tune policies |

### Vendor Dependency

Mammoth positions itself as the central browser-based governance layer for zero trust and AI, which creates a strong dependency on the vendor's roadmap, availability, and security posture. Mandating a single enterprise browser concentrates control in one vendor and can complicate future migrations or multi-browser strategies. Security architects should evaluate Mammoth's role alongside existing SWG, ZTNA, DLP, and EDR stacks.