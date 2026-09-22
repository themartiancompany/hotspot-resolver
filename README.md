[comment]: <> (SPDX-License-Identifier: AGPL-3.0)

[comment]: <> (------------------------------------------------------)
[comment]: <> (Copyright © 2024, 2025, 2026  Pellegrino Prevete)
[comment]: <> (All rights reserved)
[comment]: <> (------------------------------------------------------)

[comment]: <> (This program is free software: you can redistribute)
[comment]: <> (it and/or modify it under the terms of the GNU Affero)
[comment]: <> (General Public License as published by the Free)
[comment]: <> (Software Foundation, either version 3 of the License.)

[comment]: <> (This program is distributed in the hope that it will be)
[comment]: <> (useful, but WITHOUT ANY WARRANTY; without even the)
[comment]: <> (implied warranty of MERCHANTABILITY or FITNESS FOR)
[comment]: <> (A PARTICULAR PURPOSE. See the)
[comment]: <> (See the GNU Affero General Public License for)
[comment]: <> (more details.)

[comment]: <> (You should have received a copy of the GNU Affero)
[comment]: <> (General Public License along with this program.)
[comment]: <> (If not, see <https://www.gnu.org/licenses/>.)

# Hotspot resolver

In recent versions of Android (>10) the WiFi hotspot
subnet changes at every boot together with the hotspot
SSID; this makes hard for common users to reliably
evaluate the IP address for another device on the local
network.

Hotspot resolver correctly returns the
address for an host across reboots of the Android
device which acts as hotspot.

This program is a dependency for the
[DynSSH](
  https://github.com/themartiancompany/dynssh)
dynamic SSH client.

## How to use

Let's say you know the `goody` host you want to connect
to on the hotspot network has address usually ending in `42`.

To set `42` as a global setting for `goody you type

```bash
hotspot-resolver \
  -G \
  set \
    "goody" \
      "42"
```

So now whenever you type

```bash
hotspot-resolver \
  get \
    "goody" \
      "42"
```

you'll get the correct address for `goody` regardless
of which specific Android hotspot instance they are connected
to for easy use in other programs.

## Installation

The program in this source repo
can be installed from source using GNU Make.

```bash
make \
  install
```

The collection has been officially published
on the the uncensorable
[Ur](
  https://github.com/themartiancompany/ur)
user repository and application store as
`hotspot-resolver`.
The source code is published on the
[Ethereum Virtual Machine File System](
  https://github.com/themartiancompany/evmfs)
so it can't possibly be taken down.

To install it from there just type

```bash
ur \
  hotspot-resolver
```

The package has been released on the
[NodeJS Package Registry](
  https://npmjs.com/package/evm-contracts-tools)
as well as `hotspot-resolver` and can be installed
with

```bash
npm \
  install \
    hotspot-resolver
```

The NPM Registry package does not include the Bash code
and it's fully in Javascript.

A censorable HTTP Github mirror of the recipe published there,
containing a full list of the software dependencies needed to run the
tools is hosted on
[hotspot-resolver-ur](
  https://github.com/themartiancompany/hotspot-resolver-ur).

Be aware the mirror could go offline any time as Github and more
in general all HTTP resources are inherently unstable and censorable.

## License

This program is released by Pellegrino Prevete under the terms
of the GNU Affero General Public License version 3.
