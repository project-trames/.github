# Contributing to Trames

Thanks for your interest in contributing to Trames! We welcome bug reports, reproduction cases, documentation, benchmarks, and code contributions.

---

## Where to Contribute

Trames is split into several repositories. Please direct issues and pull requests to the relevant layer:

| Area | Repository |
| :--- | :--- |
| **Userspace Linux Kernel** (Syscalls, processes, VFS, memory, networking) | [trames-runtime](https://github.com/kb5000/trames-runtime) |
| **macOS Workspace** (HVF execution, Metal/Wayland host integration) | [trames-mac](https://github.com/kb5000/trames-mac) |
| **iPadOS Workspace** (AArch64 interpreter, iPad UI, and platform integration) | [trames-ipad](https://github.com/kb5000/trames-ipad) |
| **Linux Host** (KVM backend, CLI qualification, display testing) | [trames-linux](https://github.com/kb5000/trames-linux) |
| **Shared CLI** (Command-line parsing and client utilities) | [trames-cli](https://github.com/kb5000/trames-cli) |
| **Community & Meta** (Organization profile, documentation, and shared templates) | [project-trames/.github](https://github.com/project-trames/.github) |

*Not sure where an issue belongs?* File it under the product where you observed the behavior (e.g., `trames-mac` or `trames-ipad`) with your setup details. Maintainers will help route it to the right place.

---

## Development Workflow

1. **Check existing records**: Review existing issues, PRs, and docs in the target repository to see if the issue is already known or under discussion.
2. **Discuss major changes**: For significant architecture adjustments, new abstractions, or large syscall additions, please open an issue first to discuss the design.
3. **Keep semantics in Runtime**: Whenever fixing general Linux behavior or system call semantics, implement the fix in `trames-runtime` rather than working around it in product-specific code.
4. **Respect platform boundaries**: Keep host-specific dependencies isolated behind existing platform abstractions.

---

## Pull Request Guidelines

* **Target `main`**: All active development flows into the `main` branch of the respective repository.
* **Keep patches focused**: Avoid mixing unrelated refactorings or cosmetic formatting changes into functional bug fixes.
* **Explain the change**: In your PR description, describe:
  * The original behavior / bug and how to reproduce it.
  * The new behavior and why this implementation was chosen.
  * Any known limitations or affected submodules.

---

## Verification & Testing

Every PR should include verifiable evidence that the change works as expected:

* **Compare against native Linux**: For syscalls or POSIX semantics, verify that behavior matches a standard Linux kernel whenever possible.
* **State what ran**: Mention your host environment (OS, architecture, backend), the exact test commands executed, and the results.
* **Device vs. Simulator**: Clearly state whether verification was performed on real hardware or in a simulator/VM.
* **Missing hardware?** If your change affects a platform you don't have access to (e.g., an iPad or macOS environment), mention it in your PR so maintainers can assist with testing.

---

## AI-Driven Development

Trames is a fully AI-driven systems project. Contributions from both human engineers and autonomous AI coding agents are warmly welcomed.

* **Review & Merge**: All pull requests are reviewed by AI systems and finalized by human maintainers before merging.
* **Agent-Friendly**: If you are operating an AI agent (or are an agent contributing directly), please consult `AGENTS.md` and relevant architecture records in the target repository to follow existing design contracts.
* **Ground Truth Matters**: Regardless of who or what writes the patch, accuracy is non-negotiable. Never fabricate test runs, benchmark numbers, or compatibility claims—all submitted evidence must reflect real, reproducible execution.

---

## Licensing & Copyright

* Check the `LICENSE` file of the target repository before contributing.
* Ensure you hold the necessary rights to submit your contribution under the repository's license.
* If including third-party code or dependencies, preserve existing copyright notices, identify the upstream source, and confirm license compatibility beforehand.

---

## Reporting Issues & Security

* For regular questions and troubleshooting, refer to [SUPPORT.md](SUPPORT.md).
* **Sensitive Information**: Do not post credentials, private filesystem paths, personal data, or actionable security exploits in public issues.
