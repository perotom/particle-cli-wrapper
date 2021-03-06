# Particle CLI Installer

Downloads and installs the latest CLI wrapper from binaries.particle.io,
executes it a first time to install Node.js and the particle-cli module.

*This installer is based on the CLI installer by Daniel Sullivan. Thanks!*

## Releasing the installer

- Concourse builds and signs the executable on each git push
- Download the dev version of the installer from <https://binaries.particle.io/cli/installer/windows/ParticleCLISetup-dev.exe> and <https://binaries.particle.io/cli/installer/windows/ParticleDriversSetup-dev.exe>
- After testing those installers, open the Concourse `release-installer` job and click the + to trigger it. It will copy the files to <https://binaries.particle.io/cli/installer/windows/ParticleCLISetup.exe> and <https://binaries.particle.io/cli/installer/windows/ParticleDriversSetup.exe>

## Compile installer

- Download and install Nullsoft Installer System (NSIS) version 3
- Run `MakeNSISW ParticleCLISetup.nsi` to get `ParticleCLISetupLI.exe`

## Included components

The driver installer `wdi-simple.exe` is part of [libwdi](https://github.com/pbatard/libwdi). To rebuild it, you need to download libwdi, the [Windows Driver Kit (WDK)](https://msdn.microsoft.com/en-us/library/windows/hardware/ff557573(v=vs.85).aspx) and the [libusbK USB driver SDK](https://sourceforge.net/projects/libusbk/files/libusbK-release). Follow the instructions to build libwdi using the WDK.

The Device Firmware Update (DFU) tools are from <http://dfu-util.sourceforge.net/>

See [licences.txt](/installer/windows/licenses.txt) for more info on the
open source licenses.
