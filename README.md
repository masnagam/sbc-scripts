# Scripts for single board computers

This repository contains several scripts which are intended to be used on single
board computers like Raspberry Pi.

Each script can be run with `curl` and `sh` like below:

```sh
curl -fsSL https://raw.githubusercontent.com/masnagam/sbc-scripts/master/install-px4-drv \
  | sh -s -- --dkms install
```

The filename of a script for a specific SBC starts with a label listed below:

* `rpi`: Raspbian/Raspberry Pi
* `rock64`: Armbian/ROCK64

For details, see comments in each script or help which is shown by running with
the `-h` or `--help` option like below:

```sh
curl -fsSL https://raw.githubusercontent.com/masnagam/sbc-scripts/master/get-docker-compose \
  | sh -s -- -h
```
