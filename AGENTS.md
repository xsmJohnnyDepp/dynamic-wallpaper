# Repository Guidelines

## Project Structure & Module Organization

This repository is a Bash-based dynamic wallpaper tool. The main runtime script is `dwall.sh`, which selects a wallpaper by current hour from `/usr/share/dynamic-wallpaper/images`; `install.sh` installs it as `/usr/bin/dwall`. Use `test.sh` for local, in-place testing before installation. `uninstall.sh` removes installed files. Wallpaper assets live under `images/<style>/`, where each style contains hour-based image files such as `0.jpg`, `6.jpg`, `12.png`, or `23.jpg`. Keep style names lowercase and descriptive, matching the directory name shown to users.

## Build, Test, and Development Commands

There is no compile step. Use these commands from the repository root:

```bash
bash -n dwall.sh install.sh test.sh uninstall.sh
./test.sh -h
./test.sh -s beach
sudo ./install.sh
sudo ./uninstall.sh
```

`bash -n` checks shell syntax without executing the scripts. `./test.sh -h` verifies option parsing and style listing. `./test.sh -s beach` exercises the local image path and changes the active desktop wallpaper. The install and uninstall scripts modify `/usr/share/dynamic-wallpaper` and `/usr/bin/dwall`, so run them only when system-level changes are intended.

## Coding Style & Naming Conventions

Use Bash with the existing script style: `#!/usr/bin/env bash`, uppercase global variables, lowercase function names where already established, and `[[ ... ]]` tests. Preserve executable bits on shell scripts. Prefer quoted variable expansions for paths and arguments. Match the existing indentation style in the touched file; avoid broad formatting-only changes. Style directory names should be lowercase kebab-case, for example `neon-dystopia`, and image names must remain numeric hour names such as `0.jpg`, `13.png`, and `23.jpg`.

## Testing Guidelines

No automated test framework is present. For script changes, run `bash -n` on all shell files and at least one `./test.sh` command. For desktop-session logic, mention the tested environment in the PR, for example `XDG_SESSION_TYPE=x11`, `DESKTOP_SESSION=plasma`, or `wayland + oguri`. For new wallpaper styles, verify that expected hour files resolve to `.jpg` or `.png` and are readable by standard image tools when available, for example `identify images/<style>/*.jpg`. Avoid `./test.sh -s <style>` unless a visible wallpaper change is acceptable.

## Commit & Pull Request Guidelines

Recent history uses short imperative or past-tense subjects such as `Add Uji wallpaper set`, `Add Kyoto wallpaper set`, and `Added plasmax11 support`. Keep commits focused and concise; separate shell behavior changes from large asset additions. Pull requests should describe the affected desktop environment or asset set, list manual test commands, link related issues, and include screenshots or previews when changing wallpapers or user-facing output.

## Security & Configuration Tips

Be careful with privileged commands in installer scripts because they run `sudo` and write under `/usr/share` and `/usr/bin`. Do not add network downloads or destructive file operations without clear user consent and documentation. Do not remove user wallpaper directories outside this project’s install path.
