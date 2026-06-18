# Repository Guidelines

## Project Structure & Module Organization

This repository is a Bash-based dynamic wallpaper tool. The main runtime script is `dwall.sh`, which selects a wallpaper by current hour from `/usr/share/dynamic-wallpaper/images`. `test.sh` mirrors the runtime behavior but reads assets from the local `images/` directory for pre-install checks. `install.sh` copies scripts and assets into `/usr/share/dynamic-wallpaper` and creates `/usr/bin/dwall`; `uninstall.sh` removes installed files. Wallpaper sets live under `images/<style>/` and should contain hour-based files named `0` through `23` with `.jpg` or `.png` extensions.

## Build, Test, and Development Commands

- `bash -n dwall.sh install.sh test.sh uninstall.sh`: syntax-check shell scripts without changing the desktop.
- `./test.sh -h`: list detected local styles and verify the help path.
- `./test.sh -s firewatch`: apply a local wallpaper style for an end-to-end check; this changes the active desktop wallpaper.
- `sudo ./install.sh`: install `dwall` system-wide after local validation.

There is no compile step or package manager workflow in this project.

## Coding Style & Naming Conventions

Keep scripts portable Bash with existing function naming and option parsing patterns. Use tabs or consistent indentation matching nearby code, quote paths and variables where practical, and avoid introducing external dependencies beyond the documented desktop tools. Style directory names should be lowercase kebab-case, for example `neon-dystopia`, and image names must remain numeric hour names such as `0.jpg`, `13.png`, and `23.jpg`.

## Testing Guidelines

No formal test framework or coverage target exists. For script-only changes, run `bash -n` on all shell scripts and `./test.sh -h`. For wallpaper-set changes, verify that the new style has valid `0-23` assets and that each file is readable by standard image tools when available, for example `identify images/<style>/*.jpg`. Avoid `./test.sh -s <style>` unless a visible wallpaper change is acceptable.

## Commit & Pull Request Guidelines

Recent history uses short imperative or past-tense subjects such as `Add Uji wallpaper set`, `Add Kyoto wallpaper set`, and `Added plasmax11 support`. Keep commits focused: separate shell behavior changes from large asset additions. Pull requests should describe the affected style or desktop environment, list manual checks performed, and include previews or screenshots when adding or replacing wallpaper assets.

## Security & Configuration Tips

Be careful with installer edits because they run `sudo` and write under `/usr/share` and `/usr/bin`. Do not remove user wallpaper directories outside this project’s install path.
