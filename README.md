# xdg-sandbox

Run commands in an isolated environment with temporary XDG directories.

## Usage
```
xdg-sandbox [-qdrcv] command [args...]
```

## Options
| Flag | Description                                     |
|------|-------------------------------------------------|
| `-q` | Quiet mode — suppress command output            |
| `-d` | Delete the sandbox directory on exit            |
| `-r` | Create `$XDG_RUNTIME_DIR` inside the sandbox    |
| `-c` | Copy shell rc files (`.zshrc`, `.bashrc`) into the sandbox |
| `-v` | Verbose mode — print info messages              |

The sandbox directory is created under the environment variable `$SANDBOX_DIR` if set, or via `mktemp -d` otherwise. It sets `$HOME` and all `XDG_*` environment variables to point inside the temporary directory, preventing commands from writing to your real home.

## Examples
```sh
# Show that $HOME points inside the sandbox
xdg-sandbox bash -c 'echo "$HOME"'

# Run with auto-cleanup and see where the sandbox was created
xdg-sandbox -dv true
```

## Install
Build with `makepkg` on Arch Linux. The script is installed as `xdg-sandbox` (originally named `sandbox`, but that name was already taken on the AUR). Set `INSTALL_AS_SANDBOX=true` to install as `sandbox` instead.
