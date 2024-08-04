# Hypervisor Server

# KVM
> A Kernel-based Virtual Machine (KVM) built into Linux, its biggest advantage.
> You can run VMs out of the box on Linux with KVM. It is a type-1 hypervisor i.e. hardware-based.
>
> KVM converts the Linux host to a hypervisor to run virtual machines with bare metal like performance.

# → [Oracle VirtualBox](/software/desktop/virtualbox.md)

> VirtualBox is a top-rated open-source virtual machine program for Linux, Windows, and macOS.
>
> It is suitable for all kinds of users, whether you are just someone who wants to run Linux on a virtual machine,
> a professional who wants to create a VM for testing, or an enterprise that needs a VM solution.
>
> You can consider it as an all-in-one solution for most users. Even though it is primarily fit for desktop usage, you can try its headless mode to run a virtual machine as a remote desktop server by exploring its documentation.
>
> Key Highlights:
> - It supports a wide range of guest operating systems
> - Simple user interface and fast performance
> - Regularly updated
> - Feature-rich

# [Gnome Boxes](https://wiki.gnome.org/Apps/Boxes)

> Key Highlights:
> - Modern UX
> - Simple and easy to use
>
> GNOME Boxes is the simplest virtualization program for users looking to download test distros as quickly as possible.
>
> Compared to some other solutions, GNOME Boxes may not feature all kinds of features but the essentials. The user experience is simple, and it is easy to use for newbies.

Wow, _it is easy to use_! It looks like a frontend for qemu.

For v46.0 deb, on Mint 22
```shell
sudo apt install gnome-boxes
```

or

For v46.0 flatpak
```shell
flatpak install org.gnome-boxes
```

# [QEMU](https://www.qemu.org/)

> QEMU is a nice virtual machine program (and emulator) available across multiple platforms.
>
> It supports a wide range of hardware architectures and guest operating systems. You can couple it with KVM to run VMs that perform well because KVM is a hardware-level virtualization tool, and QEMU is a software-level virtualization program.
>
> Technically, QEMU is a type-2 hypervisor.
>
> If you want a tool that utilizes QEMU at its core and makes it easy for beginners to create virtual machines, you can explore Quickgui.
>
> Key Highlights:
>
> - Wide range of operating system support
> - It provides flexibility without depending on your hardware
>