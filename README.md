# My_Learning_Fuel

Learn everything about Fuel Blockchain

## Overview

- [Sway](https://fuellabs.github.io/sway/v0.31.3/index.html) eDSL is used for writing smart contracts
  - Contains `forc` as CDT (Contract Development Toolkit)

## Installation

### CLI

#### Rust

Install [Rust](https://github.com/abhi3700/My_Learning-Rust/blob/main/README.md#installation)

#### Fuelup

Install `Fuelup` package manager for Fuel that installs the toolchains from respective channels.

- [ ] M-1: Referred [this](https://github.com/FuelLabs/fuelup#quickstart), but got downloading error via `$ curl --proto '=https' --tlsv1.2 -sSf https://fuellabs.github.io/fuelup/fuelup-init.sh | sh`
- [x] M-2: Followed this, Downloaded binary (aarch64_mac) from [here](https://github.com/FuelLabs/fuelup/releases/).

```bash
$ code ~/.zprofile

# edit the file and add the following line
# fuel binary release setup v0.18.0
export PATH="$HOME/fuelup-0.18.0-aarch64-apple-darwin:$PATH"

$ source ~/.zprofile
```

- Verify installation

```console
$ fuelup --version
```

- Set toolchain to `beta-2-aarch64-apple-darwin`

```console
$ fuelup toolchain install beta-2
```

- Check for the toolchain as beta-2-aarch64-apple-darwin

```console
$ fuelup show
```

#### Component

`forc` build tool added as a component to the default (beta-2) channel of the toolchain - `fuelup`.

> It is also called as "**F**uel **orc**hestrator" (forc)

Install component

- [ ] M-1: `$ fuelup component add forc@0.30.1` for custom version
  - showing error
  - adding the binaries into the `~/.fuelup/bin`, but when running `forc` command, it is not able to find the binary from that directory, instead needed to be installed using the 2nd method.
- [x] M-2: Installation from source
  > min. version of `rustc` required is `1.67.0` during this time. Updated with `$ rustup update` -> `$ rustup default stable-aarch64-apple-darwin ` -> `$ rustup update beta-aarch64-apple-darwin` -> `$ rustup default nightly-aarch64-apple-darwin` for all 3 channels.

```bash
$ git clone https://github.com/FuelLabs/sway.git
$ cd sway/forc
$ cargo build
# install forc binary
$ cargo install --path .
# this would install into ~/.cargo/bin
```

`forc` is installed at this:

```console
❯ which forc                                                                                                                                                                       ⏎
~/.cargo/bin/forc
```

Confirm the Sway toolchain built successfully by running `cargo run --bin forc -- --help` from the root of the repo.

---

Available binaries in the repo:

```console
available binaries: examples-checker, forc, forc-deploy, forc-doc, forc-fmt, forc-lsp, forc-run, forc-submit, forc-tx, mdbook-forc-documenter, opt, test
```

### Editor

- VSCode is recommended
- Extensions:
  - Sway extension
  - rust-analyzer

## Networks

- Mainnet
- Testnet

## SDKs

- [Fuel Rust SDK](https://fuellabs.github.io/fuels-rs/v0.32.2/index.html)
- [Fuel Rust Typescript SDK](https://fuellabs.github.io/fuels-ts/)

## References

- [Fuel forum](https://forum.fuel.network/)
- [Github](https://github.com/FuelLabs)
  - [Fuelup](https://github.com/FuelLabs/fuelup)
  - [Sway](https://github.com/FuelLabs/sway)
- [Sway language book w.r.t SC](https://fuellabs.github.io/sway/v0.35.1/book/index.html)
- [Sway language reference](https://fuellabs.github.io/sway/master/reference/)
- [Fuel specifications](https://fuellabs.github.io/fuel-specs/master/fuel-specs.html)
