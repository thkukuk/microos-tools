# MicroOS Tools
Files and scripts for openSUSE MicroOS

## SELinux

MicroOS has support for SELinux.
If the file `/etc/selinux/.autorelabel` exists, the dracut module
`98selinux-microos` will label the root filesystem including
`/etc` and `/var`. The selinux-autorelabel-generator will generate
services to relabel other mountpoints during boot.

There is a script for automated testing of this in test/test.sh.

## systemd services

### import-pubring-from-rpmdb.service

The `import-pubring-from-rpmdb.service` imports the keys from rpmdb int
`/etc/systemd/import-pubring.gpg`.

### printenv.service

The `printenv.service` is to debug which environment variables exist
by default. It just calls `printenv`.

## development tools

* microos-rw: switches the root file system to read-write
* microos-ro: resets btrfs property to read-only again.
* rpmorphan: display files not owned by rpm
* rpm-sortbysize: list all installed packages sorted by size
