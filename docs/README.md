# Introduction to Zero-OS

Zero-OS is a stateless and lightweight Linux operating system designed for clustered deployments to host virtual machines and containerized applications.

- Zero-OS is stateless by not needing any locally stored data, not even Zero-OS system files
- Zero-OS is lightweight by only containing the components required to securely run and manage containers and virtual machines

See [Getting Started with Zero-OS](gettingstarted/gettingstarted.md) for the recommended path to quickly get up and running with Zero-OS.

Key components:

- [0-Initramfs](#0-initramfs)
- [0-Core](#0-core)
- [0-FS](#0-fs)
- [0-Hub](#0-hub)
- [0-Orchestrator](#0-orchestrator)
- [0-Disk](#0-disk)

> All documentation has been tested using **v8.2.0rc1** [jumpscale_core8](https://github.com/Jumpscale/jumpscale_core8/tree/v8.2.0rc1) and **v1.1.0-alpha-2** of [0-Initramfs Builder](https://github.com/zero-os/0-initramfs/releases/tag/v1.1.0-alpha-2), [0-Core](https://github.com/zero-os/0-core/releases/tag/v1.1.0-alpha-2), [](https://github.com/zero-os/0-fs/releases/tag/v1.1.0-alpha-2) and [Zero-OS REST API](https://github.com/zero-OS/0-disk/releases/tag/v1.1.0-alpha-2)

<a id="0-core"></a>
## Zero-OS Initramfs

0-Initramfs is an assembly of shell scripts for building the Zero-OS Linux kernel and create an 0-initramfs to start 0-Core.

- GitHub repository: [g8os/hub](https://github.com/g8os/hub)
- Documentation: [0-Initramfs Documentation](https://github.com/zero-os/0-initramfs/blob/master/docs/SUMMARY.md)
- Getting started: [Getting Started with 0-Initramfs](https://github.com/zero-os/0-initramfs/blob/master/docs/gettingstarted/gettingstarted.md)

<a id="0-core"></a>
## 0-Core

0-Core is the Zero-OS replacement for systemd, the init system to bootstrap the user space and manage all processes subsequently.

Interacting with 0-Core is done by sending commands through a Redis, allowing you to manage disks, set-up networks and create containers and start virtual machines.

- GitHub repository: [zero-os/0-core](https://github.com/zero-os/0-core)
- Documentation: [0-Core Documentation](https://github.com/zero-os/0-core/blob/master/docs/SUMMARY.md)
- Getting started: [Getting Started with 0-Core](https://github.com/zero-os/0-core/blob/master/docs/gettingstarted/gettingstarted.md)

<a id="0-fs"></a>
## Zero-OS File System

Zero-OS File System is the Zero-OS file system used in containers, which is actually a FUSE file system. Mounting the  is done by using a flist, which is a relatively small RocksDB database file, containing the metadata of the actual files and directories. On accessing a file Zero-OS fetches the required file chunks from a remote store, and caches it locally. This remote store is the Zero-OS Hub, discussed here below.

- GitHub repository: [g8os/hub](https://github.com/g8os/0-fs)
- Documentation: [ Documentation](https://github.com/zero-os/0-fs/blob/master/docs/SUMMARY.md)
- Getting started: [Getting Started with ](https://github.com/zero-os/0-fs/blob/master/docs/gettingstarted/gettingstarted.md)

<a id="0-hub"></a>
## Zero-OS Hub

The Zero-OS Hub is where all container images and and vdisk boot images are stored.

- GitHub repository: [g8os/hub](https://github.com/g8os/hub)
- Documentation: [Hub Documentation](https://github.com/g8os/hub/blob/master/docs/SUMMARY.md)
- Getting started: [Getting Started with the Zero-OS Hub](https://github.com/g8os/hub/blob/master/docs/gettingstarted/gettingstarted.md)

<a id="0-orchestrator"></a>
## Zero-OS Orchestrator

The Zero-OS Orchestrator is the REST API server for managing a cluster of Zero-OS nodes.

- GitHub repository: [zero-os/0-orchestrator](https://github.com/zero-OS/0-orchestrator)
- Documentation: [Zero-OS Orchestrator Documentation](https://github.com/zero-OS/0-orchestrator/blob/master/docs/SUMMARY.md)
- Getting Started: [Getting Started with Zero-OS Orchestrator](https://github.com/zero-OS/0-orchestrator/blob/master/docs/gettingstarted/gettingstarted.md)

<a id="0-disk"></a>
## 0-Disk

0-Disk is about the components that allow to create and use block devices (vdisks) from within virtual machines hosted on a Zero-OS node.

- GitHub repository: [zero-os/0-disk](https://github.com/zero-os/0-disk)
- Documentation: [0-Disk Documentation](https://github.com/zero-os/0-disk/blob/master/docs/SUMMARY.md)
- Getting Started: [Getting Started with NBD Server](https://github.com/zero-os/0-disk/blob/master/docs/gettingstarted/gettingstarted.md)
