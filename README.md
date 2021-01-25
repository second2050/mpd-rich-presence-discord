# MPD Rich Presence for Discord

- [MPD Rich Presence for Discord](#mpd-rich-presence-for-discord)
  - [⚠️ Disclaimer ⚠️](#️-disclaimer-️)
  - [Multi App vs Single App Mode](#multi-app-vs-single-app-mode)
  - [Command Line Arguments](#command-line-arguments)
  - [Compiling](#compiling)
    - [Dependencies](#dependencies)
  - [Similar](#similar)

---

## ⚠️ Disclaimer ⚠️
This is a fork of [Stormy's mpd-rpc](https://github.com/justas-d/mpd-rich-presence-discord) and this fork just changes the used app ID and pictures so that it uses my self configured rpc app

## Multi App vs Single App Mode
* Single App Mode

  * This mode will only use a single MPD app, which will diplay the three different MPD states. (Playing, Paused and Idle)
  * This mode syncs faster than the multi-app mode.
  
* Multi App Mode

  * This mode will use multiple, unique MPD apps: 
    * `MPD (Playing)`
    * `MPD (Paused)`
    * `MPD` (Reserved for idle)
  
  * These app names will show up next to your name on the sidebar.
  
  * This mode updates slower than the single app mode.

## Command Line Arguments

Example: `mpd_discord_richpresence -h=127.0.0.1 -P=password -p=6606 --fork --no-idle --use-multiple-apps`

| Paramater| Purpose  |
|--|--|
|`-h=ADDDRESS`|The listen-address for MPD. (Defaults to `127.0.0.1`)|
|`-p=PORT`|The port which MPD is listening on. (Defaults to `6600`)|
|`-P=PASSWORD`|The password sent to MPD after the connection has been established successfully. (Default is empty, therefore no password sent.)|
|`--fork`|Forks the process into the background.|
|`--no-idle`|Disables broadcasting of the idle state.|
|`--use-multiple-apps`|Uses the Multi-App mode.|

> ⚠️ discord-rpc [will not work](https://github.com/discordapp/discord-rpc/issues/213#issuecomment-410631101) if Discord has been installed through snap (Ubuntu Software). Please download and install Discord from the [homepage](https://discordapp.com/).


## Compiling

### Dependencies
* pthread
* [discord-rpc](https://github.com/discordapp/discord-rpc)
* libmpdclient

A [build script](build.sh) and a [PKGBUILD](PKGBUILD) is included.

The CMakeFile will take care of finding discord-rpc. If it cannot find it, it will pull the discord-rpc GitHub repo and compile from source.


## Similar

* [mpv-discordRPC, noaione](https://github.com/noaione/mpv-discordRPC) - MPV
* [foo_discord, NaamloosDT/](https://github.com/NaamloosDT/foo_discord) - foobar2000 rich presence
