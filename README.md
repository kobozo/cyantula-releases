# cyantula downloads

Installers and releases for [cyantula](https://kobozo.io), the internal app
platform by Kobozo. The product source is maintained in a separate private
repository; this repository is the distribution channel.

## Install

On a Proxmox VE host, as root, one line creates a container, installs cyantula
in it and prints the link to the setup wizard:

```bash
bash -c "$(curl -fsSL https://github.com/kobozo/cyantula-releases/releases/latest/download/proxmox.sh)"
```

On any Debian or Ubuntu machine with docker (or where docker may be installed):

```bash
curl -fsSL https://github.com/kobozo/cyantula-releases/releases/latest/download/install.sh | sudo bash
```

Either way the platform is configured in the browser afterwards, at `/setup`,
with the one-time token the installer prints. The machine then follows the
stable channel and updates itself; `cyantula status`, `cyantula update` and
`cyantula rollback` are the day-to-day commands.

## Releases

Every release carries `manifest.json` and its Ed25519 signature; the
installer refuses anything the release key did not sign. `SHA256SUMS` lists the
checksums. The `edge` pre-release is a rolling build of the development branch.

This repository is the public channel. Until `RELEASES_TOKEN` is set on the
source repository, edge builds are also published as GitHub Releases on the
private source repo so CI can ship without a cross-repo token.

For hosting, support and contact requests, visit [kobozo.io](https://kobozo.io/contact/).
