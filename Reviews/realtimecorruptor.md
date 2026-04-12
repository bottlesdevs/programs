# Real-Time Corruptor
Review for the Real-Time Corruptor Launcher.

Maintainer: @blrbrb

**Is the program properly opened?**
Grade: Bronze
Additional notes: n/a

**Is it showing alerts or other warnings?**
Grade: Platinum
Additional notes: n/a

**Does it show graphical glitches?**
Grade: Silver
Additional notes: Some UI elements flicker, fonts and text are not rendered properly.

**Does it require some tweaking in order to work properly? (Out of normal software configuration)**
Grade: Silver
Additional notes: The installation will fail if wine mono is already installed. If the software fails to launch, re-create the bottle and choose "Custom". In the new bottle go to Legacy Wine Tools -> Control Panel and ensure that Wine Mono *isn't* installed. Then go to Dependencies and manually re-install dotnet40 dotnet48, and vcredist2019. See https://github.com/bottlesdevs/Bottles/issues/2887

**Did it crash during tests execution?**
Grade: Gold
Additional notes: n/a

**Is it usable?**
Grade: Silver
Additional notes: Running games will dip and stutter on occasion, but otherwise run fine. Controllers must be manually paired and configured within the emulator instance. Loading custom package files is untested. 

**Final grade? (the lower evaluation from previous questions)**
Grade: Bronze
Additional notes: n/a

**Additional notes**
Only tested with Dolphin Emulator. (Bizhawk, Citra, melonDS, FileStub, and ProcessStub need testing)
