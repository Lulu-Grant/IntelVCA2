# Compatibility, Requirements, and Preparation Checklist

## 1. The Most Important Conclusion

Getting Intel VCA2 running usually depends on three conditions being true at the same time:

- the platform is compatible
- the operating system is old enough and appropriate
- the driver and image package is complete

If one of those is missing, the usual result is incomplete detection, unusable nodes, or a driver that appears installed but does not actually work.

## 2. Platform Compatibility

The collected materials are very consistent on one point:

> normal consumer motherboards are usually not the safest choice for Intel VCA2.

Main reasons:

- the card needs substantial **MMIO and mapping resources**
- it fits server-style resource layouts better than consumer boards
- a physical PCIe slot alone does not guarantee full enumeration

The safer platform profile is:

- a server motherboard
- a workstation platform with proven resource flexibility
- strong airflow
- enough PCIe and power headroom

## 3. Cooling Is a Core Requirement

Intel VCA2 uses passive cooling while carrying three nodes internally. That means:

- heat output is not trivial
- weak airflow can quickly become a stability problem
- ordinary low-airflow desktop cases are a poor long-term match

Better approaches include:

- a server chassis with native airflow
- directed active cooling or blower-style modifications

## 4. Why VFIO and Passthrough Usually Fail

One of the most consistent warnings in the collected materials is that Intel VCA2 does not behave like a normal passthrough GPU.

Reasons include:

- reliance on **NTB (Non-Transparent Bridge)**
- sensitivity to physical addressing and node mapping
- virtualization layers usually do not replicate the hardware relationship well enough

Typical failure pattern:

- the VM can see a device
- the driver appears to install
- node bring-up still fails

For that reason, bare metal is usually the most realistic path.

## 5. Operating System Expectations

The documented working ecosystem is old:

- older CentOS releases
- older Ubuntu releases
- package-specific kernels, tools, and helper components

The most commonly referenced working direction is:

- **CentOS 7.6 on bare metal**

That is not because it is modern. It is because it stays close to the original supported environment.

## 6. Package Checklist

Before deployment, it is wise to gather at least:

- the host OS installer
- the host driver package
- node-management tools
- node image packages
- package-specific instructions

## 7. Hardware Checklist

Before installation, confirm:

- a suitable server or workstation platform
- a proper PCIe slot
- `8-pin + 6-pin` power
- DDR4 SO-DIMM memory for the nodes
- host-side storage space for images
- optional M.2 storage if desired
- a cooling setup that can run continuously

## 8. Expectation Checklist

Intel VCA2 is not a one-evening plug-and-play device. A realistic expectation is:

- higher bring-up difficulty than a normal GPU
- package gathering is part of the job
- older operating systems are part of the process
- modern habits and assumptions often do not apply

## 9. Final Pre-Deployment Self-Check

Before starting, ask:

1. Is there a suitable server or workstation platform available?
2. Can the system provide stable power and strong airflow?
3. Are the required OS installers, drivers, and images already collected?
4. Is bare metal acceptable as the primary route?
5. Is the goal research and experimentation rather than convenience?

If several of those answers are still unclear, it is usually better to continue preparing first.
