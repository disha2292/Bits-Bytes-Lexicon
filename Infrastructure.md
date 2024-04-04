## Proxmox :
Proxmox Virtual Environment (Proxmox VE or PVE) is a robust virtualization platform designed for the provisioning of hyper-converged infrastructure. It offers features for deploying and managing virtual machines (VMs) and containers, providing flexibility and efficiency in resource utilization.

Key features of Proxmox include:

1. **Virtualization Support**: Proxmox supports two types of virtualization: container-based virtualization using Linux Containers (LXC) and full virtualization using Kernel-based Virtual Machine (KVM). This versatility allows users to choose the most suitable virtualization method based on their requirements.

2. **Web-based Management Interface**: Proxmox VE offers a user-friendly web-based management interface, making it easy to configure, monitor, and manage virtualized environments. This interface provides comprehensive control over VMs, containers, storage, networking, and other aspects of the virtual infrastructure.

3. **Mobile Application**: Proxmox also offers a mobile application that allows users to manage their Proxmox environments from their smartphones or tablets. This provides convenient remote management capabilities, enabling administrators to monitor and control their virtualized infrastructure on the go.

4. **Open Source Licensing**: Proxmox VE is released under the terms of the GNU Affero General Public License (AGPL), version 3. This means that the software is open source and freely available, allowing users to access, modify, and distribute the source code according to the provisions of the license.

5. **Hyper-converged Infrastructure**: Proxmox VE is designed for hyper-converged infrastructure (HCI), which integrates compute, storage, and networking resources into a single platform. This consolidation simplifies management and improves resource utilization, making it an ideal solution for virtualization in data centers and enterprise environments.

Overall, Proxmox VE provides a powerful and flexible virtualization platform that combines ease of use with advanced features, making it suitable for a wide range of virtualization and cloud computing use cases.


## Hyper-converged Infrastructure :

Hyper-converged infrastructure (HCI) is a software-defined IT infrastructure in which compute, storage, networking, and virtualization resources are integrated into a single, unified system managed through a common toolset. The term "hyper-converged" highlights the consolidation of these traditionally disparate components into a cohesive and tightly integrated platform.

In a hyper-converged infrastructure:

1. **Compute**: This refers to the processing power provided by physical servers or nodes within the infrastructure. These servers run virtualization software to create and manage virtual machines (VMs) and containers.

2. **Storage**: Storage resources are pooled together from the local storage drives of each server in the HCI cluster. These drives contribute to a shared storage pool, which is then abstracted and managed through software-defined storage (SDS) technologies. This allows for flexible allocation and management of storage capacity and performance across the infrastructure.

3. **Networking**: Networking capabilities are also integrated into the hyper-converged infrastructure, facilitating communication between the various components and enabling data transfer between VMs, containers, and external networks.

4. **Virtualization**: Hyper-converged infrastructure relies on virtualization technologies to abstract and virtualize compute, storage, and networking resources. This enables the creation and management of multiple virtualized instances (VMs or containers) on the same physical hardware.

The benefits of hyper-converged infrastructure include simplified management, improved scalability, reduced hardware footprint, and enhanced resource utilization. By consolidating compute, storage, and networking functions into a single platform, HCI solutions streamline deployment and operations, making them well-suited for virtualization, cloud computing, and data center modernization initiatives.

## Provisioning :
Provisioning is the process of creating and setting up IT infrastructure, and includes the steps required to manage user and system access to various resources.
Provisioning is an early stage in the deployment of servers, applications, network components, storage, edge devices, and more.


## Bare metal : 
"Bare metal" refers to a physical computer or server without any installed operating system or virtualization layer. In other words, it refers to the raw, underlying hardware of a computer system.

When we say a hypervisor like VMware ESXi or Proxmox VE runs on "bare metal," it means that it runs directly on the physical hardware without the need for an intermediate operating system. Bare metal hypervisors are installed directly onto the hardware, typically via bootable media like a USB drive or CD/DVD, and they manage the hardware resources (such as CPU, memory, storage, and networking) to provide virtualization capabilities.

Bare metal hypervisors are designed to maximize performance and efficiency by eliminating the overhead of a traditional operating system layer. This allows for better resource utilization and performance for virtualized workloads.

In contrast, traditional operating systems like Windows or Linux are installed on top of the bare metal hardware and require direct access to hardware resources. Virtualization software, if used with these operating systems, typically runs as an application or service within the operating system, rather than directly on the hardware.

Overall, "bare metal" refers to the lowest level of the computing stack—the physical hardware itself—and "bare metal hypervisor" specifically denotes a hypervisor that runs directly on this hardware, providing virtualization capabilities without the need for a separate operating system layer.



## GPU passthrough
GPU passthrough, in the context of virtualization, refers to the process of dedicating a physical GPU (Graphics Processing Unit) to a virtual machine (VM). This allows the VM to have direct access to the GPU, enabling it to fully utilize the graphics capabilities of the hardware.

Here's how GPU passthrough typically works:

1. **Host Setup**: The host system (the physical machine running the hypervisor) must have compatible hardware and software support for GPU passthrough. This includes having an IOMMU (Input/Output Memory Management Unit) enabled in the BIOS/UEFI firmware and support for virtualization extensions like Intel VT-d or AMD-Vi.

2. **Guest VM Configuration**: You create a virtual machine and configure it to support GPU passthrough. This involves specifying the GPU device to be passed through to the VM and configuring the VM to use the appropriate virtualization technology (e.g., KVM/QEMU, VMware, VirtualBox) that supports GPU passthrough.

3. **Driver and Configuration**: In the host system, you need to install and configure the necessary drivers (such as VFIO) to manage the GPU passthrough. These drivers help bind the physical GPU to the VM and ensure proper communication between the VM and the GPU.

4. **GPU Binding**: The GPU is bound to the VFIO driver on the host system, effectively detaching it from the host OS and making it available exclusively to the VM.

5. **VM Execution**: When the VM starts, it detects and uses the dedicated GPU as if it were running on physical hardware. The VM has direct access to the GPU's resources, enabling high-performance graphics rendering and GPU-accelerated applications within the VM.

GPU passthrough is commonly used in scenarios where high-performance graphics or GPU-intensive applications need to run within a virtualized environment, such as gaming, CAD/CAM, machine learning, or video rendering. It provides better performance and compatibility compared to emulated or virtualized graphics solutions. However, GPU passthrough requires careful configuration and compatible hardware to ensure reliable operation.
