# Software packaging

**TODO: consider splitting this**

## Deb `.deb`

The native packaging format for Debian, Ubuntu, and Mint Linux distributions.

### Installers

- apt-get (Debian)
- apt (Ubuntu → Mint)
- [nala](/software/console/nala.md)

## Archive releases

### Binary releases

These maybe runnable as-is, e.g. for Ventoy.
tor-browser is also provided this way.

### Source code releases

These can be problematic to build and install
- Some developers don't tell you, or don't provide sufficient dependency information.
- When not enough information it can be hard to figure out what needs installing from the compilation/build errors. Typically it is dev library needed.  
- the required dependencies may not even be available for the required version or may need a bridging component for out-of-date API calls! 

## Other Portable formats

This always come bundled with extra software, some maybe shared, but can take up a lot more diskpace and memory than native apps!  

### [Flatpak](/software/packaging/flatpak.md)

Packages an applications with extra files to make cover for OS differences;
often quite bloated compared to proper OS repository installed applications.
**TODO: decide if need a separate file and what links I need; may need

### [AppImage](/software/packaging/appimage.md)

Packages an applications with extra files to make cover for OS differences, as a disk image, run via a Fuse mount; often more usable and not as bloated as Flatpak applications. The format seems to be less popular than Flatpak, and release can be quite out of date, when not provided directly by software developers. 

