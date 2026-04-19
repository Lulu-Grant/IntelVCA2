# Networking, SSH, and Service Deployment

## 1. Why the Nodes Can Network Without Physical NICs

Intel VCA2 nodes do not rely on normal external Ethernet ports. Instead:

- nodes communicate with the host through the **PCIe bus**
- the host exposes or configures an internal network for them
- the host then acts as gateway, NAT layer, or forwarder

The easiest way to think about it is:

> each node has a very fast internal virtual network path to the host.

## 2. Internal Bandwidth

The collected materials mention iPerf3 results in the rough range of:

- about `18.1 to 18.8 Gbps` one way
- close to `32 Gbps` in reverse testing

That suggests the host-to-node path is strong enough for image access, local services, and media movement.

## 3. Basic Network Model

The common model is:

1. node talks to the host across the internal network
2. the host acts as default gateway
3. the host forwards traffic to the outside network

At that stage, outbound access often works first, while inbound access still needs more work.

## 4. Exposing Services to Other Devices

If a node service needs to be reachable from elsewhere, the host usually needs:

- port mapping
- DNAT or forwarding
- firewall rules that allow the path

Otherwise a service can appear healthy on the node while still being unreachable externally.

## 5. SSH as the Main Access Method

The materials are clear that the nodes behave like headless servers:

- no normal display workflow
- no monitor-centric management
- SSH is the main operating method

Typical pattern:

```bash
ssh <user>@<node-ip>
```

The exact default credentials should still be checked against the package or image notes in use.

## 6. Default Credentials

The collected materials are not perfectly consistent about default accounts.

What appears relatively common is:

- passwords such as `vista1` or `Vista1`

Because records vary, the safest rule is:

- confirm against the package notes
- change credentials immediately after first successful login

## 7. First Checks After Login

After reaching a node, common sanity checks include:

- `cat /proc/cpuinfo`
- `free -h`
- `df -h`
- connectivity to the host or external network

If these basics look correct, the node environment is usually in a genuinely usable state.

## 8. How to Think About Jellyfin and Docker

One of the most practical documented use cases is:

- installing Docker inside a node
- running Jellyfin
- using the CPU and P580 together for media workloads

The important point is not memorizing exact commands. It is understanding that:

- the node is a legacy system
- the container environment must respect that legacy base
- video-related devices must be exposed correctly inside the node environment

## 9. The Important 10-bit HEVC Limitation

One of the most valuable practical conclusions in the materials is:

> P580 does not support 10-bit decode in the way many modern users expect.

If 10-bit hardware decode is enabled blindly, media playback or transcoding often fails.

The more realistic strategy is:

- CPU for 10-bit software decode
- GPU for later hardware encoding

That mixed model is often the workable one.

## 10. Why the Mixed Model Can Still Work

The documented explanation is roughly:

- the node CPU can shoulder the decode side
- the `128 MB eDRAM` helps with local data movement
- the P580 can still contribute on the encode side

In practice, CPU usage may be high, but the overall media experience can still be acceptable for the right workloads.

## 11. Suitable Service Types

More suitable:

- Jellyfin
- lightweight media services
- transcoding and video-processing experiments
- isolated multi-node service testing

Less suitable:

- modern high-exposure public internet services
- workloads requiring broad support for the newest media formats
- directly exposed legacy systems without a modern protective layer

## 12. Safer Deployment Pattern

For long-term use, a safer structure is:

- host: card management, images, networking, forwarding
- nodes: service execution
- public exposure: ideally handled by a newer proxy or isolation layer

That is usually much safer than exposing the legacy host directly.
