# Fork of zincplusplus/habit-tracker

This repository is a fork of [zincplusplus/habit-tracker](https://github.com/zincplusplus/habit-tracker). It carries its own
patches and publishes its own releases. The fork skill and the workflows of
[codedpalette/fork-kit](https://github.com/codedpalette/fork-kit) manage it.

## Branches

| Branch | Role |
|---|---|
| `dev` | Default branch: upstream plus our patches. Releases come from here. |
| `feat/<name>`, `fix/<name>`, ... | A change for upstream, with a prefix that fits it. Never `fork/`. Cut it from the upstream commit that `dev` is based on: `git merge-base origin/dev upstream/master`. The upstream PR then holds only that change, and a merge into `dev` brings in no unreleased upstream code. |
| `fork/<name>` | A change that stays in this fork. Cut it from `dev`. Never rebase it onto upstream or open an upstream PR from it. |
| `sync/<ref>` | A parked upstream merge that conflicts, without upstream's CI. Resolve it, then merge it into `dev`. |

The fork keeps no copy of upstream's `master`, and `dev` holds none of upstream's
`.github` files, because GitHub runs upstream's workflows here with this fork's secrets.

## Releases

Fork releases are tagged `<upstream version>-patched.<N>`, for example `1.2.3-patched.2`.
Upstream's own tags never carry the `-patched.` part. N starts at 1 for each new upstream
version.

## Install

Install with [BRAT](https://github.com/TfTHacker/obsidian42-brat): add the beta plugin `codedpalette/habit-tracker`. The plugin id `habit-tracker-21-patched` and the name "Habit Tracker 21 (patched)" keep it apart from the store version of Habit Tracker 21. Install one of the two, not both.

## Configuration

`.github/fork.yml` holds the configuration. Edit it on `dev` only.
