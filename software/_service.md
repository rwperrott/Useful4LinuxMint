# Service Software

## → [Audio](service/_audio.md)
I am only aware of PulseAudio and PipeWire, but their maybe others, 
other extra audio APIs, like ALSA and JACK. 

---

## → [Wine](/software/service/wine.md)
- Wine is not an emulator (at least not on i386/AMD64 CPU machines), or a container or hypervisor service,
instead it is a service and console applications providing OS API translation layer for running Windows software.
- Wine can't run Windows services!
- It can access serial ports, including USB ones, but it annoyingly requires registry editing, with no GUI support for this!
- Annoyingly USB port support, which probably needs exclusive access, would still seem to be missing, despite suggestions otherwise!

---

## → [Remote Control](service/_remote-control.md)

Network services, which may provide a Web UI, or just a network API, used for remote
management/monitoring of machines, not just for servers, e.g.
- Allowing safe shutdown if a desktop machine Desktop UI becomes unusable; safer than hard reset or power-off!

---

## → [Container](service/_container.md)

---

## → [Hypervisor (type 2) ~ Virtual Machine ~ Virtualisation](service/_hypervisor.md) 

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
