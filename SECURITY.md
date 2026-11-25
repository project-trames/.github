# Security Policy

## Reporting a Vulnerability

Please report suspected security vulnerabilities privately. **Do not open public GitHub issues or pull requests for security-sensitive bugs.**

* **Preferred**: Use GitHub's **[Private Vulnerability Reporting](https://docs.github.com/en/code-security/security-advisories/guidance-on-reporting-and-communicating-vulnerabilities/privately-reporting-a-security-vulnerability)** on the affected repository (Security → Report a vulnerability).
* **Email**: If private reporting is unavailable, email `a123edcrfv@gmail.com` with the subject line `[Trames Security] Brief Description`.

Non-security compatibility bugs, ordinary guest panics, and feature requests should be reported via standard public issues. If you are unsure whether an issue has security implications, report it privately first.

---

## What to Include

To help maintainers reproduce and investigate the issue quickly, please provide:

* **Target Details**: Repository name, commit hash / release build, host OS, architecture, and execution backend (Interpreter, HVF, or KVM).
* **Proof of Concept**: Minimal steps or code to reproduce the issue.
* **Impact & Boundary**: Expected vs. observed behavior, specifically noting the security boundary crossed (e.g., guest-to-host privilege escalation, arbitrary host memory access, or host sandbox escape).
* **Logs & Traces**: Relevant output, ensuring all private keys, paths, and credentials are redacted.

---

## Scope & Security Boundary

Because Trames implements a userspace Linux kernel, it is important to distinguish between guest-level crashes and host security boundaries:

* **In Scope**:
  * Guest-to-host sandbox escapes or arbitrary host code execution.
  * Memory corruption or uncontrolled memory access within the host process.
  * Unauthorized access to host resources (filesystem, GPU/display servers, network interfaces) bypassing platform adapters.
  * Host-level denial of service affecting the host operating system.
* **Generally Out of Scope**:
  * Guest POSIX compliance gaps, internal guest panics, or guest-confined crashes (unless they lead to host-level corruption).
  * Vulnerabilities requiring already-compromised host root privileges or physical device tampering.

---

## Disclosure Process

1. **Review**: Maintainers will review the report, confirm reproducibility, and evaluate the severity and affected components.
2. **Coordination**: We will coordinate with you to validate a fix in a private branch before public release.
3. **Release & Credit**: A security fix will be committed to `main` and published in release notes. We are happy to publicly credit reporters for responsible disclosure, provided you wish to be credited.

> **Note**: Trames is developed on a best-effort basis without a paid bug bounty program.
