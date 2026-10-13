# Auto Kick

**The CPU kicks for you. You play every other snap.**

Auto Kick is a small add-on for College Football 27. On the kick types you pick, the CPU kicks for you on your own
team's kicks: field goals and extra points, and punts. You still call the play. The game then snaps the ball as soon
as the kicker is set, or, with **Control the Snap** on, when you press your snap button. You play offense,
defense and the returns yourself; the CPU just takes the kick.

- Works with the MMC Mod Manager: you launch the game from the Mod Manager, and Auto Kick loads itself about 30
  seconds after the game starts.
- No `.fbmod` and no game files are changed. It works with whatever mods you already use.

## What's in the download

```
AutoKick.exe          the Auto Kick app: install, settings and status
README.md             this file
payload\              what the app copies into the Mod Manager (leave it next to AutoKick.exe)
```

## Install

1. Close the game and the Mod Manager.
2. Unzip the download anywhere (for example your Desktop) and run **AutoKick.exe**.
3. The app looks for your Mod Manager and shows the folder it found. If it's the wrong one, or it didn't find one,
   click **Browse...** and pick the Mod Manager folder (the one with `MMCModManager.exe` in it).
4. Click **Install**.
5. **Restart the Mod Manager**: if it was open while you installed, close it and start it again. The Mod Manager
   only picks up plugins when it starts, so one that was already open never loads Auto Kick. The app reminds you
   while that Mod Manager is still running.
6. Launch the game from the Mod Manager as usual.

The app puts these files in the Mod Manager:

```
<Mod Manager>\Plugins\AutoKickPlugin.dll
<Mod Manager>\Plugins\AutoKick\   autokick.dll, autokick.ini (your settings), logs
```

**Mod Manager in Program Files?** Windows only lets administrator programs write there. The app tells you, and its
**Allow Auto Kick to write here** button asks Windows for permission once (one prompt). Or move the Mod Manager
folder somewhere else, for example `C:\Games`, and pick it again with Browse.

## Settings

| Setting | Default | What it does |
|---------|---------|--------------|
| **Auto kick** | on | The master switch. Off = every kick is yours, as normal. |
| **Field goals and extra points** | on | The CPU kicks your field goals and PATs. |
| **Punts** | on | The CPU kicks your punts. |
| **Kickoffs** | off | The CPU kicks your kickoffs. |
| **Aim kickoffs at the play's side** | off | Under Kickoffs (needs Kickoffs on). The CPU kicks to the side of the kickoff play you call: left, middle or right. A safety kick follows its Punt Left / Middle / Right play the same way. Squib and onside kicks keep their own aim. Off: the CPU picks its own spot. |
| **Control the Snap** | off | On the field goals, extra points and punts the CPU takes, the ball is snapped when you press your snap button, so you can run the play clock down first. Off: the game snaps as soon as the kicker is set. Kickoffs always snap by themselves. |

Changes save right away. The game picks them up within a second, so the next kick uses them, even in the middle of a
game. You don't need to restart anything.

The settings live in `<Mod Manager>\Plugins\AutoKick\autokick.ini`. You can edit that file by hand too (`1` = on,
`0` = off); the app keeps your comments and anything else you add. Installing a newer version or clicking Repair
never overwrites it.

## Status

While the app is open it shows what Auto Kick is doing, refreshed every second:

- **Active**: Auto Kick is in the game and taking the kicks you switched on.
- **Standing aside**: another tool is already handling kicks in this game, so Auto Kick stays out of the way.
- **Failed**: Auto Kick couldn't hook the game, with the reason. This usually means a game update changed something.
  Your kicks stay normal. Look for an Auto Kick update.
- **Game not running** / **Waiting for Auto Kick**: start the game from the Mod Manager. Auto Kick loads about 30
  seconds after the game starts. A game started any other way runs without it.
- **Not loaded**: the game has been running for over a minute and Auto Kick never loaded into it. Restart the Mod
  Manager, then launch the game from it.

Under that you see how many kicks of each type the CPU took this session, how many were left to you, and the last kick.
With **Control the Snap** on, one more line says how many of those kicks you snapped yourself.

**Open log folder** opens `Plugins\AutoKick`. `plugin.log` (loading) and `autokick.log` (kicks) are in there if you
need to report a problem.

## Updating

Close the game and the Mod Manager, run the new AutoKick.exe and click **Repair**. Your settings are kept. Then start
the Mod Manager again and launch the game from it.

## Uninstall

Close the game and the Mod Manager, run AutoKick.exe and click **Uninstall**. It removes `AutoKickPlugin.dll` and the
`Plugins\AutoKick` folder. A copy of your `autokick.ini` is kept in `%APPDATA%\AutoKick\backups`.

To remove it by hand, delete `<Mod Manager>\Plugins\AutoKickPlugin.dll` and the `<Mod Manager>\Plugins\AutoKick`
folder.

## Troubleshooting

- **Status says "Not loaded"**: the Mod Manager was already open when you installed (it only loads plugins when it
  starts), or the game wasn't started from the Mod Manager. Restart the Mod Manager and launch the game from it.
- **Status stays on "Waiting for Auto Kick"**: the plugin saw the game but the DLL hasn't reported. Read `plugin.log`
  (Open log folder).
- **"access denied" in plugin.log**: the game runs as administrator. Run the Mod Manager as administrator too.
- **A kickoff stalls**: switch off Kickoffs; the next kickoff is normal again.
- **With Control the Snap on, a kick snapped by itself**: after 90 seconds without a press, Auto Kick lets the
  game snap it, so a kick never hangs.
