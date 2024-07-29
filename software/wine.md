# [Wine](https://www.winehq.org)

The Ubuntu Wine versions are always too dated, so the WineHQ stable repo must be added for a decent WINE experience!

## Following [Ubuntu](https://wiki.winehq.org/Ubuntu) instructions, with some corrections:

1. Add the repository key:
    ```shell
    sudo mkdir -pm755 /etc/apt/keyrings
    sudo wget -O /etc/apt/keyrings/winehq-archive.key https://dl.winehq.org/wine-builds/winehq.key
    ```

2. Add the repository (via one of):
   - For Linux Mint 22 (Ubuntu Noble Numbat):
       ```shell
       sudo wget -NP /etc/apt/sources.list.d/ https://dl.winehq.org/wine-builds/ubuntu/dists/noble/winehq-noble.sources
       ```
   - For Linux Mint 21.x (Ubuntu Jammy Jellyfish):
       ```shell
       sudo wget -NP /etc/apt/sources.list.d/ https://dl.winehq.org/wine-builds/ubuntu/dists/jammy/winehq-jammy.sources
       ```
3. Ensure that `Winehq` is enabled, in the "Additional Repositories" list, in "Software Source" GUI App.

4. Check for available branch versions:
   ```shell
   apt search winehq
   ```

5. Install Wine:
    - For Linux Mint 21 (Ubuntu Noble Numbat) `staging`:
        ```shell
        sudo apt update && sudo apt install --install-recommends winehq-stable
        ```
    - For Linux Mint 21.x (Ubuntu Jammy Jellyfish) current best is `staging`, because no `stable` yet:
        ```shell
        sudo apt update && sudo apt install --install-recommends winehq-staging
        ```
6. Install [WineGUI](wingui.md), to make Wine far easier to manage.