• What it is: The volatile execution layer responsible for workspace isolation and autonomous project containment.
• Technologies inside: LXC/Docker micro-containers, overlay filesystems (OverlayFS), cgroups v2 resource capping, and pre-configured development toolchains (C++, Python, Rust).
• Purpose: To create completely isolated virtual workspaces for every user intent where the AI has full root privileges to safely create, compile, and execute code without risking the security or stability of the host system.
