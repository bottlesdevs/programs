# Blizzard Battle.net
Review for the Battle.net installer.

Maintainer: @mirkobrombin @Arcitec

**Is the program properly opened?**  
Grade: Gold  
Additional notes: Starting Battle.net is slow on Linux. The first login can be extremely slow. Be patient and wait even when it looks like it may be frozen. There are no known fixes.

**Is it showing alerts or other warnings?**  
Grade: Platinum  
Additional notes: n/a

**Does it show graphical glitches?**  
Grade: Gold  
Additional notes:
If you `Alt-Tab` away from the launcher while a popup/settings menu is open, it may be invisible when you return. Pressing the `Escape` key closes the invisible window without any further issues.

**Does it require some tweaking in order to work properly? (Out of normal software configuration)**  
Grade: Gold  
Additional notes:
After the installation, Battle.net will launch automatically - but without our compatibility tweaks. Depending on what Runner you are using, you might see a blank/white window. If so, just close Battle.net and then launch it again via the Bottles "Programs" shortcut that our installer has created for you.

When you are in the Battle.net client, you should then go into "Battle.net's menu: Settings: App", and set "When clicking X (close window)" to "Exit Battle.net completely". Also disable "Launch Battle.net when I start my computer".

These two settings are tied to the launcher's per-account config files, which have unique filenames for everyone, so our automated installer cannot do this for you.

Changing these settings ensures that Battle.net won't stay lingering invisibly in the background, which is unreliable on Linux (due to varying notification tray support, lack of robust Windows on-screen notification layering, and general slowness of keeping applications running in the background).

**Did it crash during tests execution?**  
Grade: Platinum  
Additional notes: n/a

**Is it usable?**  
Grade: Platinum  
Additional notes: n/a

**Final grade? (the lower evaluation from previous questions)**  
Grade: Gold  
Additional notes: n/a

**Additional notes**  
Battle.net runs very well on Linux, apart from the slow startup/login process. The Bottles installer optimizes its settings for compatibility and performance, and you shouldn't need to do anything else.

There's a lot of outdated and incorrect advice online about running Battle.net on Linux. Be careful with applying any other tweaks (especially from other installer scripts you might find online). Especially avoid any notes you might see about editing `/etc/hosts` to "help with the startup delay"; it does not work and has nothing to do with the issue.

Read our Battle.net installation manifest for details about most of the older tweaks and why they aren't necessary, and can even be harmful.

The slow startup/login is most likely caused by the Microsoft Edge WebView2 component, which is notoriously slow and buggy on Linux, and is used by Battle.net for its login/loading UI.

Tip: If the Battle.net interface is too small on your screen, you need to set the DPI of your bottle. Use "Settings: Display: Advanced Display Settings: Screen Scaling" to change the scale. Valid Windows DPI range: 96-400. It's recommended that you use increments of +24 (i.e. 96, 120, 144, ...), to match official Windows scaling choices. You may need to restart the bottle to apply the changes.

Lastly, if an update for Battle.net or a change of your active Runner somehow breaks the launcher, then you can simply run our Battle.net installer again. This will repair your launcher and registry in-place without losing any data. All your games and the bottle will stay intact.
