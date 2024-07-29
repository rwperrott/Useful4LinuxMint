# Virtualisation Server

## Flatpak
Packages an applications with extra files to make cover for OS differences;
often quite bloated compared to proper OS repository installed applications. 

## AppImage
Packages an applications with extra files to make cover for OS differences, as a disk image, run via a Fuse mount;
often more usable and not as bloated as Flatpak applications.

## Docker
A bare-bones image creator command, using a layered filesystem, with injectable environment variables,
storage mounts and network port mappings.
Also, associated with a root-user server, which can create a container for an images and run it.
Docker Desktop provides a management server and GUI,
*however* this can annoyingly claim exclusive access to OS hypervisor functionality.
Both popular tools for DevOps and Platform Engineering.
The images created by the image creator command can also be used by kubernetes, Podman.

## Podder
A server with a web UI for managing a docker server, without the need the problematic Docker Desktop.

## Podman
A user-space container host challenger to the Docker root-user server.
This makes it more secure, because it won't be able to cause any root-user damage if container isolation fails.

## → [Wine](/software/wine.md)
Wine (originally an acronym for "Wine Is Not an Emulator") is a compatibility layer
able to run Windows applications on several POSIX-compliant operating systems,
such as Linux, macOS, & BSD. Instead of simulating internal Windows logic,
like a virtual machine or emulator, Wine translates Windows API calls into POSIX calls, on-the-fly.
This eliminates the performance and memory penalties of other methods
and allowing you to cleanly integrate Windows applications into your desktop.

# Hypervisor
