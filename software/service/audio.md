# Audio Service

- These can fail to work because of distro root or /home issues; 
I had annoying issues with both PulseAudio and PipeWire, including no Audio!
- Annoyingly audio may break because of bad audio server configuration stored in /home/{user} files!

## PulseAudio
A dated audio service, being increasingly replaced by the more powerful PipeWire.


## → [PipeWire](/software/pipewire.md)
A powerful audio service, which has become the default for Ubuntu and Mint 22.
It has proper Bluetooth headset support, without the hacks needed by PulseAudio.

## JACK
This must be provided audio data at 48KHz, otherwise it won't work.
[PipeWire](/software/pipewire.md) supports this API well.
e.g. `Audacity` must have a sample rate converter installed, enabled,
and configured for 48KHz; otherwise it will refuse to play any sound.  
