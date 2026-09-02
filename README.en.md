# imgusev's plugins for Orca

> 🇷🇺 **Русская версия** → [README.md](README.md)

A plugin source for [Orca](https://github.com/stablyai/orca), the agent development environment (ADE) by Stably AI. Add it once and plugins install in one click, with Orca offering updates on its own.

The main one is the **Russian language pack**: [imgusev/orca-plugin-ru](https://github.com/imgusev/orca-plugin-ru) translates 98% of the interface. Details on the [project page](https://imgusev.github.io/orca-plugin-ru/).

## Adding the source

1. **Settings → Plugins** — enable the plugin system
2. **Marketplace sources → Add source**
3. Paste:

   ```
   https://github.com/imgusev/orca-plugins.git
   ```

4. On the **All** tab pick a plugin and press **Install**

## What is here

| Plugin | Description |
|---|---|
| [Русский язык для Orca](https://github.com/imgusev/orca-plugin-ru) | Russian UI translation: 13 649 of 13 838 strings (98%), native plural forms, no patching of the app. [Project page](https://imgusev.github.io/orca-plugin-ru/) |

## How it works

`orca-marketplace.json` is an index: it carries no plugin code, only links to repositories and exact tags. Orca clones the plugin from the referenced repository at the pinned `ref`, validates its manifest, and shows the requested permissions before you enable anything.

Every entry is pinned to a tag rather than a branch, so installs are reproducible and a new version appears only after the index is updated explicitly.

## Install statistics

Orca installs and updates a plugin through `git clone`, and clones the index itself when checking for updates — so installs show up in GitHub traffic data. GitHub keeps that data for 14 days only, so a workflow snapshots it daily into `data/`:

| File | What it counts |
|---|---|
| [`data/traffic-marketplace.csv`](data/traffic-marketplace.csv) | source additions and update checks |
| [`data/traffic-plugin-ru.csv`](data/traffic-plugin-ru.csv) | installs and updates of the Russian pack |

An install cannot be told apart from an update — both look like a clone.

## License

[MIT](LICENSE). The index is not officially affiliated with Stably AI.
