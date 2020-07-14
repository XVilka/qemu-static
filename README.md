# qemu-static

The purpose of this project is to build a highly compatible QEMU binary package
for linux to use for testing.

It allows to build recent QEMU version, sometimes unreleased commit-revs, and
sometimes with custom patches. For this reason, distro-based QEMU packages are
unsuitable.

The overall strategy is to use Alpine Linux to host a QEMU build and link
statically to all possible libraries.


## Usage

Just run the script that will build the container, run it, and copy the ready
artifacts from it:

```sh
./build
```

Then review final artifact(s)

```sh
ls -al artifact/
```
