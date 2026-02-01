Mozilla Firefox launched in 2004 as an open-source alternative to Internet Explorer, focusing on standards compliance, user control, and extensibility. Over time, Firefox has evolved into a multi-process, sandboxed browser with enterprise-focused variants such as Firefox Extended Support Release (ESR) to support organizational stability needs.

### Market Position

Firefox maintains a meaningful share of the global desktop browser market, generally in the single-digit percentage range, and is often adopted by users and organizations that prioritize privacy, open-source software, or non-Chromium engines. Mozilla's enterprise messaging highlights Firefox and Firefox ESR as suitable for "security at scale," with an enterprise support program for large deployments.

### Technical Foundation

Firefox is built on the Gecko engine with a multi-process architecture that separates the browser UI, web content, and privileged processes. Mozilla has deployed a Site Isolation security architecture that loads each site into its own operating system process, isolating memory between different sites and making Spectre-style attacks and cross-site data access more difficult. Firefox's open-source implementation allows external review of security mechanisms and enterprise features.

### Enterprise Adoption

Firefox for Enterprise provides MSI installers, ESR builds, and a documented policy framework to support managed deployments on Windows, macOS, and Linux. Policies can be enforced using Group Policy on Windows, configuration profiles on macOS, and `policies.json` files on Linux, all backed by a unified Enterprise Policy Engine. Mozilla positions Firefox and ESR for organizations that need a privacy-focused browser with transparent behavior.