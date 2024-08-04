# Useful4LinuxMint - Hardware - Audio - Service - PipeWire
(These tips were pulled from multiple pages.)

After upgrading to Mint 22
- Audio didn't work, wt*!
- MATE "Sound Preferences" didn't show the proper identity for my motherboard audio hardware, so decided to clean install Pipewire, and re-installs didn't help!
- Re-install, service restarts, and reboot; both didn't resolve either issue!  

- Notes:
    - Always install "wireplumber", never "pipewire-media-session", the latter is deprecated!

- Troubleshooting
    - Is the PulseAudio adapter working:
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
- Official [PipeWire](https://pipewire.org/) site.
- [PipeWire PPA for Ubuntu](https://github.com/pipewire-debian/pipewire-debian) for apt installs
    - Distro PipeWire reinstall was a waste of time, so I added this PPA and followed the process here.
    - Ignored all the official ubuntu `pipewire-*` stuff, because I didn't want to complicate fix.
- [PipeWire Guide](https://github.com/mikeroyal/PipeWire-Guide)
- [PipeWire Wiki](https://gitlab.freedesktop.org/pipewire/pipewire)
    - [Performance tuning](https://gitlab.freedesktop.org/pipewire/pipewire/-/wikis/Performance-tuning) helped me to fix no audio
    - [Config PipeWire](https://gitlab.freedesktop.org/pipewire/pipewire/-/wikis/Config-PipeWire) helped me to fix no audio