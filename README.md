The simplest way to run AArch64 clickhouse binary for testing on AMD64 machine:

1. Install QEMU:
```
sudo apt install qemu-user-static
```

2. Install the blobs from this repository:
```
sudo cp -r aarch64/* /
```

3. Download the AArch64 binary from "ClickHouse special build check".

4. Run it with QEMU:

```
qemu-aarch64-static clickhouse-aarch64 server
```

Alternatively you can install binfmt-misc:

```
docker run --rm --privileged multiarch/qemu-user-static:register --reset
```

And then run ClickHouse binary directly:

```
clickhouse-aarch64 server
```
