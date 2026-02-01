Dia is an AI-centered browser from The Browser Company (now part of Atlassian) that launched in 2025 as a Chromium-based browser with a minimalist UI and integrated AI assistant. It was designed as a consumer-friendly alternative to Arc, retaining a familiar Chrome/Safari-like interface while embedding AI capabilities into the core browsing experience. Dia's AI assistant runs in a sidebar, can chat with open tabs, summarize content, and perform contextual actions using pre-built Skills that operate directly on page content.

### Market Position

Dia initially targeted general consumers: students, researchers, professionals, and casual users who wanted AI-enhanced browsing without adopting a new workflow paradigm. Following Atlassian's acquisition of The Browser Company, Dia is now positioned as the primary browser focus with plans to evolve into an AI-powered enterprise browser for knowledge workers. As of late 2025, Dia remains in beta and is functionally closer to a consumer AI browser with emerging enterprise aspirations than a fully realized enterprise product.

### Technical Foundation

Dia is built on Chromium, inheriting Blink, multi-process architecture, and Chrome-compatible web standards and extensions. Vendor materials describe Dia as disabling many Google metrics channels and profile sync to Google accounts, relying on local storage for most content and using encrypted requests when the user explicitly sends data to Dia's chat backend. Dia uses Google Safe Browsing for phishing and malware detection.

### Enterprise Adoption

Dia's current Work messaging describes it as a modern, AI-native browser being prepared for companies of all sizes with security controls and enterprise-grade management in mind, but this is aspirational and accompanied by an early-access contact form rather than a documented enterprise feature set. Public documentation and security bulletins focus on the AI security model, Safe Browsing usage, and restrictions on what the agent can see (hiding password fields and irreversible action buttons), rather than conventional enterprise policy catalogs or admin consoles. The AI agent can see everything the user sees in authenticated sessions, which has serious implications for SSO boundaries and enterprise risk if deployed without compensating controls.