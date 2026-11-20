# agent-device-access builds

Test builds of `device-access-node`, the program that runs on a device for agent-device-access: an AI agent
(Claude, Codex) or a person reaches a Linux device with a pass signed by the device's owner, and the device checks
that pass itself. The source code will be published separately after review.

Status: pre-release test builds. Not for production use.

## Files in each release

1. `device-access-node-linux-arm64` and `device-access-node-linux-amd64`: static Linux binaries.
2. `*.sha256`: the SHA-256 of each binary.
3. `THIRD_PARTY_NOTICES.txt`: the licences of the Go toolchain and the modules built into the binaries.

## Install

The device's owner prints a one-line install command with `device-access invite` and runs it in a shell on the
device. The line downloads the binary from a release here, checks its SHA-256, and runs `join` with a one-time
invite. The invite contains a secret: do not share the line.

To check a download by hand:

    curl -fsSLO https://github.com/litvak-daniil/agent-device-access-builds/releases/download/<tag>/device-access-node-linux-arm64
    curl -fsSLO https://github.com/litvak-daniil/agent-device-access-builds/releases/download/<tag>/device-access-node-linux-arm64.sha256
    sha256sum -c device-access-node-linux-arm64.sha256

## Licence

Apache License 2.0, see [LICENSE](LICENSE). Third-party licences: [THIRD_PARTY_NOTICES.txt](THIRD_PARTY_NOTICES.txt).
