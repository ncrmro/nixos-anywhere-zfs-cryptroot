# nixos-anywhere-examples

Checkout the [flake.nix](flake.nix) for examples tested on different hosters.

```shell
nix run github:nix-community/nixos-anywhere -- \
--flake .#generic \
--generate-hardware-config nixos-generate-config ./hardware-configuration.nix \
root@192.168.122.62
```

A lof of this is bassed on help from ElvishJerricco on the NixOS forums [here](https://discourse.nixos.org/t/import-zpool-before-luks-with-systemd-on-boot/65400/17)