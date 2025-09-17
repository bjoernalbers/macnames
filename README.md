# macnames - Get or set all macOS device names at once

Your Mac has **three different system names**:

1. **ComputerName** — The user-friendly name shown in the Finder and System Settings.
2. **LocalHostName** — The Bonjour name (e.g. `MacBook-Pro.local`).
3. **HostName** — The low-level system name used in `hostname(1)` and in terminal prompts.

This shell script allows you to **get or set all three names at once** using `scutil`.

## Usage

### Show current names (no install required)

```sh
curl -fsSL https://github.com/bjoernalbers/macnames/releases/latest/download/macnames \
    | sh -s
```

Sample output:

```
ComputerName:   Mac42
LocalHostName:  Mac42
HostName:       -
```

### Set all names (requires sudo)

```
curl -fsSL https://github.com/bjoernalbers/macnames/releases/latest/download/macnames \
    | sudo sh -s -- "Mac3000"
```

This will set all three system names to "Mac3000".

## About Naming

- HostName and LocalHostName must follow stricter rules (no spaces, no umlauts, ASCII only).
- The script will validate the name before applying changes.
- If HostName is not set, it will show "-" in the output (in this case macOS
  defaults to "Mac" in your Terminal prompt).

## Security

The script `macnames` is a single POSIX-compliant file.
To review before execution:

```
curl -fsSL https://github.com/bjoernalbers/macnames/releases/latest/download/macnames
```
