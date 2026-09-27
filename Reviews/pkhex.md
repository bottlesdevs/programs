# PKHeX
Review for the PKHeX installer.

Maintainer: @Azevedo

**Is the program properly opened?**  
Grade: Gold
Additional notes: Opens successfully with .NET Desktop Runtime 10 installed.

**Is it showing alerts or other warnings?**  
Grade: Gold  
Additional notes: No alerts or warnings after applying the DPI workaround.

**Does it show graphical glitches?**  
Grade: Silver  
Additional notes: The window is not resizable and renders small (though usable). Pokemon tooltip popups are inconsistent — sometimes showing, sometimes not, sometimes disappearing too quickly.

**Does it require some tweaking in order to work properly? (Out of normal software configuration)**  
Grade: Silver  
Additional notes: Requires a Windows AppCompatFlags registry key (`DPIUNAWARE`) to prevent a .NET WinForms DPI awareness crash when opening file dialogs. This is applied automatically by the installer. A Wine runner with .NET DPI fixes (e.g. Wine 11+) is recommended over older runners like soda-9.0.

**Did it crash during tests execution?**  
Grade: Gold  
Additional notes: No crashes after the DPI workaround is applied. Without it, the app crashes on any file dialog (open/save) with `Failed to get thread's DpiAwareness context`.

**Is it usable?**  
Grade: Silver
Additional notes: Core functionality works — opening, editing, and saving Pokemon save files all function correctly. The UI quirks (non-resizable window, inconsistent tooltips) are cosmetic and do not block usage.

**Final grade? (the lower evaluation from previous questions)**  
Grade: Silver
Additional notes: Fully functional for its primary purpose. The DPI workaround is automated in the installer. Remaining issues are cosmetic (window size, tooltip rendering).

**Additional notes**  
- PKHeX binaries are available from https://projectpokemon.org/home/files/file/1-pkhex/
- The installer uses `url: local` since there is no stable direct download link.
- PKHeX requires .NET Desktop Runtime 10. The installer downloads it from Microsoft's CDN.
- Wine 11+ is recommended as the runner. Older runners (e.g. soda-9.0) may have additional issues.
- **DPI workaround**: Wine does not implement `SetThreadDpiAwarenessContext`, which .NET 10 WinForms calls when opening file dialogs. The installer sets the `DPIUNAWARE` AppCompatFlags registry key to prevent this crash.
