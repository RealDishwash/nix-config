# Nix Config Bootstrap

Use this on a new machine after cloning this repo.

## 1) Clone the repo

```bash
git clone <your-repo-url> ~/nix-config
cd ~/nix-config
```

## 2) First run (no manual nix.conf edit)

If `flakes` are not enabled yet, pass them only for the bootstrap command:

### Home Manager standalone

```bash
nix --extra-experimental-features "nix-command flakes" run home-manager -- switch --flake .#vishwas
```

## 3) Normal runs (after bootstrap)

Once your Home Manager / system config manages `nix.conf`, you can use normal commands:

### Home Manager standalone

```bash
home-manager switch --flake .#vishwas
```

## 4) Find available flake outputs

```bash
nix flake show
```

Use the output names from your flake.

For this repo, the Home Manager target is:

```bash
.#vishwas
```

This flake currently defines only `homeConfigurations` (no `nixosConfigurations` or `darwinConfigurations`).
