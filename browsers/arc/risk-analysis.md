Arc's design emphasizes workflow organization and cloud-backed features such as Notes and Easels stored in Firebase, creating data flows beyond local browsing. The vendor states it does not log page content, history, or URLs in telemetry.

### Security Architecture

Arc's security stance is anchored in its Chromium base and a Firebase/Google Cloud backend:

- **Chromium-based engine**: Inherits sandboxing, process isolation, and the broader Chromium security ecosystem
- **Firebase-backed storage**: User authentication and storage for Notes and Easels rely on Firebase with encryption at rest
- **Limited security documentation**: No full hardening, policy, or incident response guide for enterprises

### Privacy & Telemetry Considerations

| Feature | Data Sent | Can Disable? |
|---------|-----------|-------------|
| Authentication | User identifiers stored in Firebase | Intrinsic to account features |
| Notes and Easels | User content stored in Firebase, encrypted at rest | Users choose what to store; no enterprise policy surface |
| Browser telemetry | Operational metrics; no URLs, history, or page content logged | Limited configuration documentation |

### Vendor Dependency

Arc is produced by The Browser Company, an independent vendor without a large enterprise platform. The announced shift to maintenance mode and focus on new products means there is no public guarantee of extended support or enterprise commitments. Security architects should factor this uncertainty into any decision to allow Arc beyond experimental use cases.