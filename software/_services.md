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

Access a remote machine via an administration webserver, hosted by it.

---

## → [Remote Desktop](services/_remote-desktop.md)

Access a remote machine's desktop, for viewing or GUI based control. 

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
