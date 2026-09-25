# Performance Analysis of Type-1 and Type-2 Hypervisors

## 1. Introduction

This experiment focuses on the performance analysis of virtual machines running on two different types of hypervisors.

The experiment uses:

* **Proxmox VE** as a Type-1 hypervisor
* **VMware Workstation** as a Type-2 hypervisor
* **Ubuntu** as the guest operating system
* **Sysbench** for CPU performance benchmarking

Both virtual machines are configured with similar hardware resources so that their CPU performance can be compared.

---

## 2. Objectives

The objectives of this experiment are:

1. To create a virtual machine using Proxmox VE.
2. To create a virtual machine using VMware Workstation.
3. To configure both virtual machines with comparable hardware resources.
4. To verify CPU, memory and disk configurations.
5. To install and use Sysbench for CPU benchmarking.
6. To record the benchmark results.
7. To compare the performance of Type-1 and Type-2 hypervisors.

---

## 3. Experimental Configuration

| Resource               | Configuration                            |
| ---------------------- | ---------------------------------------- |
| Guest Operating System | Ubuntu                                   |
| CPU                    | 2 vCPU                                   |
| Memory                 | 2 GB                                     |
| Disk                   | 20 GB                                    |
| CPU Benchmark          | Sysbench                                 |
| Benchmark Command      | `sysbench cpu --cpu-max-prime=20000 run` |

---

# 4. Part A - Proxmox VE (Type-1 Hypervisor)

## 4.1 Proxmox VE

Proxmox VE is used as the Type-1 hypervisor for the first part of the experiment.

A virtual machine is created with the following configuration:

| Parameter       | Configuration |
| --------------- | ------------- |
| Hypervisor      | Proxmox VE    |
| Hypervisor Type | Type-1        |
| Guest OS        | Ubuntu        |
| CPU             | 2 vCPU        |
| Memory          | 2 GB          |
| Disk            | 20 GB         |
| Network         | vmbr0         |

## 4.2 Ubuntu Verification

The Ubuntu virtual machine configuration is verified using:

```bash
hostnamectl
```

The CPU configuration is checked using:

```bash
lscpu
```

Memory information is checked using:

```bash
free -h
```

Disk information is checked using:

```bash
df -h
```

System resource utilization is monitored using:

```bash
top
```

## 4.3 Sysbench Installation

Sysbench is installed using:

```bash
sudo apt update
sudo apt install sysbench -y
```

The installation is verified using:

```bash
sysbench --version
```

## 4.4 CPU Benchmark

The CPU benchmark is executed using:

```bash
sysbench cpu --cpu-max-prime=20000 run
```

## 4.5 Type-1 Results

The actual benchmark values obtained from the Proxmox VE virtual machine will be recorded below.

| Metric               | Proxmox VE     |
| -------------------- | -------------- |
| Total Execution Time | 10.00045s      |
| Total Events         | 13,941         |
| Events per Second    | 1,393.89       |
| Minimum Latency      | 0.68 ms        |
| Average Latency      | 0.72 ms        |
| Maximum Latency      | 0.78 ms        |

---


# 5. Part B - VMware Workstation (Type-2 Hypervisor)

## 5.1 VMware Workstation

VMware Workstation is used as the Type-2 hypervisor for the second part of the experiment.

A virtual machine is created with a configuration comparable to the Proxmox VE virtual machine.

| Parameter       | Configuration      |
| --------------- | ------------------ |
| Hypervisor      | VMware Workstation |
| Hypervisor Type | Type-2             |
| Guest OS        | Ubuntu             |
| CPU             | 2 vCPU             |
| Memory          | 2 GB               |
| Disk            | 20 GB              |
| Network         | NAT                |

## 5.2 Ubuntu Verification

The Ubuntu virtual machine configuration is verified using:

```bash
hostnamectl
```

The CPU configuration is checked using:

```bash
lscpu
```

Memory information is checked using:

```bash
free -h
```

Disk information is checked using:

```bash
df -h
```

System resource utilization is monitored using:

```bash
top
```

## 5.3 Sysbench Installation

Sysbench is installed using:

```bash
sudo apt update
sudo apt install sysbench -y
```

The installation is verified using:

```bash
sysbench --version
```

## 5.4 CPU Benchmark

The CPU benchmark is executed using:

```bash
sysbench cpu --cpu-max-prime=20000 run
```

## 5.5 Type-2 Results

The actual benchmark values obtained from the VMware Workstation virtual machine will be recorded below.
| Metric | Proxmox VE |
|---|---:|
| Total Execution Time | 10.0007 s |
| Total Events | 17,193 |
| Events per Second | 1,719.32 |
| Minimum Latency | 0.56 ms |
| Average Latency | 0.59 ms |
| Maximum Latency | 2.81 ms |
| 95th Percentile | 0.67 ms |

---
### Sysbench Benchmark Output

![VMware Sysbench Benchmark](Part-B-VMware-Type-2/Screenshot%202026-09-21%20162721.png)
---
# 6. Performance Comparison

The benchmark results obtained from both virtual machines will be compared using the following parameters:

| Performance Metric   | Proxmox VE     | VMware Workstation |
| -------------------- | -------------- | ------------------ |
| Hypervisor Type      | Type-1         | Type-2             |
| CPU                  | 2 vCPU         | 2 vCPU             |
| Memory               | 2 GB           | 2 GB               |
| Disk                 | 20 GB          | 20 GB              |
| Total Execution Time | To be recorded | To be recorded     |
| Total Events         | To be recorded | To be recorded     |
| Events per Second    | To be recorded | To be recorded     |
| Average Latency      | To be recorded | To be recorded     |

The comparison will be based on the actual Sysbench measurements obtained during the experiment.

---

# 7. Conclusion

This experiment provides a practical comparison of virtual machine CPU performance using a Type-1 hypervisor and a Type-2 hypervisor.

Proxmox VE and VMware Workstation are configured with comparable virtual hardware resources, and Sysbench is used to obtain CPU benchmark measurements.

The final conclusion will be based on the measured performance results from both environments.
