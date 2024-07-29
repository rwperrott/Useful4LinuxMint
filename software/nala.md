# Nala

> Nala is a front-end for libapt-pkg. Specifically we interface using the python-apt api.
>
> Especially for newer users it can be hard to understand what apt is trying to do when installing or upgrading.
>
> We aim to solve this by not showing some redundant messages, formatting the packages better,
and using color to show specifically what will happen with a package during install, removal, or an upgrade.

- Simply, A nicer, coloured, faster (parallel downloads) alternative to `apt`.

[GitHub](https://github.com/volitank/nala)

# [Installation](https://gitlab.com/volian/nala/-/wikis/Installation):

[Optional](https://linuxcapable.com/how-to-install-nala-on-debian-linux/) (**May not download!**)
- install Volarian Scar repository key.
    ```shell
    curl -fSsL https://deb.volian.org/volian/scar.key | gpg --dearmor | sudo tee /usr/share/keyrings/volian.gpg > /dev/null
    ```
-  install Volarian Scar repository
```shell
echo "deb [signed-by=/usr/share/keyrings/volian.gpg] https://deb.volian.org/volian/ scar main" | sudo tee /etc/apt/sources.list.d/volian-archive-scar-unstable.list && apt update
```

## Installation Choices
- From distribution repository (preferred):
    ```shell
    sudo apt install nala
    ```

- Direct from Volarian Scar. (**May not download!**)
    ```shell
    curl https://gitlab.com/volian/volian-archive/-/raw/main/install-nala.sh | bash
    ```
  
- From distribution test repository:
    ```shell
    sudo apt install -t nala nala
    ```
- Local deb (the reliable approach way to get the recent releases):
  - on the Volarian [releases page](https://gitlab.com/volian/nala/-/releases)
  - download the latist nala_*_all.deb
  - install it

