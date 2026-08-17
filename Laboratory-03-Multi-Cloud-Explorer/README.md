# Laboratory Activity 3 – Mission 3: Multi-Cloud Explorer

## Checkpoint 7 – Linux Investigation (KillerCoda)

Commands used to collect system information from the KillerCoda Linux playground:

| Information | Command |
|---|---|
| Operating System | `cat /etc/os-release` or `uname -a` |
| CPU Information | `lscpu` |
| Memory | `free -h` |
| Disk Space | `df -h` |

*(Run each command in your KillerCoda terminal, then paste the output below and insert a screenshot of the terminal for each one.)*

```
root@ubuntu:~$ uname -a
Linux ubuntu 6.8.0-136-generic #136-Ubuntu SMP PREEMPT_DYNAMIC Wed Jul  1 21:53:05 UTC 2026 x86_64 x86_64 x86_64 GNU/Linux

root@ubuntu:~$ cat /etc/os-release
PRETTY_NAME="Ubuntu 24.04.4 LTS"
NAME="Ubuntu"
VERSION_ID="24.04"
VERSION="24.04.4 LTS (Noble Numbat)"
VERSION_CODENAME=noble
ID=ubuntu
ID_LIKE=debian

root@ubuntu:~$ lscpu
Architecture:                x86_64
CPU(s):                      1
Vendor ID:                   GenuineIntel
Model name:                  Intel Xeon E312xx (Sandy Bridge, IBRS update)
Thread(s) per core:          1
Core(s) per socket:          1
Socket(s):                   1
Virtualization features:
  Hypervisor vendor:         KVM
  Virtualization type:       full

root@ubuntu:~$ free -h
               total        used        free      shared  buff/cache   available
Mem:           1.9Gi       417Mi       868Mi       1.1Mi       785Mi       1.5Gi
Swap:          1.0Gi          0B       1.0Gi

root@ubuntu:~$ df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/vda1        19G  5.4G   13G  30% /
/dev/vda16      881M  117M  703M  15% /boot
/dev/vda15      105M  6.2M   99M   6% /boot/efi
```

*(Insert terminal screenshots here)*

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
