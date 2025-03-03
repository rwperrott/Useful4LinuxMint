# [Double Commander](https://doublecommander.com/)

On [Sourceforge](https://sourceforge.net/projects/doublecmd/)

> Double Commander is a cross-platform open source file manager with two panels side by side.
> It is inspired by Total Commander and features some new ideas.

## Features

-   Unicode support
-   Tabbed interface
-   Multi-rename tool
-   Custom columns
-   Built in file viewer (F3) to view files of in hex, binary or text format
-   Internal text editor (F4) with syntax hightlighting
-   Archives are handled like subdirectories. You can easily copy files to and from archives. Supported archive types: ZIP, TAR, GZ, BZ2, XZ, ZST, LZMA, 7Z and also RPM, CPIO, DEB, RAR, ZIPX
-   Most operations working in background
-   Extended search function with full text search in any files
-   Configurable button bar to start external programs or internal menu commands
-   Total Commander WCX, WDX, WFX and WLX plug-ins support
-   FTP, FTPS, FTPES, SSH+SCP and SFTP protocols support

## Useful keybindings
- F5 Copy
  - **Beware**, not to assume that this refreshes a tab, like it does in other file manager.
  - A tab refresh is requested via a right-click menu entry.
- F6 Move
- F8 Delete

## Notes

- I uninstalled the `qt5` (dated!) build, and installed the `gtk2` (dated!) build, because some dialogs in the didn't render correctly in the `QT5` build one, making it unusable.
- I moved to the `gtk2` (dated!) version, because it fully works.
- Best to install via apt, not AppImage, because of recent enough versions on current Linux Mint version!
- Surprisingly powerful, … once you get used to it.
- It actually remembers the open tabs properly on the next open, unlike Xfce's Thunar!

# Cons
- No hand-holding for the sometimes confusing configuration!:
  - One confusing oddity was that he rename command is actually a move command!
  - Adding new buttons was a learning curve, because of no icon name palette, and not opening the directory for an icon where icons are normally stored.
  - Reading the online documentation is necessary for the internal commands.
  - Adding favourite tabs was needlessly hard, and should allow editing of each tab, not full-overwrite to update!
- If transferring a file(s) to/from a busy CIFS/Samba server, attempts to change directory or get meta-data will be blocked until the server gets a chance to respond, making it seem like the tab is locked.
  - A workaround of mine was to pause such transfers, to free up the server to respond.
