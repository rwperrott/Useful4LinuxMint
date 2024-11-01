# .deb, the default package format for all Debian-based distributions.

The file is an (t)ar archive with a magic value of !<arch>. Only the common (t)ar archive format is supported,
with no long file name extensions, but with file names containing an optional trailing slash,
which limits their length to 15 characters (from the 16 allowed). File sizes are limited to 10 ASCII decimal digits,
allowing for up to approximately 9536.74 MiB member files.


## Tools
| Console Tools                | Description                                                                                                  |
|------------------------------|--------------------------------------------------------------------------------------------------------------|
| [dpkg](../console/dpkg.md)   | A Debian too tool to install, build, remove and manage Debian packages.                                      |
| apt-get                      | A Debian tool tool download/installe/update/remove debs.                                                     |
| apt                          | An Ubuntu tool to download/install/update/remove debs.                                                       |
| aptitude                     | A Gnome(?) tool to download/install/update/remove debs.                                                      |
| [nala](../console/nala.md)   | An alternative, python-based, to concurrent-download and install/update/remove debs.                         |
| [alien](../console/alien.md) | A tool for converting to/from deb and other packaging, including .rpm, .slp (Stampede), .pkg (Solaris), etc. | 

| GUI Tools | Description                                                                        |
|-----------|------------------------------------------------------------------------------------|
| synaptic  | A GTK GUI allowing repo setup/search, filtering, and batch installing/uninstalling |

### Installing a downloaded .deb file



## Package Pinning, i.e. setting search priority

- See `{name}.pref` files in `/etc/apt/preferences.d/ directory.

# Entry Format:
| Line name    | Example                 | Description                                                                                      |
|--------------|-------------------------|--------------------------------------------------------------------------------------------------|
| Package      | Package: *              | wildcard or package name, even a key package for the repo                                        |
| Pin          | Pin: origin {repo name} | Origin is the address of the repo                                                                |
| Pin-Priority | 100                     | 1 = do not auto-update<br>100 = update if not in other repos<br/>over 100 = overwrite base repos |

Example: all packages, from volian.pref, priority 100
```pref
Package: *
Pin: origin deb.volian.org
Pin-Priority: 100
```


## References
- [dpkg-dev/deb(5)](https://manpages.debian.org/unstable/dpkg-dev/deb.5.en.html) man file
- [deb (file format)](https://en.wikipedia.org/wiki/Deb_(file_format))
- [Using 3rd Party Repositories](https://wiki.debian.org/DebianRepository/UseThirdParty)
- [What is APT-Pinnig and how to ajust pin-priority?](https://forums.linuxmint.com/viewtopic.php?t=95013)
