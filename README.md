# Swarm Builder

Builds AstroSwarm on a Vagrant virtual machine running Debian, or on a Raspberry Pi running Raspbian.

## How it works

`bootstrap-pi <pi ip address>` adds your public ssh key to the authorized_keys file on a Raspberry Pi so that the builder can ssh into the box.

`deploy-pi <pi ip address>` builds AstroSwarm on the Raspberry Pi.

`deploy-vagrant` launches a Debian VM (if it's not already running), and builds AstroSwarm on the VM.

## Requirements

* Vagrant
* Virtualbox
* Public/private RSA keypair stored in ~/.ssh

Current tooling assumes a Mac OS X development system.

## Quick Start

### Building on a Debian VM

1. Run `./deploy-pi`
1. Access AstroSwarm at `http://localhost:8000`

### Building on a Raspberry Pi

1. Build an AstroSwarm-compatible Raspberry Pi Micro SD card using `swarm_pi_flasher`.
1. Place Micro SD card into Raspberry Pi, turn it on, and find its IP address on your network. For my manufacturer, `arp -a | grep b8:27` works well for this.
1. Run `./deploy-pi <pi ip address>` to build AstroSwarm on the Raspberry Pi.
1. Access AstroSwarm at `http://<pi ip address>:8000`
