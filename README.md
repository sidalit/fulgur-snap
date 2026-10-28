<div align="center">

<img src="snap/gui/fulgur.png" alt="Fulgur logo" width="128" />

# Fulgur

**A fast text editor with themes and encrypted synchronization.**

[![fulgur](https://snapcraft.io/fulgur/badge.svg)](https://snapcraft.io/fulgur)
[![Base: core26](https://img.shields.io/badge/Base-core26-2C8C3C?logo=canonical&logoColor=white)](https://snapcraft.io/core26)
![Confinement: strict](https://img.shields.io/badge/Confinement-strict-2C8C3C)
[![Maintainer: sidaliteir](https://img.shields.io/badge/Maintainer-sidaliteir-2C8C3C?logo=snapcraft&logoColor=white)](https://snapcraft.io/publisher/sidaliteir)
![Architectures: amd64 and arm64](https://img.shields.io/badge/Architectures-amd64%20%7C%20arm64-2C8C3C?logo=linux&logoColor=white)

[Getting Started](#getting-started) · [Configure](#configure) · [Limitations](#limitations) · [Build](#build) · [Support](#support) · [License](#license)

Unofficial snap packaging for [Fulgur](https://github.com/fulgur-app/Fulgur), a text editor with Markdown previews, themes, remote editing and encrypted file sharing.

</div>

---

## Getting Started

<a href="https://snapcraft.io/fulgur"><img alt="Get it from the Snap Store" src="https://snapcraft.io/en/dark/install.svg" width="180"></a>

```bash
sudo snap install fulgur
fulgur
```

Launch from the terminal or your application menu.

## Configure

Manage preferences in the app. Settings and themes are stored in `~/snap/fulgur/current/.fulgur`. There are no `snap set` options.

| Optional access | Command |
| --- | --- |
| Desktop keyring for encrypted synchronization | `sudo snap connect fulgur:password-manager-service` |
| Private keys in your host `~/.ssh` directory | `sudo snap connect fulgur:ssh-keys` |
| Files on removable storage | `sudo snap connect fulgur:removable-media` |

Synchronization requires a running desktop keyring and a [Fulgurant server](https://github.com/fulgur-app/fulgurant). SSH/SFTP supports passwords or explicitly selected key files; trusted host keys are stored in `~/snap/fulgur/current/.ssh/known_hosts`.

## Limitations

- Host SSH agents and automatic discovery of host SSH configuration are unavailable.
- Printing through the host browser is restricted by the snap's private temporary directory; open the saved document in another application to print it.
- Application updates are managed by snapd.

## Build

```bash
git clone https://github.com/sidalit/fulgur-snap.git
cd fulgur-snap
sudo snap install snapcraft --classic
snapcraft pack
```

## Support

- **Installation or snap issues:** [open a packaging issue](https://github.com/sidalit/fulgur-snap/issues).
- **Application bugs:** [report them upstream](https://github.com/fulgur-app/Fulgur/issues).

## License

Snap packaging: [MIT](https://github.com/sidalit/fulgur-snap/blob/main/LICENSE).
