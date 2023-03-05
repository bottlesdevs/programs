# Star Citizen Launcher
Review for the star citizen installer.

Maintainer: @evoxcx

**Is the program properly opened?**  
Grade: Platinum
Additional notes: n/a

**Is it showing alerts or other warnings?**  
Grade: Platinum  
Additional notes: n/a

**Does it show graphical glitches?**  
Grade: Platinum  
Additional notes: n/a

**Does it require some tweaking in order to work properly? (Out of normal software configuration)**  
Grade: Platinum  
Additional notes: n/a

**Did it crash during tests execution?**  
Grade: Platinum
Additional notes: n/a

**Is it usable?**  
Grade: Bronze  
Additional notes: EAC not working for the [moment](https://robertsspaceindustries.com/spectrum/community/SC/forum/190048/thread/star-citizen-alpha-3-15-1e-ptu-7876811-patch-notes) | [WorkAround](https://github.com/starcitizen-lug/lugWarning) (Warning a ban can be issued)

**Final grade? (the lower evaluation from previous questions)**  
Grade: Bronze  
Additional notes: n/a

**Additional notes**  
SamPurple22@github

After installing "RSI Installer", inside the prefix, the following folders need to be created manually, because the RSI Launcher fails to create them:
"C:\Program Files\Roberts Space Industries\StarCitizen"
"C:\Program Files\Roberts Space Industries\StarCitizen\LIVE"
"C:\Program Files\Roberts Space Industries\StarCitizen\PTU"

#inside /etc/hosts file, the following line needs to be added - WARNING - it will disable EAC for other games on the system, ex: The Division 2 via Ubisoft Connect.

# /etc/hosts

127.0.0.1 modules-cdn.eac-prod.on.epicgames.com #Star Citizen EAC workaround

