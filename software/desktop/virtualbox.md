# [Oracle VirtualBox](https://www.virtualbox.org/)

> VirtualBox is a powerful x86 and AMD64/Intel64 virtualization product for enterprise as well as home use.
> Not only is VirtualBox an extremely feature rich, high performance product for enterprise customers,
> it is also the only professional solution that is freely available as Open Source Software under
> the terms of the GNU General Public License (GPL) version 3.


### Installation of Ubuntu Provided Version

From the Ubuntu repository of a QT GUI version, so the extension pack was probably tested to fully work.

| Mint Version | VirtualBox Version |
|--------------|--------------------|
| 22           | 7.0.16             |

- I could run isos for earlier Linux Mint versions to see, which VirtualBox versions,
  they provide, but I doubt that it would be worth it for me.

1. Install using apt
    ```shell
    sudo apt install virtualbox virtualbox-ext-pack
    ```
2. Ensure that each user who will use `VirtualBox` has been added to the `vbusers` group, so that the extension pack works.
3. Reboot

Try using Virtual box.


### ..or..

### Installation of the Latest Version

From Oracle, **but** _the extension pack may not fully work_!

See, the Official Linux [Download](https://www.virtualbox.org/wiki/Linux_Downloads) page

1. Add Repository for Latest Version
    - For Mint 20 (Debian bullseye)
    ```shell
    deb [arch=amd64 signed-by=/usr/share/keyrings/oracle-virtualbox-2016.gpg] https://download.virtualbox.org/virtualbox/debian bullseye contrib
    ```

    - For Mint 21 (Ubuntu jammy)
    ```shell
    deb [arch=amd64 signed-by=/usr/share/keyrings/oracle-virtualbox-2016.gpg] https://download.virtualbox.org/virtualbox/debian jammy contrib
    ```

    - For Mint 22 (Ubuntu noble) **Currently doesn't work**, so a direct download maybe the only current choice!
    ```shell
    deb [arch=amd64 signed-by=/usr/share/keyrings/oracle-virtualbox-2016.gpg] https://download.virtualbox.org/virtualbox/debian noble contrib
    ```

2. Install Repository Key
    ```shell
    wget -O- https://www.virtualbox.org/download/oracle_vbox_2016.asc | sudo gpg --yes --output /usr/share/keyrings/oracle-virtualbox-2016.gpg --dearmor
    ```
3. Install Virtual Box (replace "7.20.0" if this is out-of-date)
    ```shell
    sudo apt-get update
    sudo apt-get install virtualbox-7.20.0
    ```
4. Ensure that each user who will use `VirtualBox` has been added to the `vbusers` group, so that the extension pack works.

Try using Virtual box.

#### Direct Download of Latest Version

- For Mint 20*, click "Ubuntu 20.04"
- For Mint 21*, click "Ubuntu 22.04"
- For Mint 22*, click "Ubuntu 24.04"

1. Download and install the deb.
2. Ensure that each user who will use `VirtualBox` has been added to the `vbusers` group, so that the extension pack works.
3. Reboot

Try using Virtual box.