# usteer-ng

This repository is a fork of [NilsRo/usteer-ng](https://github.com/NilsRo/usteer-ng).

It is maintained as a small downstream fork for OpenWrt, with a few targeted behavior changes while staying close to upstream where possible.

## Fork-specific changes

Current downstream changes:

- **Phase 1**: stricter communication suppression when `local_mode=1`
- **Phase 2**: early hard-limit denial for weak unconnected probe requests

## Functions

`usteer-ng` is a client steering daemon for OpenWrt.  
It helps improve roaming and band-steering decisions across multiple APs in the same ESS.

Main functions include:

- synchronization of neighbor reports between APs
- policy-based handling of probe / association / authentication requests
- steering based on signal/SNR and channel conditions
- configurable roaming and steering behavior

## Installation

`usteer-ng` is available as an OpenWrt package.

It conflicts with the original `usteer` package, so both should not be installed at the same time.

Example:

```sh
opkg update
opkg remove --force-depends usteer
opkg install /root/usteer/*.ipk luci-app-usteer
