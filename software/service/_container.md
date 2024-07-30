# Container server software

Some of these run these containers inside at least one hypervisor, and some rudely hog the hypervisor, like Docker Desktop does!

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