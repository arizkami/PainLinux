# PainLinux

> **PainLinux is not an operating system.**  
> **It is a challenge.**

Last Modified: 2026-02-07

---

## What Is PainLinux

PainLinux is a **system-level challenge** designed to measure how deeply you understand Linux.

It does not provide:
- an ISO
- a root filesystem
- a toolchain
- scripts
- helper tools
- step-by-step guides

PainLinux provides **documentation only**.

If you are looking for something to install,  
you are in the wrong place.

---

## What PainLinux Measures

PainLinux evaluates understanding at the **system level**, including but not limited to:

- Boot chain comprehension (firmware → bootloader → kernel → init)
- Kernel configuration and early boot behavior
- Initramfs design and responsibility
- Manual networking without helper tools
- Storage, persistence, and disk state management
- Toolchain bootstrapping (GNU, LLVM)
- Debugging discipline
- Ability to stop when the system stops

PainLinux does **not** measure:
- speed
- memorization
- distro familiarity
- command recall

---

## What PainLinux Is Not

- Not a Linux distribution
- Not a learning tutorial
- Not a certification exam
- Not a replacement for LFS, Gentoo, or Arch
- Not beginner-friendly by design

---

## Documentation Model

PainLinux documentation follows these rules:

- Documentation is authoritative
- Documentation may change
- Documentation has **no version numbers**
- Documentation is identified only by **last modified date**
- Documentation does not guarantee success

In many cases, documentation is written in the style of `man` pages.

If the documentation is unclear,  
that ambiguity is part of the challenge.

---

## Rules (Non-Negotiable)

- No prebuilt images
- No prebuilt toolchains
- All build artifacts must live on the **target install disk**
- Networking must be configured manually
- When a build stops, **you stop**
- If it works on the first try, you missed something

---

## Challenge Environment

The PainLinux Challenge is evaluated using:

- QEMU (as a neutral execution environment)
- A blank virtual disk
- No preconfigured partitions
- No preloaded filesystems

Progress is assessed via **system behavior**, not final output.

---

## Completion

There is no “finished system”.

You are considered to have **completed** PainLinux when:
- You understand why each stage works or fails
- Kernel panic does not surprise you
- Build failures lead to analysis, not panic
- You can explain your system state without guessing

---

## Certification

A certificate may be issued **after completion**.

The certificate does not claim expertise.
It only certifies that the holder has completed the PainLinux Challenge under its constraints.

---

## Warning

PainLinux will frustrate you.  
It will invalidate assumptions.  
It will not reward persistence without understanding.

If this upsets you,  
PainLinux is working as intended.

---

## License

PainLinux documentation is provided as-is.

There are no guarantees.
There is no support.
There is no liability.

---

> *PainLinux exists only if you understand it.*
