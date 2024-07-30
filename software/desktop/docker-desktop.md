# [Docker Desktop](https://www.docker.com/products/docker-desktop/)

"The #1 containerization software for developers and teams"

"Your command center for innovative container development"

- This is an easy entry point for docker deployment, but has issues.
- Probably not an appropriate tool for live deployments.
- For how long, with Podder, Podman, and other challengers!?_


# Installation

- Open web page [Install Docker Engine on Ubuntu](https://docs.docker.com/desktop/install/ubuntu/)

## The Lazy way

- Click on the Blue "**DEB package**" button, to download the .deb installer and install this.

## The proper way

1. If not Gnome Desktop (probably not for Linux Mint), first run:
    ```shell
    sudo apt install gnome-terminal
    ```
   
2. Open web page [Setup Docker's package apt repository](https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository)
    1.
         ```shell
         # Add Docker's official GPG key:
         sudo apt-get update
         sudo apt-get install ca-certificates curl
         sudo install -m 0755 -d /etc/apt/keyrings
         sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
         sudo chmod a+r /etc/apt/keyrings/docker.asc

         # Add the repository to Apt sources:
         echo \
           "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
           $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
           sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
         sudo apt-get update
         ```

   2. Install the Docker packages.
       ```shell
       sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
       ```
      - `containerd.io` is the root-user container host server
      - `docker-ce` is the docker root-user server controlling `containerd.io` 
      - `docker-ce-cli` Docker CLI: the open-source application container engine
      - `docker-buildx-plugin` Docker Buildx cli plugin.
      - `docker-compose-plugin` Docker Compose (V2) plugin for the Docker CLI.
   3. Verify that the Docker Engine installation is successful by running the `hello-world` image.
        ```shell
        sudo docker run hello-world
        ```
