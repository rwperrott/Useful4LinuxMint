# Flatpak

- Packages an application to provide Linux distribution portability!
- The applications all run in separate sandboxes, with separate permissions.

- I dislike this format:
  - Because of the versioned dependence bloat.
  - It can't be run directly

- I prefer AppImage packaging to this.

---

- TODO: Add more details.

---

## Useful desktop Flatpak management applications:

### [Warehouse](https://flathub.org/apps/io.github.flattool.Warehouse)

[Homepage](https://flattool.github.io/warehouse/)

[GitHub](https://github.com/flattool/warehouse)

> Warehouse is a versatile toolbox and provides a simple UI to control complex Flatpak options, all without resorting to the command line.[](https://flattool.github.io/warehouse//#warehouse-is-a-versatile-toolbox-and-provides-a-simple-ui-to-control-complex-flatpak-options-all-without-resorting-to-the-command-line)

## 🚀 Main Features:[](https://flattool.github.io/warehouse//#-main-features)

1.  **Viewing Flatpak Info:** 📋 Warehouse can display all the information provided by the `Flatpak list` command in a user-friendly graphical window. Each item includes a button for easy copying.

2.  **Change Package Versions:** ↕️ Rollback any unwanted updates of any package, so long as the remote has older versions.

3.  **Managing User Data:** 🗑️ Flatpaks store user data in a specific system location, often left behind when an app is uninstalled. Warehouse can uninstall an app and delete its data, delete data without uninstalling, or simply show if an app has user data.

4.  **Batch Actions:** ⚡ Warehouse features a batch mode for swift uninstallations, user data deletions, and app ID copying in bulk.

5.  **Leftover Data Management:** 📁 Warehouse scans the user data folder to check for installed apps associated with the data. If none are found, it can delete the data or attempt to install a matching Flatpak.

6.  **Manage Remotes:** 📦 Installed and enabled Flatpak remotes can be deleted, and new remotes can be added.

7.  **Make Snapshots:** 🕐 Copy app user data to take quick backups before doing anything risky with your data.

---

### [FlatSeal](https://flathub.org/apps/com.github.tchx84.Flatseal)

[GitHub](https://github.com/tchx84/Flatseal)

> Flatseal is a graphical utility to review and modify permissions from your Flatpak applications.

---

### [FlatSweep](https://flathub.org/apps/io.github.giantpinkrobots.flatsweep)

[GitHub](https://github.com/giantpinkrobots/flatsweep)

> Flatpak leftover cleaner

