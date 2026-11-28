# Evoto
Review for the Evoto installer.

Maintainers: @chaminaud

**Is the program properly opened?**  
Grade: Gold
Additional notes: Tested with Evoto 8.1.0-422 on soda-11.0-10 in a fresh win64 Application bottle with no extra dependencies. With the system Wine runner (wine 11.0) Evoto shows a "debugger detected" message and exits with code 222; on soda-11.0-10 it starts normally.

**Is it showing alerts or other warnings?**  
Grade: Silver
Additional notes: The in-app updater downloads the new installer to `C:\Program Files\.Evoto_pro Workspace\updateDownload\` and quits, but the installer does not start. Running the downloaded `Evoto_Setup_*.exe` manually (it also works silently with `/S`) updates the program.

**Does it show graphical glitches?**  
Grade: Silver
Additional notes: The UI font is Segoe UI. soda's `wine.inf` maps "Segoe UI" to "Times New Roman", so the interface is drawn in a serif font. This is cosmetic only and not bothersome in daily use. Installing a Segoe UI-compatible font that is really named "Segoe UI" (for example Microsoft's open-source Selawik renamed with fontTools) avoids the mapping.

**Does it require some tweaking in order to work properly? (Out of normal software configuration)**  
Grade: Silver
Additional notes: Only for the font issue above. Do not install the `wininet` dependency: native wininet crashes on an unimplemented `iertutil.dll.650` call. Because of the Flatpak sandbox, photo folders outside the bottle need access, e.g. `flatpak override --user --filesystem=xdg-pictures com.usebottles.bottles`.

**Did it crash during tests execution?**  
Grade: Gold
Additional notes: No crashes with the installer's settings.

**Is it usable?**  
Grade: Platinum
Additional notes: In daily use the application is fully functional. The font issue above does not get in the way.

**Final grade? (the lower evaluation from previous questions)**  
Grade: Silver
Additional notes: n/a

**Additional notes**  
The installer uses the full offline setup (~2.4 GB). The small web downloader (`EvotoInstaller_Setup_2.0.0-3_stable.exe`) crashes at startup in Wine's builtin winhttp (page fault) on both soda and system Wine. The download URL contains the version number and must be updated when Evoto removes it from its server.

This installer and review were prepared with the help of Claude (Anthropic's AI assistant).
