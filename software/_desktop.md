# Desktop Software

## → [Btrfs Assistant](desktop/btrfs-assistant.md)

A far easier way to do common BTRFS disk management tasks on a desktop Linux.

## → [CoolerControl](services/cooler-control.md)

A GUI Frontend provided by the installer of the Cooler Control service,
a service, which modulates the speed of CPU Water Cooler Pump and Fan(s), and GPU Heatsink Fan(s) speeds.

## → [Double Commander](desktop/double-commander.md)

This seems to go wrong less than most of the other Desktop specific file managers:
- They can stall.
- Annoyingly lack functionality they should provide, like filtering, sane progress, and some native archive support!
- Their plugins for them can do retarded stuff, like change a default application just to extract archives (Thunar)!

## → Double Commander QT

This seemed less good than `Double Commander KDE`;
- Uses dated QT5
- Has rendering bugs, which squish some controls in modal child windows, making them unusable. 

## → MATE Terminal (mate-terminal)

- My favourite terminal Useful, because it can store profiles for new tabs or windows:
  - Lots of settings can be customised.
  - Can run custom commands, with a custom title, which can be more useful than aliases.

## → [Menu Libre](desktop/peazip.md)

An Editor for the _current_ desktop menu and all the *\.desktop files in other directories.
- It is annoying that it doesn't request root access support to allow editing of shared \.desktop files!

## → [PeaZip](desktop/peazip.md)

An archiver GUI, which supports multiple archive formats, apparently the archiver expected by the archive
extension for the Thunar file manager of the Linux XFCE Desktop. 

## → [QtPass](desktop/qtpass.md)

A QT GUI for the [pass](https://www.passwordstore.org/) encrypted secrets store

---

## [Desktop Menu Specification](https://www.freedesktop.org/wiki/Specifications/menu-spec/)

The company ShinyThings Inc. has developed an application named WebMirror 1.0 and would like to add its own submenu to the system menus consisting of a WebMirror menu item, and a WebMirror Admin Tool menu item. The company will use "shinythings" as its vendor id. For the purpose of this example all menu items will be available in two languages, English and Dutch. The language code for Dutch is nl.

First the company needs to create two \.desktop files that describe the two menu items:

- datadir/applications/shinythings-webmirror.desktop:
```ini
[Desktop Entry]
Encoding=UTF-8
Type=Application

Exec=webmirror
Icon=webmirror

Name=WebMirror
Name[nl]=WebSpiegel
``` 

- datadir/applications/shinythings-webmirror-admin.desktop:
```ini
[Desktop Entry]
Encoding=UTF-8
Type=Application

Exec=webmirror-admintool
Icon=webmirror-admintool

Name=WebMirror Admin Tool
Name[nl]=WebSpiegel Administratie Tool
```

A \.directory file needs to be installed to provide a title and icon for the sub-menu itself:
- datadir/desktop-directories/shinythings-webmirror.directory:
```ini
[Desktop Entry]
Encoding=UTF-8

Icon=webmirror

Name=WebMirror
Name[nl]=WebSpiegel
```

And finally, a .menu file needs to be provided, that links it all together:

- sysconfdir/menus/application-merged/shinythings-webmirror.menu:
```xml
<!DOCTYPE Menu PUBLIC "-//freedesktop//DTD Menu 1.0//EN"
"http://www.freedesktop.org/standards/menu-spec/menu-1.0.dtd">
<Menu>
    <Name>Applications</Name>
    <Menu>
        <Name>WebMirror</Name>
        <Directory>shinythings-webmirror.directory</Directory>
        <Include>
            <Filename>shinythings-webmirror.desktop</Filename>
            <Filename>shinythings-webmirror-admin.desktop</Filename>
        </Include>
    </Menu>
...
</Menu>
```



### ([Desktop Entry Specification](https://specifications.freedesktop.org/desktop-entry-spec/latest/index.html)) `*.desktop` files:

| Directory for<br/>`*.desktop` files | For     |
|-------------------------------------|---------|
| /usr/share/applications/            | all     | 
| ~/.local/share/applications         | ${USER} |

The structure is complicated, so see the link!


### [Desktop Menu Specification](https://specifications.freedesktop.org/menu-spec/latest/) `*.directory` Submenus:

| Directory for<br/> `*.directory` submenu files | For     |
|------------------------------------------------|---------|
| /usr/share/desktop-directories/                | all     | 
| ~/.local/share/desktop-directories/            | ${USER} |

| Key       | e.g.                                     | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|-----------|------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Version   | e.g. 1.1                                 | ?                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Type      | `Directory`                              | This is a mandatory field that indicates that the *.directory file describes a submenu.<br/>                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Name      | {name}                                   | Required                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| NoDisplay | true<br/> false                          | Optional                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Comment   | {tooltip}                                | Optional field to specify a tooltip for the submenu.                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Icon      | `folder`<br/>{Icon File}<br/>{icon-name} | The icon to use for the submenu.<br/> This can either be an absolute path to an image file or an icon-name.<br/> If an icon-name is provided an image lookup by name is done in the user's current icon theme.<br/> The xdg-icon-resource command can be used to install image files into icon themes.<br/> The advantage of using an icon-name instead of an absolute path is that with an icon-name the submenu icon can be provided in several different sizes as well as in several differently themed styles. |
e.g.
```yaml
test.directory
[Desktop Entry]
Version=1.1
Type=Directory
Name=Test
NoDisplay=true
Comment=A Test Comment
Icon=folder
```


### [Menu](https://specifications.freedesktop.org/menu-spec/latest/menu-file-format.html) `*.menu` (XML files)

The structure is complicated, so see the link!

### Categories

| Main<br/> Category | Description                                                                    | Notes                                                                  |
|--------------------|--------------------------------------------------------------------------------|------------------------------------------------------------------------|
| AudioVideo         | Application for presenting, creating, or processing multimedia (audio/video)   |                                                                        |
| Audio              | An audio application                                                           | Desktop entry must include AudioVideo as well                          |
| Video              | A video application                                                            | Desktop entry must include AudioVideo as well                          |
| Development        | An application for development                                                 |                                                                        |
| Education          | Educational software                                                           |                                                                        |
| Game               | A game                                                                         |                                                                        |
| Graphics           | Application for viewing, creating, or processing graphics                      |                                                                        |
| Network            | Network application such as a web browser                                      |                                                                        |
| Office             | An office type application                                                     |                                                                        |
| Science            | Scientific software                                                            |                                                                        |
| Settings           | Settings applications                                                          | Entries may appear in a separate menu or as part of a "Control Center" |
| System             | System application, "System Tools" such as say a log viewer or network monitor |                                                                        |
| Utility            | Small utility application, "Accessories"                                       |                                                                        |

| Additional<br/> Category | Description                                                                            | Related Categories                                   |
|--------------------------|----------------------------------------------------------------------------------------|------------------------------------------------------|
| 2DGraphics               | 2D based graphical application                                                         | Graphics                                             |
| 3DGraphics               | Application for viewing, creating, or processing 3-D graphics                          | Graphics                                             |                                                      
| ActionGame               | An action game                                                                         | Game                                                 |
| AdventureGame            | Adventure style game                                                                   | Game                                                 |
| ArcadeGame               | Arcade style game                                                                      | Game                                                 |
| BoardGame                | A board game                                                                           | Game                                                 |
| BlocksGame               | Falling blocks game                                                                    | Game                                                 |
| Building                 | A tool to build applications                                                           | Development                                          |
| Calendar                 | Calendar application                                                                   | Office                                               |
| CardGame                 | A card game                                                                            | Game                                                 |
| Chart                    | Chart application                                                                      | Office                                               |
| ContactManagement        | E.g. an address book                                                                   | Office                                               |
| Database                 | Application to manage a database                                                       | Office or Development or AudioVideo                  |                                                      |
| Debugger                 | A tool to debug applications                                                           | Development                                          |
| Dictionary               | A dictionary                                                                           | Office or TextTools                                  |                                                      |
| Email                    | Email application                                                                      | Office or Network                                    |
| Finance                  | Application to manage your finance                                                     | Office                                               |
| FlowChart                | A flowchart application                                                                | Office                                               |
| GUIDesigner              | A GUI designer application                                                             | Development                                          |
| IDE                      | IDE application                                                                        | Development                                          |
| OCR                      | Optical character recognition application                                              | Graphics;Scanning                                    |
| PDA                      | Tool to manage your PDA                                                                | Office                                               |
| Presentation             | Presentation software                                                                  | Office                                               |
| Profiling                | A profiling tool                                                                       | Development                                          |
| ProjectManagement        | Project management application                                                         | Office or Development                                |
| RasterGraphics           | Application for viewing, creating, or processing raster (bitmap) graphics              | Graphics;2DGraphics                                  |
| RevisionControl          | Applications like cvs or subversion                                                    | Development                                          |
| Scanning                 | Tool to scan a file/text                                                               | Graphics                                             |
| Spreadsheet              | A spreadsheet                                                                          | Office                                               |
| Translation              | A translation tool                                                                     | Development                                          |
| VectorGraphics           | Application for viewing, creating, or processing vector graphics                       | Graphics;2DGraphics                                  |
| WordProcessor            | A word processor                                                                       | Office                                               |                                                      
|                          |                                                                                        |                                                      |
|                          |                                                                                        |                                                      |
| AudioVideoEditing        | Application to edit audio/video files                                                  | Audio or Video or AudioVideo                         |
| DesktopSettings          | Configuration tool for the GUI                                                         | Settings                                             |
| HardwareSettings         | A tool to manage hardware components, like sound cards, video cards or printers        | Settings                                             |
| Printing                 | A tool to manage printers                                                              | HardwareSettings;Settings                            |
| PackageManager           | A package manager application                                                          | Settings                                             |
| Dialup                   | A dial-up program                                                                      | Network                                              |
| DiscBurning              | Application to burn a disc                                                             | AudioVideo                                           |
| InstantMessaging         | An instant messaging client                                                            | Network                                              |
| Chat                     | A chat client                                                                          | Network                                              |
| IRCClient                | An IRC client                                                                          | Network                                              |
| Feed                     | RSS, podcast and other subscription based contents                                     | Network                                              |
| FileTransfer             | Tools like FTP or P2P programs                                                         | Network                                              |
| HamRadio                 | HAM radio software                                                                     | Network or Audio                                     |
| News                     | A news reader or a news ticker                                                         | Network                                              |
| P2P                      | A P2P program                                                                          | Network                                              |
| Photography              | Camera tools, etc.                                                                     | Graphics or Office                                   |
| Player                   | Application to play audio/video files                                                  | Audio or Video or AudioVideo                         |
| Publishing               | Desktop Publishing applications and Color Management tools                             | Graphics or Office                                   |
| Recorder                 | Application to record audio/video files                                                | Audio or Video or AudioVideo                         |
| RemoteAccess             | A tool to remotely manage your PC                                                      | Network                                              |
| Telephony                | Telephony via PC                                                                       | Network                                              |
| TelephonyTools           | Telephony tools, to dial a number, manage PBX, ...                                     | Utility                                              |
| VideoConference          | Video Conference software                                                              | Network                                              |
| WebBrowser               | A web browser                                                                          | Network                                              |
| WebDevelopment           | A tool for web developers                                                              | Network or Development                               |
| Midi                     | An app related to MIDI                                                                 | AudioVideo;Audio                                     |
| Mixer                    | Just a mixer                                                                           | AudioVideo;Audio                                     |
| Sequencer                | A sequencer                                                                            | AudioVideo;Audio                                     |
| TextTools                | A text tool utility                                                                    | Utility                                              |
| Tuner                    | A tuner                                                                                | AudioVideo;Audio                                     |
| TV                       | A TV application                                                                       | AudioVideo;Video                                     |
| Viewer                   | Tool to view e.g. a graphic or pdf file                                                | Graphics or Office                                   |
|                          |                                                                                        |                                                      |
| KidsGame                 | A game for kids                                                                        | Game                                                 |
| LogicGame                | Logic games like puzzles, etc                                                          | Game                                                 |
| RolePlaying              | A role playing game                                                                    | Game                                                 |
| Shooter                  | A shooter game                                                                         | Game                                                 |
| Simulation               | A simulation game                                                                      | Game                                                 |
| SportsGame               | A sports game                                                                          | Game                                                 |
| StrategyGame             | A strategy game                                                                        | Game                                                 |
|                          |                                                                                        |                                                      |
| Accessibility            | Accessibility                                                                          | Settings or Utility                                  |
| Adult                    | Application handles adult or explicit material                                         |                                                      |
| Amusement                | A simple amusement                                                                     |                                                      |
| Archiving                | A tool to archive/backup data                                                          | Utility                                              |
| Art                      | Software to teach arts                                                                 | Education or Science                                 |
| Calculator               | A calculator                                                                           | Utility                                              |                                                      |
| Clock                    | A clock application/applet                                                             | Utility                                              |                                                      |
| Compression              | A tool to manage compressed data/archives                                              | Utility;Archiving                                    |
| ConsoleOnly              | Application that only works inside a terminal (text-based or command line application) |                                                      |
| Construction             |                                                                                        | Education or Science                                 |
| Core                     | Important application, core to the desktop such as a file manager or a help browser    |                                                      |
| COSMIC                   | Application based on COSMIC libraries                                                  |                                                      |
| DDE                      | Application based on DDE libraries                                                     | Qt                                                   |
| Documentation            | Help or documentation                                                                  |                                                      |
| Music                    | Musical software                                                                       | AudioVideo or Education                              |
| Languages                | Software to learn foreign languages                                                    | Education or Science                                 |
| ArtificialIntelligence   | Artificial Intelligence software                                                       | Education or Science                                 |
| Astronomy                | Astronomy software                                                                     | Education or Science                                 |
| Biology                  | Biology software                                                                       | Education or Science                                 |
| Chemistry                | Chemistry software                                                                     | Education or Science                                 |
| ComputerScience          | Computer Science software                                                              | Education or Science                                 |
| DataVisualization        | Data visualization software                                                            | Education or Science                                 |
| Economy                  | Economy software                                                                       | Education or Science                                 |
| Electricity              | Electricity software                                                                   | Education or Science                                 |
| Electronics              | Electronics software, e.g. a circuit designer                                          |                                                      |
| Emulator                 | Emulator of another platform, such as a DOS emulator                                   | System or Game                                       |
| Engineering              | Engineering software, e.g. CAD programs                                                |                                                      |
| FileTools                | A file tool utility                                                                    | Utility or System                                    |
| FileManager              | A file manager                                                                         | System;FileTools                                     |
| Geography                | Geography software                                                                     | Education or Science                                 |
| Geology                  | Geology software                                                                       | Education or Science                                 |
| Geoscience               | Geoscience software, GIS                                                               | Education or Science                                 |
| GNOME                    | Application based on GNOME libraries                                                   | GTK                                                  |
| GTK                      | Application based on GTK+ libraries                                                    |                                                      |
| History                  | History software                                                                       | Education or Science                                 |
| Humanities               | Software for philosophy, psychology and other humanities                               | Education or Science                                 |
| ImageProcessing          | Image Processing software                                                              | Education or Science                                 |
| Literature               | Literature software                                                                    | Education or Science                                 |
| TerminalEmulator         | A terminal emulator application                                                        | System                                               |                                                      |
| Filesystem               | A file system tool                                                                     | System                                               |
| Java                     | Application based on Java GUI libraries, such as AWT or Swing                          |                                                      |
| KDE                      | Application based on KDE libraries                                                     | QT                                                   |
| Monitor                  | Monitor application/applet that monitors some resource or activity                     | System or Network                                    |
| Motif                    | Application based on Motif libraries                                                   |                                                      |
| Maps                     | Software for viewing maps, navigation, mapping, GPS                                    | Education or Science or Utility                      |
| Math                     | Math software                                                                          | Education or Science                                 |
| NumericalAnalysis        | Numerical analysis software                                                            | Education;Math or Science;Math                       |
| MedicalSoftware          | Medical software                                                                       | Education or Science                                 |                                                      |
| Physics                  | Physics software                                                                       | Education or Science                                 |                                                      |
| Qt                       | Application based on Qt libraries                                                      |                                                      |
| Robotics                 | Robotics software                                                                      | Education or Science                                 |                                                      |
| Security                 | A security tool                                                                        | Settings or System                                   |                                 
| Spirituality             | Religious and spiritual software, theology                                             | Education or Science or Utility                      |
| Sports                   | Sports software                                                                        | Education or Science                                 |                                                      |
| ParallelComputing        | Parallel computing software                                                            | Education;ComputerScience or Science;ComputerScience |
| TextEditor               | A text editor                                                                          | Utility                                              |                                                      |
| XFCE                     | Application based on XFCE libraries                                                    | GTK                                                  |


