# Star Citizen
Review for the Star Citizen game and its launcher.

Maintainer: @evoxcx

**Is the program properly opened?**  
Grade: Gold
Additional notes: n/a

**Is it showing alerts or other warnings?**  
Grade: Gold
Additional notes: The launcher will always complain that you are using an "unsupported version of Windows", but you should just dismiss the warning since the game still runs perfectly.

**Does it show graphical glitches?**  
Grade: Gold
Additional notes:
- The game runs well, but the Electron-based launcher will sometimes have graphical glitches. It's recommended to go into the launcher settings and disabling "background video", "non-essential animations" and "transition effects" to greatly increase the launcher's performance and stability.
- It's also recommended to go into the launcher settings and enabling "close-to-quit", to prevent the launcher from staying permanently in the background after you've exited the game, since that increases the risk of having issues the next time you try to open the launcher.
- Sometimes, the launcher will not show up at all, or may get stuck in an endless glitching loop with a flickering black screen (especially on Wayland). There is no way to permanently fix it, but the simplest solution when it happens is to use the "Force Stop all Processes" action for your bottle, to terminate the broken launcher process. Then try launching it again.

**Does it require some tweaking in order to work properly? (Out of normal software configuration)**  
Grade: Gold
Additional notes:
- The game **requires** that `sysctl vm.max_map_count` returns a value of `1048576` (or higher) to avoid crashes, since the game uses huge amounts of memory-mapped file handles. Some modern distros already use the correct value by default. You can temporarily write the correct value with `sudo sysctl -w vm.max_map_count=1048576`, or you can make it permanent with `echo "vm.max_map_count=1048576" | sudo tee /etc/sysctl.d/90-vm_max_map_count.conf` and then rebooting.
- Wayland users **must** manually apply the `pl_pit.forceSoftwareCursor = 1` [mouse cursor fix](https://github.com/starcitizen-lug/knowledge-base/wiki/Troubleshooting#mousecursor-warp-issues-and-view-snapping-in-interaction-mode), otherwise the mouse cursor will warp around randomly and will completely fail to interact with the game.
- You should **always** manually close (or minimize) the game launcher after you start the game, because the launcher tends to grab keyboard/mouse input even when it's in the background, which can make it impossible to interact with the game.

**Did it crash during tests execution?**  
Grade: Gold
Additional notes:
- Use the default DX11 graphics API. Don't enable Vulkan in the game, since it's known for causing lots of crashes on Linux (you may not even be able to launch the game at all after enabling Vulkan mode).
- If you've enabled Vulkan and your game is now crashing on launch, then you must manually go to `drive_c/users/<your name>/AppData/Local/star citizen` inside your bottle, and then find the `GraphicsSettings.json` file for your version of the game, and finally either delete the file itself or remove the bad `GraphicsRenderer` value within it.

**Is it usable?**
Grade: Gold
Additional notes:
- EasyAntiCheat (EAC) is **required** to log into the game since July, 2025. You **must** therefore use a [compatible Runner](https://github.com/starcitizen-lug/knowledge-base/wiki/Tips-and-Tricks#recommended-runners) which contains special patches for Star Citizen's EAC. In Bottles, that's the "Kron4ek 10.3+ Staging TKG" runner (`kron4ek-wine-10.3-staging-tkg-amd64`) (or newer versions of it).
- You can [read the latest news about anticheat in Star Citizen](https://github.com/starcitizen-lug/knowledge-base/wiki/Tips-and-Tricks#easy-anti-cheat) if the Linux compatibility changes in the future.

**Final grade? (the lower evaluation from previous questions)**  
Grade: Gold
Additional notes: The game itself runs perfectly after performing the tweaks and workarounds described in this document. The launcher can be a hassle sometimes, but following the advice in this document will improve your experience.

**Additional notes**  
n/a
