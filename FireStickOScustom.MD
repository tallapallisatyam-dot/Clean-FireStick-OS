Prompt for Android/Google/Firestick model
I want to fully debloat and optimize my Android/Google/Firestick model using https://github.com/Gathin23/cleanyourtv.
My local IP address is: 192.x.x.x Please execute the following step-by-step:
1. **Connect & Identify:**
   - Connect to my TV via ADB 
   - Query the real hardware model, manufacturer, and Android version (`getprop ro.product.model`, `ro.product.manufacturer`, etc.).
   - Find the best matching community profile in `examples/` from the CleanYourTV repo.

2. **Backup & Safety First (DO NOT delete anything yet):**
   - Create a standalone `restore_tv.sh` script on my computer that can re-enable all packages and restore stock settings with one command if needed.
   - List the bloatware and telemetry you plan to disable and **ASK ME for confirmation** regarding personal apps I might want to keep (such as Netflix, Prime Video, USB media players, and OTA updates not required).
Install this Launcher manager 
adb install -r home-on-fire.apk
adb shell pm grant io.github.toolicious.homeonfire android.permission.WRITE_SECURE_SETTINGS
adb shell am start -n io.github.toolicious.homeonfire/.MainActivity

3. **Debloat & Speed Tweaks:**
   - Once confirmed, disable the agreed-upon bloatware, ad recommendation channels, and background telemetry using `pm disable-user --user 0` (do NOT uninstall).
   - Set UI window and transition animation scales to `1x` 
   - Restrict background execution for heavy idle apps like Netflix (`cmd appops set com.netflix.ninja RUN_IN_BACKGROUND ignore`).
Remove below apps
Amazon Kids
Amazon Live shopping
Fire TV Early Access
Music and More
install this Launcher manager 
adb install -r home-on-fire.apk
adb shell pm grant io.github.toolicious.homeonfire android.permission.WRITE_SECURE_SETTINGS
adb shell am start -n io.github.toolicious.homeonfire/.MainActivity

4. **Build & Install CleanYourTV Launcher:**
   - Use the installed OpenJDK 17 and Android SDK to compile the official CleanYourTV launcher (`com.gathin.tvhome`) from `launcher/`.
   - Install the compiled APK onto the TV via ADB.
   - Set `com.gathin.tvhome/.MainActivity` as the default Home activity and launch it.
   - Safely disable the stock ad-filled Google TV launcher (`com.google.android.tvlauncher` or `com.google.android.apps.tv.launcherx`).
   - Enable accessibility helpers (`InputKeyService` and `HomeKeyService`) so remote input and Home buttons work natively.

