# Node Images, Boot Modes, and Persistence

## 1. The Key Idea

Using Intel VCA2 is not mainly about turning on a GPU feature. It is about:

- the host managing the card
- each node booting its own operating system
- actual workloads running inside those node environments

That is why images and boot modes matter so much.

## 2. The Two Main Modes

The collected materials repeatedly refer to two main approaches:

- RAMDisk mode
- BlockIO mode

## 3. RAMDisk Mode

RAMDisk mode works roughly like this:

1. the host binds an image to a node
2. the image is injected into memory during boot
3. the node runs with part of memory acting like a system disk

Strengths:

- often useful for quick validation
- can be a good first bring-up method
- fits temporary testing

Weaknesses:

- not persistent in the usual sense
- reboot or power loss can remove changes
- long-term environment management becomes awkward

Best fit:

- initial bring-up
- temporary experiments
- confirming that a node can boot

## 4. BlockIO Mode

BlockIO mode is closer to a VM-disk style model:

- the host stores an image file
- the image is mapped to the node
- the node uses it like a persistent system disk

Strengths:

- changes survive reboot
- better for long-term maintenance
- better for repeatable service deployment

Weaknesses:

- more image preparation effort up front
- stronger dependence on sensible host storage planning

Best fit:

- long-lived node environments
- service deployment
- repeat testing and configuration work

## 5. Which One to Choose

A simple rule of thumb:

- first boot validation: **RAMDisk**
- long-term usable environment: **BlockIO**
- repeated service use: **BlockIO**
- temporary experimentation: **RAMDisk**

Unless there is a specific constraint, BlockIO is usually the better main path.

## 6. What to Track for Every Image

For every image, it is useful to record:

- image filename
- source package
- matching driver version
- intended purpose such as test, persistent Linux, or Windows

This becomes important because package versions and naming patterns are not always fully uniform.

## 7. M.2 and Images

The collected materials make one point fairly clearly:

- on-card M.2 storage is optional
- node images can live on normal host storage
- M.2 is helpful, but not mandatory

So the practical meaning is:

- no M.2: still workable
- with M.2: sometimes more convenient for transport or organization

## 8. What Success Looks Like

A successful node boot means more than just a command finishing. It means:

- healthy node status in management tools
- a usable OS environment inside the node
- readiness for networking and SSH access

If a node still cannot be used afterward, check:

- image version compatibility
- node memory population
- boot mode choice
- driver and image alignment

## 9. How to View the Windows Path

The official package includes Windows-related material, but the overall direction of the collected experience remains:

- Windows is possible to study
- Linux is usually the safer first path
- the practical value still centers on legacy media-processing workflows

## 10. Persistence Advice

For long-term use, a sensible pattern is:

- prefer BlockIO
- back up image files regularly
- keep each node role stable
- give the nodes clear responsibilities

Example:

- Node 1: testing
- Node 2: media service
- Node 3: backup or experimental work
