# CoolerControl

- [GitLab](https://gitlab.com/coolercontrol/coolercontrol)
- [GitHub](https://github.com/codifryed/coolercontrol) (mirror)

>What Is This?
CoolerControl is a feature-rich cooling device control application for Linux. It has a system daemon
for background device management, as well as a GUI to expertly customize your settings.
>
>What Features Does It Have?
>
>- A highly configurable GUI with system overview.
>- A control daemon that runs in the background.
>- Auto detection of hwmon/sysfs and liquidctl devices including some laptops.
>- Enhanced liquidctl device support (AIOs, USB Fan hubs, LCD screens, RGB lighting, etc).
>- Fan control support for most NVidia and AMD GPUs.
>- Fully customizable speed Profiles like Fixed, Graph(Curve), and Mix that can be applied to
multiple fans.
>
>Functions to control how a Profile is applied with hysteresis, threshold, directional, and
response time control.
>- System-wide cooling Modes to adjust all your devices at once.
>- Create your own Custom Sensors based on a File or on a combination of temperature sensors.
>- Combine Profiles from multiple devices for complete cooling coverage.
>- Re-applies settings after waking from sleep.
>- External monitoring and GUI support.
>- Comprehensive REST API for extensions.

It can control various devices, including:
- Corsair CPU Water Coolers. 
- Nvidia GPU fan, with temperature.

## Installation

- For Mint 21 and 22 [Debian](https://gitlab.com/coolercontrol/coolercontrol#debian) Debian apt
    ```shell
    sudo apt install curl apt-transport-https
    curl -1sLf \
      'https://dl.cloudsmith.io/public/coolercontrol/coolercontrol/setup.deb.sh' \
      | sudo -E bash
    sudo apt update
    sudo apt install coolercontrol
    sudo systemctl enable --now coolercontrold
    ```
