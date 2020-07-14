# qemu-static

The purpose of this project is to build a highly compatible QEMU binary package
for linux to use for testing.

It allows to build recent QEMU version, sometimes unreleased commit-revs, and
sometimes with custom patches. For this reason, distro-based QEMU packages are
unsuitable.

The overall strategy is to use Alpine Linux to host a QEMU build and link
statically to all possible libraries.


## build docker image
```
docker build --tag qemu .
```

## run container, save ID, copy artifact(s)
```
docker run -it --cidfile=qemu.cid qemu true
docker cp "$(cat qemu.cid):work/artifact/." artifact
```

## review final artifact(s)
```
ls -al artifact/
```
