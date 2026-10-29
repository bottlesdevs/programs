# Cadence OrCAD X
Review for the Cadence OrCAD X installer (OrCADXInstall.exe 25.10.050, OrCAD X 25.1).

Maintainers: @<your-github-user>

**Is the program properly opened?**  
Grade: TBD  
Additional notes: Capture opens projects and runs PSpice simulations (transient, AC sweep). PCB Editor not checked yet.

**Is it showing alerts or other warnings?**  
Grade: TBD  
Additional notes: n/a

**Does it show graphical glitches?**  
Grade: TBD  
Additional notes: With the font and icon steps of this installer, the interface font and icons of Capture look like on Windows.

**Does it require some tweaking in order to work properly? (Out of normal software configuration)**  
Grade: TBD  
Additional notes: Requires a Cadence account; the installer downloads about 50 GB. The registry workarounds for fonts, icons and PSpice are part of the installer steps.

**Did it crash during tests execution?**  
Grade: TBD  
Additional notes: n/a

**Is it usable?**  
Grade: TBD  
Additional notes: Licensing by signing in with a Cadence account works.

**Final grade? (the lower evaluation from previous questions)**  
Grade: TBD  
Additional notes: n/a

**Additional notes**  
Bring your own OrCADXInstall.exe from Cadence (Bottles asks for the file) and sign in with a Cadence account in the installer window. Tested with Bottles 67.3 (Flatpak) and the soda-11.0-10 runner. Changing the runner resets the font mapping of the Soda wine.inf; tools/font-icon-fix.sh of https://github.com/<your-github-user>/Cadence-Bottles applies it again.
