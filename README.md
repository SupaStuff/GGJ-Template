# Unity Template for Global Game Jam

This project template follows the tutorials from [GameCI](https://game.ci/docs) using the simple example (one platform) and a Personal License. The releases are in the format required to make GGJ submissions. Namely, the zip contains:

- Source files moved from _PROJECTNAME/_ to _src/_
- Build in _release/_
- Project wiki is cloned to _press/_
- **License** is CC0
- _other/_ is omitted because what else could be important?

## How to use

1. Fork this repo
2. Set up the project wiki with appropriate pages for things like YouTube links
3. Rename _GGJ-Game/_ to the name of your game (no spaces)
4. Change [`PROJECT_NAME`](https://github.com/SupaStuff/GGJ-Template/blob/master/.github/workflows/main.yml#L12) from "GGJ-Game" to the same name you gave the folder
5. Optionally, edit the [target branch](https://github.com/SupaStuff/GGJ-Template/blob/master/.github/workflows/main.yml#L7) if you use anything other than `master` as your default branch (I guess [`main`](https://sfconservancy.org/news/2020/jun/23/gitbranchname/))

> TODO: Explore [OpenUPM](https://openupm.com/)

### Activate License

You also need to activate a Unity license once to use the build/release job.
Go to `Github` > `<Your repository>` > `Actions` > `Acquire activation file (One time per repo)`
and run this workflow. Once it's done, follow these steps:

> Copied from <https://game.ci/docs/github/activation>

- Download the manual activation file that now appeared as an artifact.
- Visit [license.unity3d.com](https://license.unity3d.com/manual) and upload it.
- You should now receive your license file (Unity_v20XX.x.ulf) as a download.
- Open `Github` > `<Your repository>` > `Settings` > `Secrets`.
- Create a secret called `UNITY_LICENSE` and copy the contents your license file into it.

### Screenshots

You'll also want to push a screenshot and other media to the wiki so that it gets bundled in the zip's _press/_ directory.
There's no way to do this in the web editor, so you'll have to clone the wiki and push the media that way.
Ideally, you would also reference any pushed screenshots/media on the wiki's home page.
(Home is omitted from the zip since it won't be useful for submission. You can change this [here](https://github.com/SupaStuff/GGJ-Template/blob/master/.github/workflows/main.yml#L76))

## Limitations

1. To use GameCI for Unity version > 2019.2, this template uses GameCI actions that are still in alpha. This is probably why Test and Build steps build a new Docker image every time...
2. Test step takes forever even with 0 tests! So it's commented out. This is probably due to it downloading assets, which should probably be done in a previous step.
3. Due to the long duration of the main workflow you probably don't want to run this in PR, so it only runs on push/merge to master.
