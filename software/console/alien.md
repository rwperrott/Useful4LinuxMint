# alien

- TODO: may need more tidy up or content.

Alien is a computer program that converts between different Linux package formats, created by Joey Hess and presently maintained by Kyle Barry.[1]

## Features

Alien supports conversion between Linux Standard Base (LSB), LSB-compliant .rpm packages,[2] .deb, Stampede (.slp), Solaris (.pkg) and Slackware (.tgz, .txz, .tbz, .tlz)[3] packages. It is also capable of automatically installing the generated packages, and can try to convert the installation scripts included in the archive as well. Automatic installation should be used with caution since Linux distributions may vary significantly from one another, and using install scripts automatically converted from an Alien format may break the system.
Usage

A sample usage of Alien:

```shell
$ alien --to-rpm --scripts ./mypkg.deb
```

This will convert mypkg.deb to mypkg.rpm with the preinst, postinst, prerm and postrm scripts from the Debian package (deb) into the RPM package.

Terminal commands for Alien:
```shell
$ alien ${filename}.rpm # Rpm to Deb

$ alien -k ${filename}.tar.gz # Tar.gz to Deb

$ alien -d ${filename}.tar.bz2 # Tar.bz2 to Deb

$ alien --to-deb ~/${filename}.tgz # Tgz to Deb

$ alien -r ${filename}.deb
```

It might require `root` user or permissions to run the command. If it does then proceed with the commands below.
```shell
$ sudo alien ${filename}.rpm # Rpm to Deb

$ sudo alien -k ${filename}.tar.gz # Tar.gz to Deb

$ sudo alien -d ${filename}.tar.bz2 # Tar.bz2 to Deb

$ sudo alien --to-deb ~/${filename}.tgz # Tgz to Deb

$ sudo alien -r ${filename}.deb
```

# Similar applications

- CheckInstall, for the source tarball (i.e. Gentoo) to .deb (Debian).

External Resources (no links)
- "Official website". sourceforge.io.
- "Previous page for Alien by Joey Hess". joeyh.name. Retrieved 2018-03-08.
- "alien(1)". manpages.debian.org.
- "alien(1)". manpages.ubuntu.com.
- "fakeroot(1)". manpages.debian.org. "an alien helper utility"