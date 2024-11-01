# dpkg

- Added so that I don't have to reopen multiple webpages to see this all; web pages often being hideously bloated, with js frameworks and tracking! 
- TODO: Merge all of this into something a lot more usable, if useful enough to me.

## Baeldung - [Guide to Linux dpkg Command With Examples](https://www.baeldung.com/linux/dpkg-tutorial)
Last updated: May 22, 2024
Written by: Gbenga Oyatoye
Reviewed by: Hiks Gerganov

### 1. Overview

dpkg is the core package manager for Debian-based Linux systems, streamlining software package installation, removal, and administration. Moreover, the tool can conduct essential tasks such as unpacking, configuring, and maintaining a package database.

In this tutorial, we’ll examine the functions of the dpkg command and how to utilize it efficiently. Additionally, we’ll offer some examples to get acquainted with this tool under Linux.
### 2. Syntax

Understanding the basic operations of dpkg is essential for any Linux user. This is especially so since this command forms the basis for managing software packages in Linux.

The basic syntax of dpkg comprises two parameters:

dpkg [options] [package.deb|package-name]

Now that we’ve seen the syntax, let’s understand these parameters:

    [options]: flags to alter its behavior and output
    [package.deb|package-name]: packages to be applied to the command

Let’s see a breakdown of the most commonly used commands and their functions:
Options 	Description
-i 	 Install a package
-r 	 Remove a package
-l 	 list of installed packages
-s 	 Show information about a specific installed package
-C 	 Check for broken dependencies
-L 	 List files installed by a package
-P 	 Purge package configuration files
-A 	 Configure all unpacked but unconfigured packages

Next, we proceed to apply this command to deb packages in practice.
### 3. Basic Usage

As we already saw, the dpkg command has many options with different functions.
### 3.1. The -i Option

The -i option instructs the dpkg command to install a deb software package.

For example, we can install the jed programmers editor via its deb package:

```shell
$ sudo dpkg -i jed_0.99.20\~pre.181+dfsg-1_amd64.deb
[sudo] password for kali:
(Reading database ... 518829 files and directories currently installed.)
Preparing to unpack jed_0.99.20~pre.181+dfsg-1_amd64.deb ...
Unpacking jed (1:0.99.20~pre.181+dfsg-1) over (1:0.99.20~pre.178+dfsg-6) ...
Setting up jed (1:0.99.20~pre.181+dfsg-1) ...
Updating precompiled files... done
Processing triggers for kali-menu (2023.4.7) ...
Processing triggers for desktop-file-utils (0.27-1) ...
Processing triggers for mailcap (3.70+nmu1) ...
Processing triggers for hicolor-icon-theme (0.17-2) ...
Processing triggers for man-db (2.12.0-3) ...
```

From the above result, we can see that the dpkg -i command initiated and guided the installation of the software.
### 3.2. The -r Option

Next, the -r option prompts the dpkg command to remove specified packages from the operating system.

Before removing the jed package we just installed, it’s good to check the dpkg.log file and identify installed packages on the Linux system. For example, we can check the most recent installed packages:

```shell
$ grep "install" /var/log/dpkg.log | tail
2024-05-13 18:54:24 status installed hicolor-icon-theme:all 0.17-2
2024-05-13 18:54:25 status installed man-db:amd64 2.12.0-3
2024-05-13 18:59:47 startup archives install
2024-05-13 18:59:48 status half-installed jed:amd64 1:0.99.20~pre.178+dfsg-6
2024-05-13 18:59:48 status installed jed:amd64 1:0.99.20~pre.181+dfsg-1
2024-05-13 18:59:48 status installed kali-menu:all 2023.4.7
2024-05-13 18:59:48 status installed desktop-file-utils:amd64 0.27-1
2024-05-13 18:59:48 status installed mailcap:all 3.70+nmu1
2024-05-13 18:59:48 status installed hicolor-icon-theme:all 0.17-2
2024-05-13 18:59:49 status installed man-db:amd64 2.12.0-3
```

The log shows part of all the installed packages; the grep command matches the pattern install within strings inside the dpkg.log file. Next, the tail command reveals ten lines of information at the bottom of the log, which are the latest installed packages.

Now that we have an idea of the installed packages and dependencies with the jed package, let’s remove the previously installed package:

```shell
$ sudo dpkg -r jed
[sudo] password for kali:
(Reading database ... 518829 files and directories currently installed.)
Removing jed (1:0.99.20~pre.181+dfsg-1) ...
update-alternatives: using /bin/nano to provide /usr/bin/editor (editor) in auto mode
Processing triggers for man-db (2.12.0-3) ...
Processing triggers for hicolor-icon-theme (0.17-2) ...
Processing triggers for desktop-file-utils (0.27-1) ...
Processing triggers for mailcap (3.70+nmu1) ...
Processing triggers for kali-menu (2023.4.7) ...
```

As a result of the -r option with the dpkg command, the jed package was removed from the system. We can check for removed packages by checking the dpkg.log file:

```shell
grep "remove" /var/log/dpkg.log | tail
2024-05-13 18:50:43 startup packages remove
2024-05-13 18:50:44 remove jed:amd64 1:0.99.20~pre.178+dfsg-6 <none>
2024-05-14 16:41:42 startup packages remove
2024-05-14 16:41:44 remove jed:amd64 1:0.99.20~pre.181+dfsg-1 <none>
```

Similar to the previous operation of checking recently installed packages, the command above shows the latest removed packages with the dpkg command. As shown in the result, the jed command was removed.

### 3.3. The -l Option

The -l option prompts the dpkg command to list all installed packages:

```shell
dpkg -l > instPacks.txt
```

So, we saved the list of installed packages into a file named instPacks.txt. Subsequently, we can view the content using the cat command:

```shell
$ cat instPack.txt
Desired=Unknown/Install/Remove/Purge/Hold
| Status=Not/Inst/Conf-files/Unpacked/halF-conf/Half-inst/trig-aWait/Trig-pend
|/ Err?=(none)/Reinst-required (Status,Err: uppercase=bad)
||/ Name                           Version                  Architecture Description
+++-===========================================================-==========================================================
ii  7zip                           23.01+dfsg-8             amd64        7-Zip file archiver with a high compression ratio
ii  accountsservice                23.13.9-6                amd64        query and manipulate user account information
ii  acl                            2.3.2-1                  amd64        access control list - utilities
ii  adduser                        3.137                    all          add and remove users and groups
ii  adwaita-icon-theme             46.0-1                   all          default icon theme of GNOME
ii  amass                          4.2.0-0kali1             amd64        In-depth DNS Enumeration and Network Mapping
...
```

From the result, we can see that the dpkg -l command not only outputs the installed packages but also adds a few other pieces of information:

    Desired
    Status
    Err?

These additions provide more details about the package. For example, we previously filtered the dpkg.log using two of the possible Desired values: install and remove.

### 3.4. The -s Option

Furthermore, we can show information about specific packages using the -s option of the dpkg command.

Let’s examine one of the installed packages from the previous list:

```shell
$ dpkg -s 7zip
Package: 7zip
Status: install ok installed
Priority: optional
...
Homepage: https://www.7-zip.org/
```

The output here is very long and contains detailed data about many aspects of the selected package. For example, package dependencies, who manages the package, its size, and many more were all included.
3.5. The -P Option

The -P option prompts the dpkg command to purge the package of all related files that were installed along with it:

```shell
$ sudo dpkg -P jed
[sudo] password for kali:
(Reading database ... 518818 files and directories currently installed.)
Purging configuration files for jed (1:0.99.20~pre.181+dfsg-1) ...
```

The command syntax above evaluates all installed packages before finally purging the jed configuration files.
### 4. Advanced Options

Now, we can advance the basic knowledge by looking at options that force, audit, and unpack packages.
### 4.1. Using Force Long Flags

Let’s use the force options with dpkg:

```shell
$ sudo dpkg --force-architecture --install jed_0.99.20.181_amd64.deb
[sudo] password for kali:
Selecting previously unselected package jed.
....
Preparing to unpack jed_0.99.20.181_amd64.deb ...
Unpacking jed (1:0.99.20~pre.181+dfsg-1) ...
...
Updating precompiled files... done
...
```

The –force-architecture makes dpkg force the installation of packages even if the architecture doesn’t match.

We can take a look at another force option that deals with versions:

```shell
$ sudo dpkg --install --force-confnew jed_0.99.20.181_amd64.deb
Selecting previously unselected package jed.
(Reading database ... 518818 files and directories currently installed.)
Preparing to unpack jed_0.99.20.181_amd64.deb ...
```

The above long flag, –force-confnew, forces dpkg to always use the new version of a configuration file during installation.
4.2. Using Audit Long Flags

The –audit option is used to check all installed packages for issues. These issues may include security vulnerabilities, dependency problems, file integrity, configuration, and consistency checks.

Let’s examine the usage of this option:

```shell
$ dpkg --audit
```

Notably, the command returned no output, meaning no issue was found.
### 4.3. Unpacking Packages

Finally, let’s understand how to unpack packages to get to their files and directories:

```shell
$ sudo dpkg --unpack jed_0.99.20.181_amd64.deb
(Reading database ... 518829 files and directories currently installed.)
Preparing to unpack jed_0.99.20.181_amd64.deb ...
Unpacking jed (1:0.99.20~pre.181+dfsg-1) over (1:0.99.20~pre.181+dfsg-1) ...
...
Processing triggers for man-db (2.12.0-3) ...
```

The command unpacked the jed deb package as shown above. Thus, we gained more insight into the various other dependencies that the package would install as well as the contents of its files and directories.
### 5. Conclusion

In the article, we discussed the basic syntax of using the dpkg command and its various common flags.

By adding flags, we modified the behavior of the dpkg command, thus affecting its output. Furthermore, we also demonstrated more use cases with long flags.

## wikepaedia
dpkg is the software at the base of the package management system in the free operating system Debian and its numerous derivatives. dpkg is used to install, remove, and provide information about .deb packages.

dpkg (Debian Package) itself is a low-level tool. APT (Advanced Package Tool), a higher-level tool, is more commonly used than dpkg as it can fetch packages from remote locations and deal with complex package relations, such as dependency resolution. Frontends for APT, like aptitude (ncurses) and synaptic (GTK), are used for their friendlier interfaces.

The Debian package "dpkg" provides the dpkg program, as well as several other programs necessary for run-time functioning of the packaging system, including dpkg-deb, dpkg-split, dpkg-query, dpkg-statoverride, dpkg-divert and dpkg-trigger. It also includes the programs such as update-alternatives and start-stop-daemon. The install-info program used to be included as well, but was later removed as it is now developed and distributed separately. The Debian package "dpkg-dev" includes the numerous build tools described below.

### History

The first attempt at a package management system for Linux was possibly the development of StopAlop by Greg Wettstein at the Roger Maris Cancer Center in Fargo, North Dakota. It provided inspiration for the creation of dpkg. dpkg was originally created by Ian Murdock in January 1994 as a Shell script. Matt Welsh, Carl Streeter and Ian Murdock then rewrote it in Perl, and then later the main part was rewritten in C by Ian Jackson in 1994. The name dpkg was originally a shortening of "Debian package", but the meaning of that phrase has evolved significantly, as dpkg the software is orthogonal to the deb package format as well as the Debian Policy Manual which defines how Debian packages behave in Debian.

### Example use

To install a .deb package:

```shell
dpkg -i filename.deb
```

where filename.deb is the name of the Debian package (such as pkgname_0.00-1_amd64.deb).

The list of installed packages can be obtained with:

```shell
dpkg -l [optional pattern]
```

To remove an installed package:

```shell
dpkg -r packagename
```

### Development tools

dpkg-dev contains a series of development tools required to unpack, build and upload Debian source packages.[16] These include:

| Tool                | Description                                                                                                                                             |
|---------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| dpkg-source         | packs and unpacks the source files of a Debian package.                                                                                                 |
| dpkg-gencontrol     | reads the information from an unpacked Debian tree source and generates a binary package control package, creating an entry for this in Debian/files.   |
| dpkg-shlibdeps      | calculates the dependencies of runs with respect to libraries.                                                                                          |
| dpkg-genchanges     | reads the information from an unpacked Debian tree source that once constructed creates a control file (.changes).                                      |
| dpkg-buildpackage   | is a control script that can be used to construct the package automatically.                                                                            |
| dpkg-distaddfile    | adds a file input to debian/files.                                                                                                                      |
| dpkg-parsechangelog | reads the changes file (changelog) of an unpacked Debian tree source and creates a conveniently prepared output with the information for those changes. |

### Database

The dpkg database is located under/var/lib/dpkg; the "status" file contains the list of installed software on the current system. There is no information about repositories in this database.[15]

### wpkg packager for Windows

This section is about wpkg, a look-alike of the debian dpkg packager. For WPKG, an unrelated packager for Microsoft Windows, see WPKG (software).

wpkg was created as a dpkg look-alike that would run under the Microsoft Windows operating system.[17] It subsequently evolved to include functionality similar to parts of the APT suite, improved repository management, distribution management and was ported to Linux and Unix-like systems, including Cygwin, Mingw32, macOS, OpenSolaris and FreeBSD.[18][19] It retains .deb file format compatibility[20] and is supplied with the ready-to-use executable wpkg.exe. As of March 2024, the most recent release of the software was in 2015.[18]

## [The dpkg Command in Linux - A Beginners Reference](https://www.digitalocean.com/community/tutorials/dpkg-command-in-linux)
- (partially trimmed of waffle and poor grammar)

Packages help in delivering or installing any application on a Linux system.
Essentially, packages are compressed archives of the files and dependencies required to install a program or service.

These packages are used when you want to install a new program or service on their system.
All the packages on a system are stored in a local ‘repository’.

This repository can be accessed by a package management service whenever required.
Let’s talk about one of those package management utilities, the dpkg command in Linux today.
What is the dpkg command?

Essentially, the man page describes it like this: “dpkg is a tool to install, build, remove and manage Debian packages.”

We use the dpkg command to interact with packages on our system. It is controlled fully with the help of command-line
parameters; the first parameter is the action parameter that is used to direct what to do.
This parameter may or may not be followed by any other parameter.

Later, a new tool named aptitude was designed to provide a more user-friendly, interactive front-end for the users to
manage packages without the complexity of the dpkg command. It interacts with the dpkg interface for the user.
Now, let’s try and understand the dpkg command in Linux.
Here’s what the basic syntax of the dpkg command looks like:

```shell
dpkg [options] [.deb package name]
```

The dpkg command provides a long list of options to customise the data we receive while analysing our network. Here is a list of some of the most popular dpkg options.

Option 	Function
-i OR --install 	Install a package using the dpkg command. The command will extract all control files for the specified package, remove any previously installed older instance of the package, and install the new package on our system.
-r OR --remove 	Remove an installed package from our system. It removes every file belonging to the specific package except the configuration files. This can be seen as the uninstallation option.
-P OR --purge 	An alternative way to remove an installed package from our system. It completely removes every fie belonging to the specific package, including the configuration files. This can be seen as the ‘complete uninstallation’ option.
--update-avail 	Uhe information of the dpkg command about available packages in its repositories. If new packages are available, they are synced from the official repositories.
--merge-avail 	Merge the information of the dpkg command about available packages in its repositories with previously available information. It is usually run right after the previous command.
--help 	Display the help page for the dpkg command and exit.

These are some of the most commonly used options for the dpkg command and you can explore more by displaying the help options in your terminal.
Using the dpkg command.

Let us explore the common uses of the dpkg command. As the command works the same for both Debian and Ubuntu systems, we will only mention Ubuntu in this tutorial from now on.
1. Installing a package

We can install a deb package in Ubuntu or Debian using the dpkg -i command option.

Here’s how you’d install a package.

```shell
sudo dpkg -i [package name]
```

You can also install multiple packages at the same time by specifiying the package names separated by spaces.
2. Removing a package

When you no longer need a program or service on your system, there is no use keeping it.

The dpkg command has got us covered here as well.

We can uninstall a program or service from our system using the dpkg -r option.

Let’s remove the VLC player that we installed for this demonstration.

```shell
sudo dpkg -r [package name]
```

3. Updating your repositories

The dpkg repository stores all the packages available for installation on your Ubuntu or Debian Linux distribution.

However, as these packages are stored locally you can often end up having old versions of packages for a program when newer versions have already been released. This causes a need for a method to update your repositories.

Guess what? The dpkg `--update-avail` option has got you covered.

It checks the online repositories and downloads all the updated packages to your local repository.

Let’s update our local repositories to the latest version:

```shell
sudo dpkg --update-avail
```
