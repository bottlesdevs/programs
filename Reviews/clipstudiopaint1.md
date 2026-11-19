# CLIP STUDIO PAINT 1.x
Review for the CLIP STUDIO PAINT 1.x installer.

Maintainers: @miranyx

**Is the program properly opened?**  
Grade: Platinum
Additional notes: Tested with CLIP STUDIO PAINT 1.13.2 on soda-11.0-35-experimental and soda-11.0-36-experimental. The installer sets the Windows version to Windows 8.1 and disables the Wayland driver; with Windows 10 the program crashes after the welcome slideshow (unsupported `Windows.UI.Input.RadialController` in `triglavwinrt.dll`) and with the Wayland driver it is terminated by a Wayland protocol error. The Windows 8.1 setting is written to `HKCU\Software\Wine`, so the Windows version shown in the Bottles settings has no effect for this bottle.

**Is it showing alerts or other warnings?**  
Grade: Gold
Additional notes: On first start CLIP STUDIO asks for a license, login or sign-up, as on Windows. Logging in works and is remembered. The built-in news panel shows "OFFLINE – Not connected to the Internet" although login and the online license check work; probably an outdated info service for version 1.x.

**Does it show graphical glitches?**  
Grade: Silver
Additional notes: In the "Getting Started" login dialog, two button labels show their line break as `□□` and the text runs into one line. The "next" arrow of the welcome slideshow does nothing (closing it works). Under XWayland a few empty 1×1 helper windows appear in the desktop's window overview while the program runs; they disappear when it is closed. All of these are cosmetic.

**Does it require some tweaking in order to work properly? (Out of normal software configuration)**  
Grade: Gold
Additional notes: No tweaks needed after installation. Because of the Flatpak sandbox, files are saved to the bottle's own Documents folder by default; to save to your normal folders, allow access, e.g. `flatpak override --user --filesystem=xdg-pictures com.usebottles.bottles`.

**Did it crash during tests execution?**  
Grade: Platinum
Additional notes: No crashes with the installer's settings.

**Is it usable?**  
Grade: Gold
Additional notes: Drawing, new layers, undo/redo, saving and reopening `.clip` files and exporting to PNG work. Pen pressure with a graphics tablet was not tested.

**Final grade? (the lower evaluation from previous questions)**  
Grade: Silver
Additional notes: n/a

**Additional notes**  
Version 1.13.2 is used on purpose; it needs a CLIP STUDIO account or a 1.x license/serial number.
