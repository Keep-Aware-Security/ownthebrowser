Comet represents an agentic browser where the primary differentiator is an integrated AI capable of reading, remembering, and acting on user content across sessions. This changes traditional browser risk assumptions: security teams must consider the browser as an autonomous actor that can perform actions based on instructions from untrusted content.

### Security Architecture

Comet retains Chromium's security model. The differentiated risks stem from the AI layer:

- **Agentic capabilities**: Comet's AI can click buttons, fill forms, navigate across tabs, and interact with APIs
- **Cross-session memory**: The AI retains knowledge of prior pages, forms, and connected accounts across tabs and time
- **Deep integrations**: Comet can read and act on Gmail, calendars, and Notion content

### Agent Hijacking & Prompt Injection

Security research describes concrete attack scenarios against Comet's AI:

- **Indirect prompt injection**: Attackers can embed instructions in page content that override user prompts
- **Agent hijacking**: A malicious link can direct the AI to access emails, credentials, and connected apps
- **Persistent influence**: The AI's memory can be abused to continue harmful behavior across other sites

### Privacy & Telemetry Considerations

| Feature | Data Sent | Can Disable? |
|---------|-----------|-------------|
| AI interactions | Queries and page content sent to Perplexity backends | Users control when to invoke AI; enterprise deployments can restrict usage patterns |
| Tracking & personalization | Data used to personalize suggestions | Privacy settings can limit some tracking |
| Local vs cloud storage | Some content stored locally; shared when needed for AI tasks | Users can use stricter modes or incognito |

### Vendor Dependency

Adopting Comet introduces dependency on Perplexity AI as both browser provider and AI platform. Security architects should evaluate Comet within the context of their broader Perplexity relationship, including contractual commitments and data-handling terms.