# Wav2Bar
A tool to make custom audio visualization and export production videos for the audio/music industry.
- **Website:** https://picorims.github.io/wav2bar-website/
- **Blog:** https://picorims.github.io/wav2bar-blog/
- **Discord Server:** https://discord.gg/EVGzfdP

## Important Notes
- **This tool is usable at this point, but is still in early development! Your work is subject to bugs, backup your saves!**
- Git LFS used to be used for node_modules and FFMpeg, but is no longer used. Both of these folders have been removed from the repository, but not its history. You do not need to clone them. Git LFS files are no longer included in archive downloads. **If you want a full release source code archive, go to the releases section. This will include node_modules, but not FFmpeg** (which can be downloaded from their official website compiled and packaged).

## Hacking
- NodeJS must be installed (It will install npm too).
- Clone the git repository (you can also use GitHub's download button *if you only want to perform tests*). Note that Git LFS is no longer used. Git LFS files are not cloned and packaged anymore.
- Install node modules and dependencies using `npm install`.
- Open the repository folder in a prompt and run `npm start`.
- If everything works, download FFmpeg for your operating system and configure it in the app settings (otherwise export won't work!).

## Compiling
Compilation is done through electron-forge v6's `make` command. No matter the platform, you can compile by running `npm run make` which is an alias to electron-forge make. It will automatically package the app before, but you can also do it using `npm run package`. More info at https://www.electronforge.io/ and https://www.electronforge.io/configuration.

Compilation settings are detailed in package.JSON at the "config" node. You can add additional configurations to export in other formats, but you need to have access to the targetted platform/OS and install required dependencies. The list of available makers is available at https://www.electronforge.io/config/makers.

FFmpeg should be installed independently and not compiled in the application.

#### ZIP
Zip maker is available for all platforms, without any dependencies required. On Windows, it will produce an executable (.exe) to run the app from anywhere on a Windows machine, without any installation process.

### Windows specific

#### WiX MSI
This maker create a Windows .msi installer. To make a .msi installer, Wix must be installed on the machine (not necessarily Windows), as well as `light` and `candle` installed from the WiX Toolkit. More info at https://www.electronforge.io/config/makers/wix-msi and https://github.com/felixrieseberg/electron-wix-msi.
**The paths for the installer assets are absolute, don't forget to change them in package.json or the make command will fail!**

### Linux specific
There are existing configurations for .deb and .rpm packages **although they have not been tested** as I have no viable Linux development environment at the moment.

#### .deb packages
.deb packages can be made on MacOS and Linux machines with `fakeroot` and `dpkg` packages installed.
See https://www.electronforge.io/config/makers/deb

#### .rpm packages
.rpm packages can be made on Linux machines with `rpm` or `rpm-build` packages installed.
See https://www.electronforge.io/config/makers/rpm.

### Mac Specific

#### .pkg packages
Although there is no support for MacOS, the application may run just fine as Electron supports MacOS. If you would like to make a .pkg package for MacOS instead or running from source, you may look at https://www.electronforge.io/config/makers/pkg.


## Using the Command Line Interface (CLI)

See `docs/cli.md` for more details.


## License
This tool is licensed under GPL-3.0-or-later

    Wav2Bar - Free software for creating audio visualization (motion design) videos
    Copyright (C) 2022  Picorims <picorims.contact@gmail.com>

    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <https://www.gnu.org/licenses/>.
