# Windnows Update
- ## [Windows keeps crashing when installing an update](#crash1)
<br><br><br><br>
## <a name="crash1"></a>**Windows keeps crashing when installing an update**
Corrupted or damaged system files often cause several errors on PC including system crashing and freezing issues. The possible solution: Run SFC and DISM scan.
- Open **cmd** as Admin.
- Run:
```cmd
sfc /scannow
```
- After this command, all the corrupted files will get repaired and restored.
- Run:
```cmd
dism /online /cleanup-image /restorehealth
```
- This command will repair the Windows image. So, wait until the scanning process completes to 100%.
- After completing the process, restart your computer, and then try to upgrade again.