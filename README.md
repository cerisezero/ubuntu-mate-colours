# Ubuntu MATE Colours

![Screenshot of thte 3 themes using custom colours](.github/screenshot@2x.jpg)

A small program that takes `ubuntu-mate-artwork` (theme & icons)
and swaps out the green to a colour of your choice.

Only these themes are supported:

- Ambiant-MATE
- Ambiant-MATE-Dark
- Radiant-MATE

These versions are supported:

* Ubuntu MATE 18.04 LTS
* Ubuntu MATE 19.04
* Ubuntu MATE 19.10

These themes are not considered final yet, please test and
[report issues here](https://github.com/lah7/ubuntu-mate-colours/issues) or find
an issue to help out with.


## Versioning

This project works with the latest upstream release of `ubuntu-mate-artwork`, which
is normally tested for the latest Ubuntu version. As a result, older (and LTS)
releases may include theme & icon updates not found in
`ubuntu-mate-themes` and `ubuntu-mate-icon-themes` packages for that release.

Updates to `ubuntu-mate-colours` are represented by the fourth decimal, for example:

> 19.10.5.**2** = **2**nd build based on 19.10.5.


## Installation

Packages are available for both the generator and pre-defined colours.
On Ubuntu, simply add the PPA and install the packages as desired.

    sudo add-apt-repository ppa:lah7/ubuntu-mate-colours

The following colours are available:

| Hex                               | Colour          |
| --------------------------------- | --------------- |
| ![](.github/aqua.png) `#2DACD4`   | Aqua
| ![](.github/blue.png) `#5489CF`   | Blue
| ![](.github/brown.png) `#965024`  | Brown
| ![](.github/orange.png) `#E95420` | Orange
| ![](.github/pink.png) `#E231A3`   | Pink
| ![](.github/purple.png) `#7E5BC5` | Purple
| ![](.github/red.png) `#CE3A3A`    | Red
| ![](.github/teal.png) `#1CB39F`   | Teal
| ![](.github/yellow.png) `#DFCA25` | Yellow

Packages are split by colour, so installing `ubuntu-mate-colours-blue` will
give you the blue variants of Ambiant-MATE, Ambiant-MATE-Dark and Radiant-MATE.

    sudo apt install ubuntu-mate-colours-blue

After installing, the themes/icons will be available to choose from **Appearance** (Look & Feel).

If your desired colour isn't listed, you can create your own using the generator:

    sudo apt install ubuntu-mate-colours-generator

There's also the option to install them all, but this may take up a lot of disk space!

    sudo apt install ubuntu-mate-colours-all


## Generator Usage

First, make sure you have an up-to-date copy of the [`ubuntu-mate-artwork` repository](https://github.com/ubuntu-mate/ubuntu-mate-artwork).
If you have `git` installed, you can make a clone using this command:

    git clone https://github.com/ubuntu-mate/ubuntu-mate-artwork.git --depth=1

To update this copy without re-downloading everything in future:

    cd ubuntu-mate-artwork
    git pull --rebase origin master

It is possible to use your currently installed installation of the theme & icons
by specifying `/` for `--src-dir`, but please be aware this project is designed to
work with the latest version of the theme & icons.

#### Required arguments

| Argument          | Description                                             |
| ----------------- | ------------------------------------------------------- |
| `--theme`         | Ubuntu MATE theme to use, such as Ambiant-MATE.
| `--hex`           | Standard #RRGGBB hex value.
| `--name`          | A human readable name to describe this colour.
| `--src-dir`       | Path to the root of the `ubuntu-mate-artwork` repository.

For **hex**, you can use colour picker applications to choose the colour.

    mate-color-selection
    zenity --color-selection

For example:

    ubuntu-mate-colours-generator --theme="Ambiant-MATE" --hex="#5489CF" --name="Blue" --src-dir=/home/user/ubuntu-mate-artwork

The script by default will create the theme in `~/.local/share/themes` and
`~/.local/share/icons`, making it available to the local user.


#### Optional arguments

| Argument               | Description                                       |
| ---------------------- | ------------------------------------------------- |
| `--install-icon-dir`   | Target path to process/install the new icons.
| `--install-theme-dir`  | Target path to process/install the new theme.
| `-v` or `--verbose`    | Show details of each file being processed.
| `-y` or `--overwrite`  | Suppress confirmation prompt to replace target path.
| `--ignore-existing`    | Ignore theme/icons files if they already exist.


## Generated your own?

Don't forget to update your copy as time passes. To keep it up-to-date, pull the
latest changes from `ubuntu-mate-artwork` and run this program again. If
forgotten for too long, you may miss out on bug fixes and improvements
present in the `ubuntu-mate-themes` package.


## License

Both this program and [`ubuntu-mate-artwork`](https://github.com/ubuntu-mate/ubuntu-mate-artwork)
are licensed under the GPLv3.
