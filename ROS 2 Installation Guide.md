# ROS 2 Installation Guide

**Area:** Installation  
**Content type:** Overview  
**Level:** Beginner to intermediate

## Overview

Installing ROS 2 correctly helps ensure that your development environment matches your operating system, permissions, and intended use. This guide summarizes the supported installation options described in the supplied ROS 2 installation information, compares binary packages with source builds, and outlines how to choose an approach.

## Contents

1. Binary packages
2. Building from source
3. Choosing an installation method
4. Platform-specific installation guides
5. Advanced installation topics
6. Summary

## 1. Binary Packages

Binary packages provide a prebuilt ROS 2 installation. They are intended for users who want to start using ROS 2 without building it themselves.

According to the supplied installation information, binary packages are available for the following Tier 1 platforms:

| Platform | ROS 2 distribution / version stated in source | Binary installation options |
|---|---|---|
| Ubuntu Linux (amd64 / aarch64) | Resolute Raccoon (26.04) | Debian packages (recommended) or binary archive |
| Red Hat Enterprise Linux 10 (amd64) | Not specified | RPM packages (recommended) or binary archive |
| Windows 11 (amd64) | Not specified | Windows binary (VS 2019) |
| Fedora Linux (amd64) | Not specified | RPM packages (recommended) |

Binary availability depends on the operating system and ROS 2 distribution. If a platform is not listed as supported for binaries, building from source or using a container may be an alternative.

### Package installation and binary archives

On supported Linux systems, users can install ROS 2 from distribution packages or use a binary archive. Package installation is generally recommended because the package manager installs required dependencies and can receive updates through normal system updates. Installing system packages usually requires administrator or root privileges.

A binary archive is an alternative when package installation is unsuitable, such as when root access is unavailable. Windows binary installations are provided as archives rather than Debian packages.

## 2. Building from Source

A source build compiles ROS 2 from its source code. It is intended for developers who need to modify ROS 2, omit selected components, work on a platform without supported binaries, or use the latest development version.

The supplied information lists source-build support for:

| Platform | Source-build support stated in source |
|---|---|
| Ubuntu Linux 26.04 | Supported |
| Ubuntu Linux 26.04 (Pixi) | Supported |
| Windows 11 | Supported |
| RHEL 10 / Fedora | Supported |
| macOS | Supported |

A source build offers more flexibility, but it requires the developer to follow the platform-specific instructions and manage the build environment and dependencies.

## 3. Choosing an Installation Method

Both binary packages and source builds can provide a functional ROS 2 installation. The best choice depends on what you plan to do.

| Your situation | Suggested approach | Why |
|---|---|---|
| You want to start using ROS 2 quickly | Binary packages | ROS 2 is already built and ready to install |
| You use a supported Linux distribution and have administrator access | Distribution packages | Dependencies are installed automatically and updates integrate with system package management |
| You do not have administrator access | Binary archive, if available for your platform | Avoids installing system packages |
| You need to modify ROS 2 or omit components | Build from source | Provides control over the source and build configuration |
| Your platform does not provide suitable binaries | Build from source or use a container | Provides an alternative for unsupported binary platforms |
| You plan to contribute to ROS 2 core | Build the latest development version from source | Core development uses source-installation instructions associated with the Rolling distribution |

## 4. Platform-Specific Installation Guides

Use the installation instructions that match your platform and intended installation method:

| Guide | Purpose |
|---|---|
| Installing on Ubuntu | Install ROS 2 on Ubuntu |
| Installing on Windows (binary) | Install the Windows binary distribution |
| Installing on RHEL / Fedora (RPM packages) | Install ROS 2 using RPM packages |
| Installing ROS 2 on Raspberry Pi | Set up ROS 2 on Raspberry Pi |
| Troubleshooting installation | Diagnose common installation problems |

Consult the official ROS 2 documentation for the detailed, current commands and prerequisites for your specific distribution and operating system.

## 5. Advanced Installation Topics

The ROS 2 installation documentation also covers advanced options and related topics:

| Topic | Description |
|---|---|
| Advanced installation options | Additional setup approaches and configuration choices |
| RMW implementations | Middleware options used for ROS 2 communication |
| Mirrors | Alternative package or repository mirrors |
| Snapshot repository | Installing from a snapshot of repository content |

## 6. Contributing to ROS 2 Core

If you plan to contribute directly to ROS 2 core packages, the supplied guidance recommends installing the latest development version from source. Those instructions are shared with the Rolling distribution.

## Summary

ROS 2 can be installed from prebuilt binaries or built from source. Binary packages are the simplest starting point for general use, and Linux distribution packages are recommended when available and when administrator access is permitted. Binary archives are useful when system package installation is not an option. Source builds are better suited to developers who need to customize ROS 2, contribute to core packages, or use a platform without suitable binary packages.

Before installing, confirm your operating system, architecture, ROS 2 distribution, and access permissions, then follow the matching official platform instructions.
