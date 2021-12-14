## Install Flutter in "D:\flutter" folder:
1. ### dd "D:\flutter\bin" to the PATH environment variable.
2. ### Add "JAVA_HOME" with value "C:\Program Files\Android\jdk\microsoft_dist_openjdk_1.8.0.25\" as an environment variable.
3. ### Locate Android SDK (Open Android Studio, go to File - Settings - Appearence and Behavior - System Settings - Android SDK and there you can find it)
4. ### Go to the location of Android Studio, and change to "tools\bin"
5. ### Run command sdkmanager.bat --install "cmdline-tools;latest"
6. ### Go to "D:\flutter\bin" and run "flutter doctor"
7. ### Run "flutter doctor --android-licenses"
8. ### Run "flutter config --enable-windows-desktop"
9. ### Install the Flutter and Dart plugins in Android Studio.
    - #### Open plugin preferences (File > Settings > Plugins).
    - #### Select Marketplace, select the Flutter plugin and click Install.