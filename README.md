# Useful4LinuxMint
Useful bookmarks and notes for my Linux Mint installs

## Hardware

### Audio
(PulseAudio is obsolete, Pulsewire replaced it.)

- Test it works `pactl info`

#### [Pipewire](https://pipewire.org/)
(These tips were pulled from multiple pages.)


After upgrade to Mint 22, audio didn't work and didn't show proper motherboard audio device in MATE "Sound Preferences", so decided to clean install pipewire, and reinstalls didn't help, so needed to try a lot more!


- Notes:
  - Never install "pipewire-media-session", it's deprecated!
  - Always install "wireplumber".

- Troubleshooting
  - Is PulseAudio adapter working:
    ```shell
    pactl info
    ```
  - Query services:
    ```shell
    systemctl --user status pipewire{,-pulse}.{socket,service} pipewire-media-session.service
    ```
  - Reload user service
    ```shell
    
    ```
  *TODO: COMPLETE*

Links:
- [PipeWire PPA for Ubuntu](https://github.com/pipewire-debian/pipewire-debian) for apt installs
    - Used this PPA and the process here, in preference to Distro default, or any dubous answer on Mint/Ubuntu forums, or some other blog, or "answer" site!
    - Ignored all the official ubuntu pipewire-* stuff, because would probably break audio again.
- [PipeWire Guide](https://github.com/mikeroyal/PipeWire-Guide)
- [PipeWire Wiki](https://gitlab.freedesktop.org/pipewire/pipewire)
    - [Performance tuning](https://gitlab.freedesktop.org/pipewire/pipewire/-/wikis/Performance-tuning) helped me to fix no audio
    - [Config PipeWire](https://gitlab.freedesktop.org/pipewire/pipewire/-/wikis/Config-PipeWire) helped me to fix no audio

## Terminal Software

## Desktop Software

### QtPass

A GUI for the [pass](https://www.passwordstore.org/) encrypted secrets store

To install:
```shell
apt-get install qtpass
```

### LibreWolf

Firefox needs to be made more secure, to need replacing by LibreWolf; annoyingly Linux Mint, at least the MATE flavour, has a dependencies on Firefox, so it can't be uninstalled!

Install using [Main Debian Respository](https://librewolf.net/installation/debian/#main-debian-repository) sources script; password is needed for sudo!
This must be redone after `mintupgrade` to a new Mint version, because `mintupgrade` annoyingly requires deletion of `/etc/apt/sources.list.d/librewolf.sources`, because of this hack.

#### Preferences - Search

- Ensure that prefered Default Search Engine is configure.

#### Preferences - Privacy & Security

- Password - Ask to save password - unticked!
  Use [PassFF](https://codeberg.org/PassFF/passff) [Firefox extension](https://addons.mozilla.org/firefox/addon/passff) with [QtPass](https://github.com/IJHack/qtpass) [instead!

_TODO: Complete_

## Service Software

### Wine

The Ubuntu Wine versions are always too dated, so the WineHQ stable repo must be added for a decent Wine experience!

_TODO: Complete_

### Github Desktop

Annoyingly, Github don't provide an install for Linux, only for Windows and Mac!

Install using the repo using the `@shiftkey`or `@mwt` script [here](https://github.com/shiftkey/desktop#debianubuntu),
then run:
```shell
sudo apt update && sudo apt install github-desktop
```

Configuration
- Options
  - Advanced
    Untick "Usage" [] bla
- Accounts
  Sign in with Github.com webpage, and ensure that the browse does have excessive security present, so that it works!
  I prefer the mobile GitHub App for 2FA.
