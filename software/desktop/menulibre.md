# menulibre

This is a Desktop menu editor, which indirectly edits the menu
and the ([Desktop Entry Specification](https://specifications.freedesktop.org/desktop-entry-spec/latest/index.html))
`*.desktop` menu files.
It is far more powerful than the often confusing and unhelpful right-click menu editor for desktop menus, like MATE's!

- Supports creating, editing and deleting, and editing some of their values:
  - `*.directory` (sub-directory) files; which seem shockingly poorly documented!
  - `*.desktop` (launcher) files; which are well documented. 
- It does not appear to support viewing, editing, adding or deleting localised versions of any named values.


## Discovered Annoyances

1. No launcher cloning feature, say if you want to start a GUI app with terminal. 
2. Launcher (*.desktop) filenames can't be edited by this application.
3. New launcher entries can't be user named!
4. I'd like an options to create copy of, or create soft links to, a launcher, in the `~/Desktop` directory!

## Window Contents

- The top menu has buttons to:
  - Add a new launcher, directory or separator.
  - Save changes.
  - Undo.
  - Redo.
  - Test launch the displayed launcher.
  - Delete the current entry, in the Right pane.
  - A search text box.

- The Left hand pane
  - All entries, or any found entries, as a menu tree, with hidden items.

- The Right hand pane - for the entry selected in the Left hand pane
  - For a directory:
      - Blank
  - For a directory:
      - Its icon (editable)
      - The _copyable_ desktop's (Xfce, MATE, etc.) menu file path (/usr/\* or ~/\*)
  - For a launcher:
      - **(at the bottom) the _copyable_ \*.desktop file path**
      - Its icon (editable)
      - Application Details
        - Command (editable); clicking on open reveals a dialog for editing:
          - Environment variable
          - Command
          - File
          - URL
          - Extra
      - Option switches
        - Run in terminal
        - Use startup notification
        - Hide from menus
      - Tabs for table/list/form entries
        - Categories table (buttons for : add, delete, delete all)
          - Category Name
          - Section
        - Actions table (buttons for : add, delete, delete all, move up, move down)
          - Show
          - Name
          - Command
        - Advances (`;` is the list separator character)
          - Generic Name
          - Try Exec (command)
          - Only Show In (list), e.g. XFCE)
          - Not Shown In (list)
          - Mimetypes (list)
          - Keywords (list)
          - Startup WM Class
            - Magnifying Glass button brings up a window to select this from the running GUI application
          - Implements
          - Hidden (switch)
          - DBUS Activate (switch)
          - Prefers Non-Default GPU (switch)
          - Uses Notifications (switch)
