# QtPass

A QT GUI for the [pass](https://www.passwordstore.org/) encrypted secrets store.

To install:
```shell
apt-get install qtpass
```

It can generate OTP tokens from token specifications, like GitHub provides, but only if:
- The [pass-otp](../console/pass-otp.md) command/extension to pass was installed, e.g. via `apt`.
- The token specification **must** be present in the password field of a password file.
  This is annoying for the `passff` Firefox extension,
  because it can't provide the OTP token if the login is from a different password file,
  so it has to be got via pass-otp or this GUI.  


## TODO:
- Add configuration details for this GUI to use pass password files.
- Add md file and links for `pass` console command.
- Add md file and links for `pass-otp` console command.
- Add md file and links for `passff` Firefox extension.
