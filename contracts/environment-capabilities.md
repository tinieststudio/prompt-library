# Environment Capabilities

Before implementation, report the capabilities that affect verification:

- operating system and architecture;
- runtime and package-manager versions;
- browser and browser-driver versions;
- available build, test, lint, and scan tools;
- filesystem read/write boundaries;
- network access and private-network access;
- credentials or services intentionally unavailable.

Use capability detection rather than assumptions. If a required capability is missing, mark the affected task blocked and identify the exact missing capability. Do not silently replace a required check with a weaker one.
