# Remote Control Server

Network services, which provide a Web UI on the managed machines, for remote
management/monitoring of those machines, and not just for servers, e.g.
- Allowing safer shutdown/reboot of a machine after something has gone badly wrong.
- Not SSH, because that may not be able to gather as much information, even with a rich client.

## → [Cockpit](/software/services/cockpit.md)

> Cockpit is a web-based graphical interface for servers, intended for everyone.

I've stopped using this because of WTF service failures, which I couldn't fix!
- Uninstallation was a disaster!
- `apt purge` failed to roll its configuration back to normal locations, so lots of junk directories are left, e.g:
    - It fails to push its Samba included configuration back to the normal Samba configuration files.
    - It fails to convert samba registry back to file based configuration, so this has to be done manually!

## → [Webmin](/software/services/webmin.md)

> Webmin is a web-based system administration tool for Unix-like servers, and services with about 1,000,000 yearly installations worldwide. Using it, it is possible to configure operating system internals, such as users, disk quotas, services or configuration files, as well as modify, and control open-source apps, such as **BIND** DNS Server, **Apache** HTTP Server, **PHP**, **MySQL**, and many more.

- My replacement for `Copilot`.
- Cons:
    - No usable ZFS support.
    - No BTRFS support found so far.
