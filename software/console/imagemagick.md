# ImageMagick

>ImageMagick® is a free, open-source software suite, used for editing and manipulating digital images. It can be used to
> create, edit, compose, or convert bitmap images, and supports a wide range of file formats, including JPEG, PNG, GIF,
> TIFF, and Ultra HDR.
>
>ImageMagick is widely used in industries such as web development, graphic design, and video editing, as well as in
> scientific research, medical imaging, and astronomy. Its versatile and customizable nature, along with its robust
> image processing capabilities, make it a popular choice for a wide range of image-related tasks.
>
>ImageMagick includes a command-line interface for executing complex image processing tasks, as well as APIs for
> integrating its features into software applications. It is written in C and can be used on a variety of operating
> systems, including Linux, Windows, and macOS.

**Do NOT install any `\*magick\*` package from ubuntu deb repository**, _it is obsolete/breaking junk._

**Do not call `convert`, it is deprecated**; _`mogrify` is probably what you should be calling._

## Installation

Sadly `Ubuntu` still hasn't fixed the mess above even for `Noble`, so v7 source must be downloaded, built and installed.
- No, you can get a usable Flatpak or AppImage for this because of multiple console executables!

- [Download](https://imagemagick.org/script/download.php)
  - Download "magick"
  - Hope it works OK, it didn't for me after an upgrade to Mint22 after Install from Linux Source to get ImageMagick v7, not dated v6!
  - This isn't a good enough solution for a command suite without scripts to simulate the separate commands properly!
- or
- [Install from Linux Source](https://imagemagick.org/script/install-source.php#linux)
  - Download sourcecode somewhere safe; the number after the `-` of the 2nd CD may differ later!
    ```shell
    cd ~/Downloads && \
    sudo rm -f -r ImageMagick* && \
    wget https://imagemagick.org/archive/ImageMagick.tar.gz && \
    tar -xf ImageMagick.tar.gz && \
    cd "$(find ~/Downloads -type d -name ImageMagick*)"
    ```
  - Configure it ... be patient, it takes a long time to compiler!
    - try
      ```shell
      ./configure --with-modules
      ```
    - else
      ```shell
      ./configure --with-modules
      ```
  - Make binaries
    - try
      ```shell
      make
      ```
    - else
      ```shell
      gmake
      ```
  - Install binaries
    ```shell
    sudo make install
    ```
  - Check install
    ```shell
    magick --version
    ```
  - Cleanup
    ```shell
    cd ~/Downloads
    sudo rm -f -r ImageMagick*
    ```



