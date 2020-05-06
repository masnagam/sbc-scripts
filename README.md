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

## Docker images for `get-docker-compose`

Docker Hub:

* https://hub.docker.com/r/masnagam/docker-compose

Supported platforms:

* alpine
* debian (main platform)

Supported architectures:

* amd64
* arm32v7
* arm32v8

### Invoke the build job

Run a script like below:

```shell
REPO=masnagam/sbc-scripts
GITHUB_TOKEN='token...'
VERSION='1.25.4'

JSON=$(cat <<EOF
{
  "event_type": "build-docker-compose",
  "client_payload": {
    "version": "$VERSION",
    "latest": true
  }
}
EOF
)

echo "$JSON" | curl https://api.github.com/repos/$REPO/dispatches \
  -X POST -d @- \
  -H "Authorization: token $GITHUB_TOKEN" \
  -H "Content-Type: application/json"
```

## License

Licensed under either of

* Apache License, Version 2.0
  ([LICENSE-APACHE] or http://www.apache.org/licenses/LICENSE-2.0)
* MIT License
  ([LICENSE-MIT] or http://opensource.org/licenses/MIT)

at your option.

Unless you explicitly state otherwise, any contribution intentionally submitted
for inclusion in this project by you, as defined in the Apache-2.0 license,
shall be dual licensed as above, without any additional terms or conditions.

[LICENSE-APACHE]: ./LICENSE-APACHE
[LICENSE-MIT]: ./LICENSE-MIT
