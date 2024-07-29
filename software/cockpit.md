# [Cockpit](https://cockpit-project.org/)

Cockpit is a web-based graphical interface for servers, intended for everyone, especially those who are:
- new to Linux (including Windows admins).
- familiar with Linux and want an easy, graphical way to administer servers.
- expert admins who mainly use other tools but want an overview on individual systems.

Thanks to Cockpit intentionally using system APIs and commands, 
a whole team of admins can manage a system in the way they prefer, 
including the command line and utilities right alongside Cockpit.

- The login prompt uses OS username and password, so these must be secure, especially for users who can run sudo!
- It has a simulated terminal console, so console commands like apt and nano can be run via it.
- It snapshots incidents of an excessive system load, and can graph this;
I don't know it the offenders can be identified from this.
- It supports remote machine reboot. 
- I even have a copy installed on a Raspberry Pi B+, for easier management.

# [Installation](https://cockpit-project.org/running.html#ubuntu)

- For Linux Mint 21
    ```shell
    sudo apt install -t jammy-backports cockpit
    ```

- For Linux Mint 22
    ```shell
    sudo apt install -t noble-backports cockpit
    ```

# [Applications](https://cockpit-project.org/applications.html) (functionality extensions)

Cockpit also supports a large list of optional and third-party applications.

- Some of these may require more work to install, even manual build and install from a GitHub repository source-release. 
