Dia's security posture is defined not only by Chromium's baseline protections but also by its AI agent's ability to read and act on content within authenticated sessions, which substantially alters the browser threat model.

### Security Architecture

Dia builds on Chromium's multi-process architecture and Google Safe Browsing, then layers an AI agent that observes page content and executes Skills:

- **Chromium sandbox and Safe Browsing**: Inherits Chrome-like sandboxing and uses Safe Browsing for URL reputation
- **Agent visibility controls**: Vendor documentation states that passwords and irreversible action buttons are hidden from the agent
- **Local storage with encrypted requests**: Content data is stored locally and encrypted, with data only sent to Dia's chat backend when the user issues an AI request

### AI Agent & SSO Risks

Dia's AI agent can observe everything visible in the user's browser, including content behind SSO:

- Prompt-injection attacks can instruct the agent to access unrelated tabs or exfiltrate data
- SSO boundaries are weakened because the agent operates within authenticated sessions
- Multi-step autonomous attacks become more feasible as agents chain actions together

### Privacy & Telemetry Considerations

| Feature | Data Sent | Can Disable? |
|---------|-----------|-------------|
| AI chat requests | Content and prompts sent when users invoke the assistant | Users choose when to send; enterprise enforcement not fully documented |
| Optional learning from history | If enabled, Dia uses browsing history for personalization | Opt-in per user; can be left disabled |
| Browser telemetry | Operational and diagnostic data | Enterprise configuration details limited |

### Vendor Dependency

Dia is now part of Atlassian's strategy to build an AI-powered enterprise browser, tying it closely to Atlassian's SaaS ecosystem (Jira, Confluence, Trello, Loom). Enterprise controls, AI governance, and roadmap direction will be determined by Atlassian's priorities.