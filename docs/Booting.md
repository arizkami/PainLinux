# PainLinux Challenge

> **PainLinux is not an OS.  
> It is a challenge that measures system-level understanding.**

Last Modified: 2026-02-07

---

## 1. Boot Chain

Booting is the first system-level responsibility.  
No assumptions are provided.

---

### 1.1 Boot from GRUB

#### Objective
Boot a **self-built Linux kernel** using **GRUB**.

No root filesystem is assumed.  
No initramfs is required at this stage.

Reaching a shell is **not** the goal.

---

#### Description
The kernel **must** be loaded explicitly by GRUB.

No distribution defaults are allowed.  
No automatic configuration is assumed.

GRUB is only a loader.  
It does not validate correctness.

If the kernel fails to boot,  
the failure belongs to the builder.

---

#### Requirements
- Linux kernel source built by the participant
- GRUB (EFI or BIOS, participant’s choice)
- Manually defined kernel parameters
- No reliance on prebuilt images

---

#### Constraints
- The kernel image must be loadable by GRUB
- Kernel parameters must be provided explicitly
- The kernel **must reach early initialization**
- A kernel panic is an acceptable outcome
- Silence is not

---

#### Expected Failure Modes
Any of the following are valid and expected:

- Kernel panic: unable to mount root filesystem
- No output after `Loading Linux...`
- Immediate reboot
- Triple fault

Failure is not an error state.  
It is part of the challenge.

---

#### Success Criteria
This step is considered **complete** when **any one** of the following occurs:

- Kernel messages appear on the console
- A controlled kernel panic is observed
- Execution reaches the point where `init` would be executed

A working userspace is **not required**.

---

#### Warnings
- GRUB success does not imply kernel correctness
- Booting once does not imply repeatability
- A kernel that boots today may fail tomorrow

---

#### Failure Policy
If the kernel does not boot:

**Stop.**

Do not toggle random kernel options.  
Do not add parameters blindly.  
Read the failure before proceeding.

---

#### Notes
If this step feels trivial,  
you are either experienced  
or you have missed something.

---

### 1.2 Boot from EFI Shell

#### Objective
Boot a **self-built Linux kernel** directly from the **UEFI Shell**,  
without using GRUB or any secondary bootloader.

This step exists to remove all abstractions.

---

#### Description
The EFI Shell exposes the firmware interface directly.

There is no configuration generator.  
There is no safety net.

The kernel is executed as an EFI application.  
You are responsible for everything that follows.

If this fails,  
the firmware is not at fault.

---

#### Requirements
- UEFI-capable system or virtual machine
- Linux kernel built with EFI support
- Access to an EFI Shell environment
- Manually supplied kernel parameters

---

#### Constraints
- No GRUB or intermediary bootloader
- No automatic device discovery assumptions
- No implicit console configuration
- No guarantee of output

Silence is a valid outcome.

---

#### Expected Failure Modes
Any of the following are valid and expected:

- Kernel fails to load as an EFI image
- Immediate return to EFI Shell
- Silent hang
- Kernel panic without console output

These failures indicate missing understanding,  
not misconfiguration.

---

#### Success Criteria
This step is considered **complete** when **any one** of the following occurs:

- The kernel executes and prints output
- The kernel reaches early initialization
- A controlled failure occurs after execution begins

Booting further than GRUB is **not required**.

---

#### Warnings
- EFI success does not imply kernel correctness
- Firmware behavior is not consistent across systems
- Debugging options may be limited or absent

---

#### Failure Policy
If the kernel does not execute:

**Stop.**

Do not immediately fall back to GRUB.  
Understand why the firmware rejected or failed to execute the kernel.

---

#### Notes
If you can boot from the EFI Shell reliably,  
you understand the boot chain at a level  
most systems never expose.

---

> *PainLinux does not reward speed.*  
> *It rewards understanding.*
