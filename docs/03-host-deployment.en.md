# Host Deployment Guide

## 1. What the Host System Does

In an Intel VCA2 setup, the host is not just a machine that happens to hold the card. It is responsible for:

- providing a compatible physical platform
- supplying power, cooling, and PCIe resources
- running host drivers and node-management tools
- storing node images
- acting as the gateway for node networking
- handling forwarding when services are exposed outward

In practice:

> the host is part of the Intel VCA2 system, not just an external controller.

## 2. Recommended Deployment Flow

A stable overall sequence is usually:

1. install a compatible legacy host OS on bare metal
2. install the card and confirm hardware detection
3. install host drivers and node-management tools
4. verify that all three nodes are visible
5. prepare node images
6. choose RAMDisk or BlockIO boot mode
7. configure host-to-node networking

## 3. Recommended Host OS

The most commonly referenced practical route in the collected materials is:

- **CentOS 7.6 on bare metal**

That path is popular because it matches the original driver ecosystem more closely than modern distributions.

Less promising first attempts include:

- forcing modern Linux distributions immediately
- starting with PVE passthrough
- nesting VCA2 behind another virtualization layer

## 4. Hardware Installation Order

A sensible sequence is:

1. confirm the platform and BIOS are not obviously resource-limited
2. install DDR4 SO-DIMM memory as needed for the intended nodes
3. place the card in an appropriate PCIe slot
4. connect `8-pin + 6-pin` power
5. ensure airflow or extra cooling is ready
6. boot into the host OS

Not every node must be populated if a smaller configuration is acceptable, but memory planning directly affects later use cases.

## 5. First Host-Side Validation

After booting the host, the first task is hardware-level validation, not service installation.

The most obvious validation step mentioned in the materials is:

```bash
lspci
```

The goal is not a single exact string. The real goal is to confirm that Intel VCA2-related devices appear and that the platform has not already failed at enumeration time.

If this step is wrong, likely suspects include:

- platform compatibility
- slot choice
- power
- BIOS resource allocation
- general hardware stability

## 6. How to Think About Driver Installation

The collected materials suggest a useful pattern:

- when the environment is wrong, drivers are difficult
- when the environment is right, drivers are often less mysterious than expected

The best approach is:

1. align the platform and OS first
2. follow the instructions inside the exact package being used
3. keep notes about the current driver version and package layout

Exact commands should still come from the official package because names, scripts, and service layout can vary by release.

## 7. What Counts as Success

Driver installation alone is not enough. Real success means:

- node-management tools actually work
- all three nodes appear with readable status
- the card is ready for the next image and boot steps

Only then is the card truly alive in a usable sense.

## 8. Host Storage Planning

Even if the card has M.2 storage positions, the node images do not have to live there.

A practical host storage plan is:

- host OS on a normal system disk
- node images, backups, and logs on host storage
- optional on-card M.2 storage only when it helps portability or organization

## 9. Why the Host Should Stay Focused

Because the host often needs:

- a legacy OS
- older drivers
- older tooling

it is usually wiser to keep the host focused on Intel VCA2 infrastructure rather than turning it into a general public-facing service machine.

## 10. Completion Criteria

Host deployment is in a good state when all of the following are true:

- the card is powered and stable
- the host OS is compatible
- the hardware is visible on the host
- drivers and node-management tools are installed
- node status is visible
- image and network preparation can begin cleanly
