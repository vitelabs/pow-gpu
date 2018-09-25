# DPoW work server

This project is a dedicated work server for [the Distributed Proof of Work System](https://www.reddit.com/r/nanocurrency/comments/94lx28/distributed_nano_pow_subscription_system/). (website TBD)

It supports the `work_generate`, `work_cancel`, and `work_validate` commands from the Nano RPC.
For details on these commands, see [the Nano RPC documentation](https://github.com/nanocurrency/raiblocks/wiki/RPC-protocol).

To see available command line options, run `dpow-work-server --help`.

## Modifications

The following modifications have been made to acomodate a variable work difficulty threshold:

- `work_generate` request now takes a mandatory **threshold** field:

    ```json
    {
        "action": "work_generate",  
        "hash": "718CC2121C3E641059BC1C2CFC45666C99E8AE922F7A807B7D07B62C995D79E2",
        "threshold": "ffffffc000000000"
    }
    ```

- `work_validate` request now takes a mandatory "threshold" field:

    ```json
    {
        "action": "work_validate",  
        "hash": "718CC2121C3E641059BC1C2CFC45666C99E8AE922F7A807B7D07B62C995D79E2",
        "work": "631610a77f76d909",
        "threshold": "ffffffc000000000",
    }
    ```

Useful **threshold** values:

- `ffffffc000000000` for Nano

- `fffffe0000000000` for Banano


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
git clone https://github.com/guilhermelawless/dpow-work-server.git
cd dpow-work-server
cargo build --release
cd target/release
./dpow-work-server --help
```
