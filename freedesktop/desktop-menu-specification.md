# [Desktop Menu Specification](https://www.freedesktop.org/wiki/Specifications/menu-spec/)

This is an XML file of one of more `<Menu>`
```xml
<Menu>
    <Name>Applications</Name>
    ...
    <Menu>..</Menu><!-- zero or more nested sub-menus -->
    ...
    <Include> <!-- zero or one -->
        <Filename>{name}.desktop</Filename> <!-- one or more .desktop launcher filenames -->
    </Include>
</Menu>
```

- See [Desktop Entry Specification](desktop-entry-specification.md) for *.desktop details.


## Example

The company ShinyThings Inc. has developed an application named WebMirror 1.0 and would like to add its own submenu to the system menus consisting of a WebMirror menu item and a WebMirror Admin Tool menu item. The company will use "shinythings" as its vendor id. For the purpose of this example all menu items will be available in two languages, English and Dutch. The language code for Dutch is nl.

First the company needs to create two .desktop files that describe the two menu items:

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

A .directory file needs to be installed to provide a title and icon for the sub-menu itself:
- datadir/desktop-directories/shinythings-webmirror.directory:
```ini
[Desktop Entry]
Encoding=UTF-8

Icon=webmirror

Name=WebMirror
Name[nl]=WebSpiegel
```


And finally, a .menu file needs to be provided that links it all together:

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
