# pkexec

> pkexec allows an authorized user to execute PROGRAM as another user; `root` if not specified.
> 
> If PROGRAM is not specified, the default shell will be run.
> 
> If username is not specified, then the program will be executed as the administrative
super user, `root`.

An alternative to sudo, especially when you want a root password prompt as a Desktop GUI prompt, 
or because you can't use sudo because the current user lacks Administrator permissions,
as I discovered for a user on 32-bit `Debian 12`, on an ancient netbook. 

Beware: I discovered that some executed PROGRAM, somehow, loss root access so misbehave, but don't when run via sudo!

## Installation

This may not be necessary, because it may already be a default part of your Linux distribution.

## Usage

> pkexec [--version] \[--disable-internal-agent\] [--help]

> pkexec [--keep-cwd] \[--user username\] PROGRAM \[ARGUMENTS...\]

### Switches

| Switches                 | Description                                                                                                                                                                 |
|--------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| --disable-internal-agent | forbid registering its own authentication agent, when one was not provided.                                                                                                 |
| --keep-cwd               | Don't cd to the user's /home subdirectory before running the program; this may fix some "only works with sudo" issues,<br/> e.g. trying to run something via relative path. |
| --help                   | Print short help details to stdout; run `man pkexec` to see more details.                                                                                                   |
| --user username          | Specify a user name, rather than `root`, to attempt to impersonate.                                                                                                         |
| --version                | Print the `pkexec` version to stdout.                                                                                                                                       |


### Use in She-bang, to cover a whole script's execution. 

It can be used at the start of this header line for script files, e.g.:

- Python as `root`
    ```shell
    #!/usr/bin/pkexec /usr/bin/python
    ```

- Bash as `root`
    ```shell
    #!/usr/bin/pkexec /usr/bin/bash
    ```
