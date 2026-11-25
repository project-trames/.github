<p align="center">
  <img src="https://raw.githubusercontent.com/project-trames/.github/main/assets/trames-banner.svg" alt="Trames — A portable userspace Linux runtime with pluggable execution engines." width="100%">
</p>

<p align="center">
  <a href="#the-project">The Project</a> ·
  <a href="#products">Products</a> ·
  <a href="#shared-components">Shared Components</a> ·
  <a href="#get-started">Get Started</a> ·
  <a href="https://github.com/project-trames/.github/blob/main/CONTRIBUTING.md">Contribute</a>
</p>

---

## The Project

Trames is a modular userspace Linux runtime written primarily in Rust.

Rather than shipping a monolithic virtual machine, Trames decouples OS semantics, instruction execution, and host integration:

* **Userspace Linux Kernel**: Implements Linux syscalls, virtual processes, memory mapping, filesystems, and networking in user space.
* **Pluggable Execution Engines**: Runs guest code using the most suitable engine for the host platform—an AArch64 interpreter on iPadOS, Hypervisor.framework (HVF) on macOS, or KVM on Linux.
* **Host Adapters**: Bridges graphics (Wayland/Xwayland), GPU acceleration (Vulkan/Metal), audio, files, and input into the guest.

Because the underlying Linux implementation is shared, bug fixes and newly supported syscalls automatically benefit all target platforms.

Trames runs unmodified ARM64 Linux binaries, supporting terminal utilities, graphical workspaces, and developer toolchains.

---

## Products

| Product | Description | Status |
| :--- | :--- | :--- |
| [**Trames Mac**](https://github.com/kb5000/trames-mac) | Desktop Linux workspace for macOS powered by native HVF execution and host graphics. | In development |
| [**Trames iPad**](https://github.com/kb5000/trames-ipad) | Local Linux terminal and graphical environment for iPadOS using an AArch64 interpreter. | In development |
| [**Trames Linux**](https://github.com/kb5000/trames-linux) | Linux host environment using KVM for headless workloads and display testing. | In development |
| **Trames Android** | Sandboxed Linux and Android guest environments on Android hosts. | Planned |
| **Trames Windows** | Trames environment on Windows hosts. | Planned |
| **Trames Run** | An OCI container runtime built on the shared userspace kernel. | Planned |
| **Tramix** | A standalone operating system powered by Trames, using Linux for underlying hardware drivers. | Concept |

---

## Shared Components

Core subsystems are structured as reusable libraries:

| Component | Responsibility | Status |
| :--- | :--- | :--- |
| [**trames-runtime**](https://github.com/kb5000/trames-runtime) | The shared userspace Linux kernel, syscall layer, and core OS abstractions. | In development |
| [**trames-cli**](https://github.com/kb5000/trames-cli) | Shared command-line interfaces and host integration utilities. | In development |
| **Network Stack** | A standalone, pure-Rust userspace networking stack. | Planned |
| **CPU Engine** | A standalone, pluggable execution and interpreter library. | Planned |

---

## Get Started

* **Workspaces**:
  * [**Trames Mac**](https://github.com/kb5000/trames-mac#readme) — hardware-accelerated desktop Linux on macOS.
  * [**Trames iPad**](https://github.com/kb5000/trames-ipad#readme) — local terminal and graphical Linux on iPadOS.
  * [**Trames Linux**](https://github.com/kb5000/trames-linux#readme) — KVM-backed execution and qualification tests.

* **Architecture**:
  * Read the [Runtime Overview](https://github.com/kb5000/trames-runtime#readme) to see how system calls, virtual memory, and networking are implemented.

* **Contributing**:
  * Bug reports, test cases, and patches are welcome. Check out [CONTRIBUTING.md](https://github.com/project-trames/.github/blob/main/CONTRIBUTING.md) to get started.
