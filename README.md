# Flatpak wrapper of inklestudio's Ink CLI (inklecate)

This is a thin wrapper around
[inklestudio's](https://www.inklestudios.com/) `inklecate`, to allow
running this CLI tool from Linux systems where the Mono runtime is not
available, or without having to install it separately. It uses
[flatpak](https://flatpak.org/) and it's [Mono SDK
extension](https://github.com/flathub/org.freedesktop.Sdk.Extension.mono5).

# Install

Download the latest release and click on the downloaded file to
install it. If clicking on it doesn't work in your system, run from
the command-line:

    flatpak install inklecate-0.9.0.flatpak

To build and install the flatpak yourself:

    flatpak-builder build-dir com.inklestudios.inklecate.json --force-clean --repo=repo
    flatpak build-bundle ./repo inklecate.flatpak com.inklestudios.inklecate
    flatpak install inklecate.flatpak

# Usage

Play a `.ink` file in the command line:

    com.inklestudios.inklecate -p TheIntercept.ink

Convert a `.ink` file to the JSON bytecode-like format, suitable for
loading it in a Ink engine:

    com.inklestudios.inklecate TheIntercept.ink

It will output a `TheIntercept.ink.json` file.

For the upstream usage, see:
https://github.com/inkle/ink#advanced-using-inklecate-on-the-command-line
