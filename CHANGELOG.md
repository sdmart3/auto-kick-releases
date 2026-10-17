# Changelog

## 0.2.2

- Fixed: kickoffs the CPU takes for you no longer shank out of bounds. Because the kick was for your team, the game used the miss formula meant for a human using the kick meter, which has a hard shank built in. Your CPU kickoffs now use the same formula as the CPU's own kickoffs, and the final aim is also kept inside the field as a backstop.

## 0.2.1

- **Kick like a CPU team** (under Kickoffs): the kickoffs the CPU takes for you use the CPU's kicking sliders instead of yours, so your difficulty and slider settings don't make them less accurate. Field goals, extra points and punts still use yours. Off by default.
- **Aim kickoffs at the play's side** is less extreme: Kickoff Left / Right now aim about as wide as the game's own CPU kickoffs, never wider.
- Fixed: on rare launches Auto Kick couldn't load (no free memory close enough to the game) and that game ran without it. It now falls back to a spot inside the game's own code.

## 0.2.0

- **Control the Snap**: on the field goals, extra points and punts the CPU takes, the ball waits for your snap button, so you can run the play clock down first. Off by default.
- **Aim kickoffs at the play's side**: when the CPU kicks off for you, Kickoff Left / Middle / Right go to the side you called. Safety kicks follow Punt Left / Middle / Right. Squib and onside keep their own aim. Off by default; needs Kickoffs on.
- Works on the current game update.

## 0.1.0

First release.

- The CPU kicks for you on the kick types you pick: field goals and extra points, punts, kickoffs.
- Settings app (AutoKick.exe): install, repair and uninstall into the Mod Manager; one switch per kick type; changes apply on the next kick, even mid-game; live status.
- Loads through a Mod Manager plugin. No .fbmod, no game files changed.
