# Installation Guide

0) Install adb and fastboot from https://wiki.lineageos.org/adb_fastboot_guide.html

1) Find the appropriate LineageOS installation guide @ https://wiki.lineageos.org/install_guides.html

2) Before exiting recovery mode (the last step on the guide, when you type `adb reboot`), download the appropriate gapps.zip from https://wiki.lineageos.org/gapps.html and load it by typing the command `adb sideload filename.zip`, replacing `filename.zip` with the name of the gapp.zip file

3) After running `adb reboot`, use the following commands while the device is plugged in to complete setup:

OS X
```
if adb get-state 1>/dev/null 2>&1
then
  echo "Host found"
  echo "Downloading boot animation..."
  curl -O https://raw.githubusercontent.com/WeIgniteChange/os/master/bootanimation.zip
  echo "Flashing zip"
  adb push bootanimation.zip /data/local
  echo "Rebooting..."
  adb reboot
  echo "Setup complete!"
else
  echo "Host not found, make sure an android device is plugged in!"
fi
```
