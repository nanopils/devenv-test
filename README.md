## Introduction

Devenv is a development environment that comes with Nix and Cachix.

This is the minimal version for a starter project.

## Setup

### Nix

[Official setup](https://nixos.org/download):
```bash
sh <(curl -L https://nixos.org/nix/install) --daemon
```

Or as [this guide](https://github.com/mcdonc/.nixconfig/blob/master/videos/devenv-ubuntu/script.rst) suggests:
```bash
curl --proto '=https' --tlsv1.2 -sSf -L https://install.determinate.systems/nix | sh -s -- install
```
### Devenv

```bash
echo "trusted-users = $(whoami)" | sudo tee -a /etc/nix/nix.conf
nix profile install nixpkgs#cachix
cachix use devenv
nix profile install --accept-flake-config tarball+https://install.devenv.sh/latest
# The command above installs devenv and takes som time...
```

Devenv is now installed!
## Initializing a project

Run this in you project root:
```bash
devenv init
```
## Using Devenv

```bash
cd <path/to/project>
devenv shell
# installing the shell...
devenv up
