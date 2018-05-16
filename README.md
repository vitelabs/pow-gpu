# Banano work server

This project is a dedicated work server for [the Banano cryptocurrency](https://banano.co.in/).

It supports the `work_generate`, `work_cancel`, and `work_validate` commands from the Nano RPC.
For details on these commands, see [the Nano RPC documentation](https://github.com/nanocurrency/raiblocks/wiki/RPC-protocol), as it works the same in Banano.

To see available command line options, run `banano-work-server --help`.

## Installation

### OpenCL

Ubuntu:

```
sudo apt install ocl-icd-opencl-dev
```

Fedora:

```
sudo dnf install ocl-icd-devel
```

### Rust

```
curl https://sh.rustup.rs -sSf | sh
```

### Build and run

```
git clone https://github.com/meltingice/banano-work-server.git
cd banano-work-server
cargo build --release
cd target/release
./banano-work-server --help
```
