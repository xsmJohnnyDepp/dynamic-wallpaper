# Repository Guidelines

## Project Structure & Module Organization

This repository is a Bash-based dynamic wallpaper tool. The main runtime script is `dwall.sh`; it is installed as `/usr/bin/dwall` by `install.sh`. Use `test.sh` for local, in-place testing before installation. `uninstall.sh` removes installed files. Wallpaper assets live under `images/<style>/`, where each style contains hour-based image files such as `0.jpg`, `6.jpg`, `12.png`, or `23.jpg`. Keep style names lowercase and descriptive, matching the directory name shown to users.

## Build, Test, and Development Commands

There is no compile step. Use these commands from the repository root:

```bash
bash -n dwall.sh install.sh test.sh uninstall.sh
./test.sh -h
./test.sh -s beach
sudo ./install.sh
sudo ./uninstall.sh
```

`bash -n` checks shell syntax without executing the scripts. `./test.sh -h` verifies option parsing and style listing. `./test.sh -s beach` exercises the local image path. The install and uninstall scripts modify `/usr/share/dynamic-wallpaper` and `/usr/bin/dwall`, so run them only when system-level changes are intended.

## Coding Style & Naming Conventions

Use Bash with the existing script style: `#!/usr/bin/env bash`, uppercase global variables, lowercase function names where already established, and `[[ ... ]]` tests. Preserve executable bits on shell scripts. Prefer quoted variable expansions for paths and arguments. Match the existing indentation style in the touched file; avoid broad formatting-only changes.

## Testing Guidelines

No automated test framework is present. For script changes, run `bash -n` on all shell files and at least one `./test.sh` command. For desktop-session logic, mention the tested environment in the PR, for example `XDG_SESSION_TYPE=x11`, `DESKTOP_SESSION=plasma`, or `wayland + oguri`. For new wallpaper styles, verify that expected hour files resolve to `.jpg` or `.png`.

## Commit & Pull Request Guidelines

Recent history uses short, imperative summaries such as `Added plasmax11 support` and `Update README.md`. Keep commits focused and concise. Pull requests should describe the affected desktop environment or asset set, list manual test commands, link related issues, and include screenshots or previews when changing wallpapers or user-facing output.

## Security & Configuration Tips

Be careful with privileged commands in installer scripts. Do not add network downloads or destructive file operations without clear user consent and documentation.
