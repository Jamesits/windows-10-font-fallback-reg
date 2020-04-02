# Windows 10 font fallback config

## Submit default config  
Export your `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\FontLink\SystemLink`

## Principle to patch en_us to looks like your language
**BACKUP EVERYTHING OR USE VIRTUAL MACHINE TO PRACTICE BEFORE APPLY ON REAL PC**  
**BACKUP EVERYTHING OR USE VIRTUAL MACHINE TO PRACTICE BEFORE APPLY ON REAL PC**  
**BACKUP EVERYTHING OR USE VIRTUAL MACHINE TO PRACTICE BEFORE APPLY ON REAL PC**

Run two Windows system, one in the virtual machine as en_us, one is your language  
Diff between en_us.reg and your language.reg, find all difference  
Open Regedit and browse to `FontLink\SystemLink` on both systems

If a new section appears in en_us.reg,  
copy it to a new reg file encoding as `Unicode` in Windows notepad  
Remove this section from en_us.reg  
Add & remove other new section until all copied to a new reg file

If a section is modified or removed by en_us.reg, ignore it

Import this new reg file to your language system  
Use Regedit browse to `FontLink\SystemLink`,  
open each imported config item from new reg file,  
it will look like this:

![image](https://user-images.githubusercontent.com/10773245/78219225-b02e8300-74f1-11ea-8dca-b5ce31ebc3a9.png)

Cut & Paste your language-related font config lines to the very beginning of all,  
but if they are starts with an English font, below it  
Do this until all the new section are modified

Optional: Create your own `FontSubstitutes.reg` to fix the QT software problem,  
it's very simple, so ignore the principle here

Reboot and check the results  
If all cleared, export `SystemLink.reg` and your own `FontSubstitues.reg`  

**Make sure `SystemLink.reg` only contains the new entry comes from en_us.reg**  
**Make sure `FontSubstitues.reg` only contains what entry you have changed**  
Create a pull request to submit your results of the work.
