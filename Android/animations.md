## How to change android animation scales to less than .5

### Make your phone snappier!

- Download, extract and add to system path (optional), the [Android SDK Platform Tools](https://developer.android.com/tools/releases/platform-tools)
- Enable USB Debugging
- Connect your Android device to your PC via a USB cable
- ```
  adb shell
  ```
  - If the `platform-tools` folder is not in your system path, you will need to navigate to the folder where you extracted the SDK Platform Tools and run the command from there.
  - You will now get a prompt on your device, tap Allow.
- Execute the below commands

  - ```
      settings put global window_animation_scale 0.25
      settings put global transition_animation_scale 0.25
      settings put global animator_duration_scale 0.25
    ```
- To verify if the values have been set

  - ```
      settings get global window_animation_scale
      settings get global transition_animation_scale
      settings get global animator_duration_scale
    ```
- The custom values set won't be visible in the Developer Options
