# ARK-OS Packaging and Image Assembly

## Overview

The `packaging/` repository contains image assembly recipes, root filesystem (`rootfs`) staging blueprints, initramfs bundling scripts, and distribution format definitions for ARK-OS.

---

## Directory Organization

- `recipes/` - Declarative specifications for generating system images, disk partitioning profiles (GPT/ESP), and package manifests.
- `rootfs/` - Staging directory layouts, minimal directory hierarchy definitions (`/dev`, `/proc`, `/sys`, `/etc`, `/sbin`, `/bin`), and base permission models.

---

## Bring-Up Packaging Staging

Per [ADR-0004](file:///home/aarav/repo/arkos/docs/decisions/ADR-0004-initial-boot-process-initramfs.md):
- **Phase 1 (Initial Bring-Up):** Packaging focuses exclusively on generating a standalone compressed CPIO archive (`initramfs.cpio.gz`) containing `/sbin/arkrt`, required runtime dynamic libraries, and essential static nodes for direct QEMU boot.
- **Phase 2 (Persistent Storage):** Recipes expand to produce raw disk images (`.raw`, `.qcow2`) with partitioned GPT layouts, UEFI EFI system partitions, and root filesystem formatting.

---

## License

This repository is licensed under the Apache License, Version 2.0. See [LICENSE](file:///home/aarav/repo/arkos/packaging/LICENSE) for the full license text.
