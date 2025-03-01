# Service Software

## Hardware

### → [Audio](services/_audio.md)
I am only aware of PulseAudio and PipeWire; but their maybe others. Other audio APIs, include ALSA and JACK. 

---

## Cooling

### [Cooler Control](services/cooler-control.md)
> CoolerControl is a feature-rich cooling device control application for Linux. It has a system daemon
> for background device management, as well as a GUI to expertly customize your settings.
> For modulating CPU Water Cooler Pump and Fan(s), and GPU Heatsink Fan(s) speeds.
> Provides both web and desktop UIs.

---

## Platform Translation

### → [Wine](/software/services/wine.md)
- Wine is not an emulator (at least not on i386/AMD64 CPU machines), or a container or hypervisor service,
instead it is a service and console applications providing a translation layer allowing Windows software to run on Linux.
- Wine can't run Windows services!
- There does seem to be some just-in-time compilation/provisioning going on the background. 
- The translation can be imperfect, but can work surprisingly well.
- It can access serial ports, including USB ones, but it annoyingly requires registry editing, with no GUI support for this!
- Annoyingly USB port support, which probably needs exclusive access, would still seem to be missing, despite suggestions otherwise!

---

## → [Remote Control](services/_remote-control.md)

Network services, which may provide a Web UI, or just a network API, used for remote
management/monitoring of machines, not just for servers, e.g.
- Allowing safe shutdown if a desktop machine Desktop UI becomes unusable; safer than hard reset or power-off!

## → [Copilot](services/cockpit.md) 👎

I've stopped using this because of WTF service failures, which I couldn't fix!
- Uninstallation was a disaster!
- Purge does not roll its configuration back to normal locations, so lots of junk directories are left, e.g:
  - It fails to push its Samba included configuration back to the normal Samba configuration files.
  - It fails to convert samba registry back to file based configuration, so this has to be done manually!

## → [Webmin](https://webmin.com/)

Webmin is a web-based system administration tool for Unix-like servers, and services with about 1,000,000 yearly installations worldwide. Using it, it is possible to configure operating system internals, such as users, disk quotas, services or configuration files, as well as modify, and control open-source apps, such as **BIND** DNS Server, **Apache** HTTP Server, **PHP**, **MySQL**, and many more.

- My replacement for `Copilot`.
- Cons:
  - No usable ZFS support.
  - No BTRFS support found so far.

---

## → [Remote Desktop]

- VNC and RDP often have support consistency issues on Linux, so are not recommended!

### → [NoMachine](https://www.nomachine.com/)

More CPU intensive than VNC or RDP, but just-works across multiple OS.
- Server was easy to get working on Linux, unlike VNC and RDP.
- A working android client exists, but is less powerful than desktop OS clients, has some bugs.
- Feature rich; possibly better than RDP, e.g.!
  - Servers advertise on LAN, so less connection setup needed. 
  - The ability to mount client directories on a target machine.
  - The ability to mount target directories on a client machine.
- Cons
  - Server and target server configuration could be better.

---

## → [Container](services/_container.md)

Stuff like Docker, Podman, and Kubernetes for running OCI images.

---

## → [Hypervisor (type 2) ~ Virtual Machine ~ Virtualisation](services/_hypervisor.md) 

Server software, which allows running software an OS in an isolated environment,
this can allow injection of access to some system resources e.g.
- Rationed CPU use.
- Rationed GPU use, by whole cores, or sharing.
- Memory, a set amount of memory for it exclusive use.
- Storage
    - Virtual drive on a file.
    - iSCSI network drive
    - Real drive access.
    - Maybe simulated CIFS shares for host directory access.
- Desktop - sometimes via a remote desktop server.
- Network
  - Simulating a NIC, with own MAC address/IP.
  - Bridging/NAT across host existing NAT.
  - Simulating a NIC on a virtual host-only network.
