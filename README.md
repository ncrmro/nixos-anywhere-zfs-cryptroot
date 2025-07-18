# nixos-anywhere-examples

Checkout the [flake.nix](flake.nix) for examples tested on different hosters.

```shell
nix run github:nix-community/nixos-anywhere -- \
--flake .#generic \
--generate-hardware-config nixos-generate-config ./hardware-configuration.nix \
root@192.168.122.62
```

A lof of this is bassed on help from ElvishJerricco on the NixOS forums [here](https://discourse.nixos.org/t/import-zpool-before-luks-with-systemd-on-boot/65400/17)

```
nix add install nixpkgs#nixos-rebuild
nixos-rebuild switch --flake .#generic --target-host "root@root@192.168.1.124"
```

```
nix-shell --extra-experimental-features flakes --packages sbctl
sbctl create-keys
sbctl enroll-keys --microsoft

# View current slots
systemd-cryptenroll /dev/zvol/rpool/credstore
# Allow unlocking with TPM
systemd-cryptenroll /dev/zvol/rpool/credstore --tpm2-device=auto --tpm2-pcrs=1,7 # --wipe-slot=1
```