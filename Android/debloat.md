# debloat your Android [without root access]

### 1. Enabling USB Debugging on your phone

- Enable **Developer Options**

  - Settings --> About phone --> Build Number (Tap 7 times)
- System --> Developer Options --> Enable USB Debugging

---

### 2. Install ADB

- [download](https://developer.android.com/tools/releases/platform-tools) and install Adroid SDK Platform Tools
- open cmd/powershell in this folder (or optionally add to system path)
- type `adb devices` to list attached devices
- GRANT permission on your phone!

---

### 3. debloat

- ```
  adb shell
  ```
- Find the name of the packages to uninstall

  - ```
    pm list packages | grep '<OEM/Carrier/App Name>'
    ```
  - Alternately, use **App Inspector** from Google Play Store to know the package names of all the installed apps on your phone
- Command to uninstall a system app

  - ```
    pm uninstall -k --user 0 NameOfPackage
    ```

---

### 4. re-install an uninstalled app

If you've deleted an app by mistake or a secondary app is force closing because it's dependent on an app you uninstalled, you can re-install the app using the following set of commands

- ```
  pm install-existing NameOfPackage
  ```

---

### NOTES
- Apps aren't fully (or rather truely) uninstalled
- They are just being uninstalled for the current user (user 0 is the default/main user of the phone)
- `--user 0` - the system app will only be uninstalled for the current user (and not all users, which is something that requires root access)
- `-k` - keep cache/data directories of the system application preserved (which can’t be removed without root)
- Therefore, even if you uninstall a system app using this method, you can still receive official OTA updates from your carrier or OEM