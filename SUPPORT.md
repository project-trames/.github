# Getting help with Trames

## Setup and usage

Start with the README and setup documentation for the product you are using:

- [Mac](https://github.com/kb5000/trames-mac#readme)
- [iPad](https://github.com/kb5000/trames-ipad#readme)
- [Linux](https://github.com/kb5000/trames-linux#readme)

Search the product's existing issues before opening a new one. If the documentation
does not answer your question, open a **Question / setup help** issue in that
product's repository. Include the relevant platform, version, command, and error.

## Bugs and compatibility

Use the bug report form in the product where the failure occurs. You do not need
to diagnose Runtime or backend internals first.

Include:

- Product version or commit, host OS, and hardware architecture.
- Execution backend, when known, and guest distribution and application versions.
- Exact reproduction steps, expected behavior, and actual behavior.
- Relevant logs, including whether the problem also occurs on native Linux if tested.

Remove tokens, passwords, private keys, personal paths, and private data from logs.
Avoid attaching a complete root filesystem or memory dump to a public issue.

## Features and contributions

Use a feature proposal to explain the workflow you want to enable, current
limitations, and alternatives you have tried. For patches, read
[CONTRIBUTING.md](CONTRIBUTING.md) and the target repository's local guidance.

## Sensitive security reports

Keep exploit details and sensitive data out of public issues. Follow
[SECURITY.md](SECURITY.md) to report a suspected vulnerability privately.

For harassment or other community conduct concerns, follow
[CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md).

## Availability

Trames is under active development. Support is provided on a best-effort basis;
response times, fixes, and compatibility with a particular application are not guaranteed.
