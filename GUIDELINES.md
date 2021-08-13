> ⚠️ We will try to keep it updated but as this is an under [early development feature](https://usebottles.com/blog/release-2021.7.28/#what-are-installers), can be outdated.

# Guide lines
This document show the guide lines with all methods for writing and propose new instalers in Bottles.

Each installer need a manifest in YAML format to be interpreted by Bootles.

## Example
These manifest can be used as examples:
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

## Grades
The following metrics should be used to define the compatibility grade of the installer.

### Valuation tests
As any software have different behaviors, we cannot define common tests, but we can provide questions for the maintainer to answer using a supported grade (broken, bronze, silver, gold, platinum):
- The program boots up?
- Is it showing alerts or other warnings?
- Does it show graphical glitches?
- Does it require some tweaking before installation? (Out of normal software configuration)
- Did it crash during tests execution?


