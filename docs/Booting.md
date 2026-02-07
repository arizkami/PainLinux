# PainLinux Challenge

> **PainLinux is not an OS.  
> It is a challenge that measures system-level understanding.**

Last Modified: 2026-02-07

---

## 1. Boot Chain

### 1.1 Boot Kernel in GRUB

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

> *PainLinux does not reward speed.*  
> *It rewards understanding.*
