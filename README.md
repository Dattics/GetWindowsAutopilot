# Get Windows Autopilot Info
Script on CMD to get Windows Autopilot info on a CSV file for configured devices. It also works on OOBE.
It appends new computers' info in the same file, thus, you can do this on several PCs and import it only once.

First time (this is done only once):
1. Plug a USB drive on a Windows PC
2. Paste the three files
  a. 1.cmd
  b. 2.cmd
  c. Get-WindowsAutoPilotInfo.ps1
 
On every Windows 10 PC you want to get the Autopilot info:
1. Plug the USB drive
2. Open the drive folder (usually D:\)
3. Open an elevated CMD session (as administrator)
4. Check if Windows Remote Management is working by typing:
    winrm quickconfig
    a. If prompted, type "y" (without quotation marks) to config Windows RM.
5. Change directory to the USB drive (usally D:\)
    a. On CMD, type "> cd /D D:\" (without quotation marks)
    b. The second "D" on the command must be changed according to correct letter assigned to your USB drive
6. Right click on "1.cmd" and click on "Run as administrator"
7. If it's the first computer, a new file named "computers.csv" will be created with the info requiered to be uploaded
    a. If it is not the first computer, new info will be appended to the old one

On every new computer (unconfigured Windows 10):
During Out of Box Experience (OOBE) - The screen where you choose the country as soon as the PC starts (explaination for non-experienced users):
1. Press CTRL+F10
    a. A new CMD window will open
2. Check if Windows Remote Management is working by typing:
    winrm quickconfig
    a. If prompted, type "y" (without quotation marks) to config Windows RM.
3. Change directory to the USB drive (usally D:\)
    a. On CMD, type "> cd /D D:\" (without quotation marks)
    b. The second "D" on the command must be changed according to correct letter assigned to your USB drive
4. Right click on "1.cmd" and click on "Run as administrator"
5. If it's the first computer, a new file named "computers.csv" will be created with the info requiered to be uploaded
    a. If it is not the first computer, new info will be appended to the old one
    b. You can check if the file was created by typing "dir"
6. Remove the USB drive and repeat on other PCs as needed.
