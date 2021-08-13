> ⚠️ We will try to keep it updated but as this is an under [early development feature](https://usebottles.com/blog/release-2021.7.28/#what-are-installers), can be outdated.

# Guide lines
This document show the guide lines with all methods for writing and propose new installers in Bottles.

Each installer need a manifest in YAML format to be interpreted by Bottles.

## Example
These manifests can be used as example:
- https://github.com/bottlesdevs/programs/blob/main/Games/epicgamestore.yml
- https://github.com/bottlesdevs/programs/blob/main/Games/steam.yml
- https://github.com/bottlesdevs/programs/blob/main/Games/uplay.yml

## Structure
Each manifest has 5 sections:
- header
- dependencies
- executable
- steps

### Header
```yaml
Name: epicgamestore
Description: The official Epic Games launcher.
Grade: Gold
```

where:
- **Name** is the lowercased, special characters and white spaces free name of the software (generally the file name without the extension)
- **Description** this is a short description fo the software
- **Grade** Broken|Bronze|Silver|Gold|Platinum this is NOT the grade declared in ProtonDB or WineHQ. Read the Grades section.

### Dependencies
This is a list of dependencies required by the software and that should be installed by the installer.

```yaml
Dependencies:
- d3dx9
- msls31
- riched20
- allfonts
- d3dcompiler_43
- d3dcompiler_47
```

### Executable
These parameters are used by Bottles for multiple scopes:
- create the desktop entry
- register the program in the bottle

```yaml
Executable:
  name: Epic Games Store
  icon: epicgamestore.svg
  file: EpicGamesLauncher.exe
  path: Program Files (x86)/Epic Games/Launcher/Portal/Binaries/Win32
  arguments: -opengl -SkipBuildPatchPrereq
```

where:
- **name** is the full name of the program (special charactes and white spaces allowed)
- **icon** the name from the data directory. Read the Data section.
- **file** the name of the executable to start the program
- **path** path (inside the `bottle/drive_c` directory) to the executable (without the executable itself)
- **arguments** optional arguments to pass to the executable on start

## Grades
The following metrics should be used to define the compatibility grade of the installer.

### Valuation tests
Since any software has different behaviors, we cannot define common tests, but we can provide questions for the maintainer to answer using a supported grade (Broken, Bronze, Silver, Gold, Platinum):
- Is the program properly opened?
- Is it showing alerts or other warnings?
- Does it show graphical glitches?
- Does it require some tweaking in order to work properly? (Out of normal software configuration)
- Did it crash during tests execution?
- Is it usable?


