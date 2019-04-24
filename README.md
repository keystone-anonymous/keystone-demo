# keystone-demo
Demo host and enclave applications exercising most minimal eyrie functionality.

This demo includes a small enclave server that is capable of remote
attestation, secure channel creation, and performing a simple
word-counting computation securely.

## Suggested usage

Starting in main keystone repo (not demo):
```
./fast-setup.sh
[... run tests etc ...]
cd keystone-demo
source source.sh
./quick-start.sh
make getandsethash
make
./copy-demo.sh
cd ..
make
./scripts/run-qemu
[ in qemu ]
root / sifive
insmod keystone-driver.ko
./enclave-host.riscv &
./trusted-client.riscv 127.0.0.1
[ ... Interact with trusted client ... ]
```

Please see documentation in the docs/ directory.

./quick-start.sh will clone/build all necessary components for the
demo to run in qemu if you have already built keystone and it's sdk
tests successfully.
