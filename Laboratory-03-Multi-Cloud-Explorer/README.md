# Laboratory Activity 3 – Mission 3: Multi-Cloud Explorer

## Checkpoint 7 – Linux Investigation (KillerCoda)

Commands used to collect system information from the KillerCoda Linux playground:

| Information | Command |
|---|---|
| Operating System | `cat /etc/os-release` or `uname -a` |
| CPU Information | `lscpu` |
| Memory | `free -h` |
| Disk Space | `df -h` |

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/4fcdf517-d2c9-40d7-997e-8cd1cdbfc4b2" />

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/241c790f-d7b4-43fa-9c6a-3652df3b7634" />

**Summary of specs:**

| Resource | Value |
|---|---|
| OS | Ubuntu 24.04.4 LTS (kernel 6.8.0), x86_64 |
| CPU | 1 vCPU (Intel Xeon, KVM-virtualized) |
| Memory | 1.9 GiB total |
| Disk | 19 GB root volume (5.4 GB used) |

### If this Linux server were migrated to the cloud, which AWS, Azure, and GCP services could host it?

Given the actual specs collected above, one vCPU with roughly 2 GiB of RAM and a 20 GB disk, this server is small enough to fit the entry-level virtual machine tier on any of the three providers. On **AWS**, the closest match is an **Amazon EC2 t2.small** instance (1 vCPU, 2 GiB RAM), paired with a 20 GB **Amazon EBS gp3** volume for the disk. On **Azure**, the equivalent would be an **Azure Virtual Machine** using the **B1ms** burstable size (1 vCPU, 2 GiB RAM), backed by a 20 GB Standard SSD managed disk. On **GCP**, the same specs map to a **Compute Engine** instance using a custom machine type (**e2-custom-1-2048**: 1 vCPU, 2048 MB RAM), with a 20 GB persistent disk attached. All three options fall into each provider's "burstable" or "shared-core" family, which is designed for lightweight workloads like this one rather than sustained heavy compute, so migrating this server wouldn't require anything beyond the smallest general-purpose VM tier on any platform.

---

*For the full mission overview, checkpoint deliverables, and repository structure, see the Laboratory Activity 3 assignment sheet.*
