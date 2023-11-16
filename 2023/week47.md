# Week 47

## What is OpenStack?

OpenStack is a collection of open-source projects designed to work together to form the basis of a cloud. OpenStack can be used for both private and public cloud implementation.

## The following hypervisors are supported

KVM - Kernel-based Virtual Machine. The virtual disk formats that it supports is inherited from QEMU since it uses a modified QEMU program to launch the virtual machine. The supported formats include raw images, the qcow2, and VMware formats.

LXC - Linux Containers (through libvirt), used to run Linux-based virtual machines.

QEMU - Quick EMUlator, generally only used for development purposes.

VMware vSphere 5.1.0 and newer - Runs VMware-based Linux and Windows images through a connection with a vCenter server.

Hyper-V - Server virtualization with Microsoft Hyper-V, use to run Windows, Linux, and FreeBSD virtual machines. Runs nova-compute natively on the Windows virtualization platform.

Virtuozzo 7.0.0 and newer - OS Containers and Kernel-based Virtual Machines supported. The supported formats include ploop and qcow2 images.

zVM - Server virtualization on z Systems and IBM LinuxONE, it can run Linux, z/OS and more.

Ironic - OpenStack project which provisions bare metal (as opposed to virtual) machines.
