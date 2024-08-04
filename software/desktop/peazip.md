# PeaZip

- [GitHub.io](https://peazip.github.io/index.html)
- [GitHub.com](https://github.com/peazip/PeaZip)

>What is PeaZip free file archiver utility
>
>PeaZip is a free file archiver utility, similar to WinRar, WinZip, and 7-Zip (or File Roller, and Ark on Linux), based on Open Source technologies of 7-Zip / p7zip archiver, Facebook Zstandard compressor, FreeArc, Google Brotli compressor, PAQ family of compressors, PEA (archiving and encryption) project, and other Free Software file compression tools.
>
>What is different in PeaZip?
>
>The project started aiming to provide features often overlooked in applications of the same type.
>
>- Be CLI-friendly: bridge the gap between GUI and CLI applications to offer the best of the two worlds, blending the archive manager into a scripting engine to automate compression / archiving / backup / extraction... tasks.
>
>- From "Console" tab in archiving and extraction screens, the tasks defined in the GUI can be exported as CLI scripts, i.e. for reuse, syntax learning or inspection purpose, of for refining the tasks beyond the capabilities of the GUI.
>
>- Offer two factor authentication (password + keyfile) for all formats supporting encryption, to increase security against guessing and dictionary based attacks on weak passwords.
>
>- Provide a GUI for less commonly supported compression formats - which comes from very interesting research threads in compression field, like the very powerful compressor zpaq or very fast ones as brotli, and zstandard - and provide a platform-agnostic GUI for 7z/p7zip on non-Windows systems.
>
>- Provide multiple file management features each of whom meeting the needs of different use cases, like verification of a wide array of checksum and hash functions, find duplicates, convert archives, search in archives, bookmarks, tabbed browsing, etc.
>
>- Deploy all the above in a tool which is natively portable, can be used from removable devices or shared on a network / cloud, without installation, and offers the same UX on all operating systems and desktop environments.
>
> bla....

## Installation

There appears to be no proper deb repository instructions.

See [GitHub.com releases](https://github.com/peazip/PeaZip/releases), pick either release:
- peazip_{version}.LINUX.Qt5-1_amd64.deb - _I suggest this one_
- peazip_{version}.LINUX.GTK2-1_amd64.deb)
