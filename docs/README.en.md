# Intel VCA2 Documentation Guide

This page is the English landing guide for the repository.

This repository now includes an English documentation path for readers who do not want to navigate Chinese pages first.

## Recommended Reading Order

1. [English Quick Start](./QUICKSTART.en.md)
2. [Overview and Hardware Structure](./01-overview.en.md)
3. [Compatibility and Preparation Checklist](./02-compatibility-and-checklist.en.md)
4. [Host Deployment Guide](./03-host-deployment.en.md)
5. [Node Images and Boot Modes](./04-node-images-and-boot-modes.en.md)
6. [Networking, SSH, and Service Deployment](./05-networking-ssh-and-services.en.md)
7. [Risks, Limitations, and FAQ](./06-risks-limitations-and-faq.en.md)
8. [Documentation Scope and Boundaries](./07-scope-and-boundaries.en.md)
9. [Repository README package index](../README.md)

## What Each Document Covers

## `01-overview.en.md`

- what Intel VCA2 is
- why it is not a normal GPU
- why the three-node architecture matters

## `02-compatibility-and-checklist.en.md`

- platform and motherboard compatibility
- cooling and power expectations
- why consumer boards often fail
- why VFIO / VM passthrough is usually not the right route

## `03-host-deployment.en.md`

- the role of the host system
- legacy OS expectations
- hardware installation flow
- driver and node-management workflow

## `04-node-images-and-boot-modes.en.md`

- RAMDisk vs BlockIO
- persistence tradeoffs
- image planning
- why BlockIO is generally preferred for long-term use

## `05-networking-ssh-and-services.en.md`

- internal PCIe-based networking model
- SSH access to nodes
- service deployment mindset
- Jellyfin / media workload considerations

## `06-risks-limitations-and-faq.en.md`

- what Intel VCA2 is still good for
- what it is not good for in modern usage
- security and maintenance risks
- common troubleshooting directions

## `07-scope-and-boundaries.en.md`

- how to use this documentation correctly
- why exact commands should still come from the official package

## Repository README package index

- which files in the official Mega package matter most
- how host packages, images, and dependencies are separated
- where to find quick links and representative filenames

## Important Note

This repository is a structured guide. It does **not** replace the full official driver, image, and tooling package.

The official package should remain the primary source for:

- exact installation commands
- node-management commands
- image mount commands
- service names and script paths
- credentials and version-specific behavior

## Search Terms

For search and discovery, the most relevant terms are:

`Intel VCA2`, `Intel Visual Compute Accelerator 2`, `Intel VCA2 guide`, `Intel VCA2 documentation`, `Intel VCA2 deployment`, `Intel VCA2 BlockIO`, `Intel VCA2 RAMDisk`, `Intel VCA2 transcoding`, `Intel VCA2 Jellyfin`
