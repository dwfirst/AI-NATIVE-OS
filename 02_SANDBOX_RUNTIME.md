• What it is: The volatile execution layer responsible for workspace isolation and autonomous project containment.
• Technologies inside: LXC/Docker micro-containers, overlay filesystems (OverlayFS), cgroups v2 resource capping, and pre-configured development toolchains (C++, Python, Rust).
• Purpose: To create completely isolated virtual workspaces for every user intent where the AI has full root privileges to safely create, compile, and execute code without risking the security or stability of the host system.

---

### Open Questions

1. LXC vs Docker: which provides better isolation for AI-generated code?
2. How is GPU access mediated between sandbox and host?
3. What is the maximum number of concurrent sandboxes before resource exhaustion?
4. How does the sandbox handle persistent state across sessions?
5. What is the threat model for container escape, and how is it mitigated?
