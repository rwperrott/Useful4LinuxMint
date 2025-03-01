# [micro](https://micro-editor.github.io/)

    A modern and intuitive terminal-based text editor.

- [GitHub](https://github.com/zyedidia/micro)
  - This does not provide releases.
  - Install via distro repo command or as on the website.

## Features

### Easy to Use

Micro's number one feature is being easy to install (it's just a static binary with no dependencies) and easy to use.

### Highly Customizable

Use a simple json format to configure your options and rebind keys to your liking. If you need more power, you can use Lua to configure the editor further.

### Colors and Highlighting

Micro supports over 75 languages and has 7 default colorschemes to choose from. Micro supports 16, 256, and truecolor themes. Syntax files and colorschemes are also very simple to make.

### Multiple Cursors

Micro has support for Sublime-style multiple cursors, giving you lots of editing power directly in your terminal.

### Plugin System (see Plugins)

Micro supports a full-blown plugin system. Plugins are written in Lua and there is a plugin manager to automatically download and install your plugins for you.

### Common Keybindings

Micro's keybindings are what you would expect from a simple-to-use editor. You can also rebind any of the bindings without problem in the bindings.json file.

### Mouse Support

Micro has full support for the mouse. This means you can click and drag to select text, double click select by word, and triple click to select by line.

### Terminal Emulator

Run a real interactive shell from within micro. You could open up a split with code on one side and bash on the other -- all from within micro.

And much more! Check out the full list of features here as well as the built-in help system also viewable online here.


## Plugins

From [Github plugin-channel](https://github.com/micro-editor/plugin-channel)


| Plugin          | Description                                             | Link                                                       | 2.0 Support                              |
| --------------- | ------------------------------------------------------- | -------------------------------------------------------    | ---------------------------------------- |
| `comment`       | Plugin to auto comment or uncomment lines               | https://github.com/micro-editor/comment-plugin             | :heavy_check_mark: (provided by default) |
| `snippets`      | Provides snippets functionality                         | https://github.com/micro-editor/updated-plugins/tree/master/micro-snippets-plugin         | :heavy_check_mark:                       |
| `go`            | Provides `gofmt` and `goimports` support for Go files   | https://github.com/micro-editor/go-plugin                  | :heavy_check_mark:                       |
| `fish`          | Provides `fishfmt` support for Fish files               | https://github.com/onodera-punpun/micro-fish-plugin        | :heavy_check_mark:                       |
| `wc`            | Plugin to count words/characters                        | https://github.com/adamnpeace/micro-wc-plugin              | :heavy_check_mark:                       |
| `fzf`           | Provides `fzf` support for opening files                | https://github.com/samdmarshall/micro-fzf-plugin           | :heavy_check_mark:                       |
| `pony`          | Provides auto-indentation for Pony files                | https://github.com/Theodus/micro-pony-plugin               | :heavy_check_mark:                       |
| `editorconfig`  | EditorConfig Support for micro                          | https://github.com/10sr/editorconfig-micro                 | :heavy_check_mark:                       |
| `crystal`       | Provides various `crystal` tools for crystal files      | https://github.com/ColinRioux/micro-crystal                | :heavy_check_mark:                       |
| `gotham-colors` | A colorscheme for code that never sleeps in Gotham City | https://github.com/novln/micro-gotham-colors               | :heavy_check_mark: (provided by default) |
| `misspell`      | Plugin that corrects commonly misspelled words          | https://github.com/onodera-punpun/micro-misspell-plugin    | :heavy_check_mark:                       |
| `monokai-dark`  | A dark monokai colorscheme                              | https://github.com/Theodus/micro-monokai-dark              | :heavy_check_mark: (provided by default) |
| `manipulator`   | Extend text manipulation abilities                      | https://github.com/NicolaiSoeborg/manipulator-plugin       | :heavy_check_mark:                       |
| `filemanager`   | A file manager!                                         | https://github.com/NicolaiSoeborg/filemanager-plugin       | :heavy_check_mark:                       |
| `vcs`           | Mark changed lines in Git or Mercurial repositories     | https://bitbucket.org/dermetfan/micro-vcs                  | :heavy_check_mark: (provided by default) |
| `joinLines`     | Plugin which joins selected lines or the following with the current | https://github.com/Lisiadito/join-lines-plugin | :heavy_check_mark:                       |
| `bounce`     | Plugin that implements nano-style smart home and bouncing the cursor between matching-brackets | https://github.com/deusnefum/micro-bounce | :heavy_check_mark:                       |
| `quoter`     | Plugin that allows you to add quotes or brackets around selected text | https://github.com/deusnefum/micro-quoter | :heavy_check_mark:                       |
| `zigfmt`        | Provides `zig fmt` integration for Zig files            | https://github.com/squeek502/micro-zigfmt                  | :heavy_check_mark:                       |
| `jlabbrev`      | Provides backslash abbreviations from the julia prompt  | https://github.com/MasFlam/jlabbrev                        | :heavy_check_mark:                       |
| `nord-colors`   | A set of dark and light colorschemes based on Nord      | https://github.com/KiranWells/micro-nord-tc-colors         | :heavy_check_mark:                       |
| `autofmt`          | Runs `yapf` (or other autoformatters) in place when saving files           | https://github.com/a11ce/micro-yapf                        | :heavy_check_mark:                       |
| `bookmark`      | Bookmark lines and quickly jump between saved positions | https://github.com/haqk/micro-bookmark                     | :heavy_check_mark:                       |
| `quickfix`      | Adds a functionality similar to VIM quickfix pane       | https://github.com/serge-v/micro-quickfix                  | :heavy_check_mark:                       |
| `jump`      | Jump to any function, class or heading with F4. Go, Markdown, Python, C and in 40 other languages | https://github.com/terokarvinen/micro-jump   | :heavy_check_mark:      |
| `detectindent`  | Automatically detect indentation settings               | https://github.com/dmaluka/micro-detectindent              | :heavy_check_mark:                       |
| `lsp`           | An basic LSP client implementation                      | https://github.com/AndCake/micro-plugin-lsp                | :heavy_check_mark:                       |
| `run`      | F5 to save and run, F12 to 'make', F9 to 'make' in background. Go, Python, Lua and executable file (#!) supported. Can 'make' whole project even from subdir. | https://github.com/terokarvinen/micro-run   | :heavy_check_mark:      |
| `palettero`      | Command palette - Ctrl-P to fuzzy search & run commands, textfilters and descriptions. Use Python oneliners and grep to edit text. |  https://github.com/terokarvinen/palettero  | :heavy_check_mark:      |
| `cheat`      | F1 cheatsheet for the language you're editing: Python, Go, Lua... |  https://github.com/terokarvinen/micro-cheat  | :heavy_check_mark:      |
	https://github.com/terokarvinen/micro-cheat 	✔️
