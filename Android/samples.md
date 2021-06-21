# 1. Auto-incrementing version number
For various reasons (for example publishing an update to an app on Google Play Store will require it to have a newer versions), you should increment the version/build number for your project.

This can be easily done in your **build.gradle** file.

First you define a file to hold the versionCode (**version.properties** below). You read the code from it (if the file does not exist, set the code to 0), then you increment it, and save it back to the file to be used on the next build.
```gradle

android {
...
    def versionFile = file('version.properties')
    Properties prop = new Properties()
    if (versionFile.canRead()) {
        prop.load(new FileInputStream(versionFile))
    }
    else {
        prop['VERSION_CODE']='0'
    }
    def code = prop['VERSION_CODE'].toInteger() + 1
    prop['VERSION_CODE']=code.toString()
    prop.store(versionFile.newWriter(), null)

    defaultConfig {
        ...
        versionCode code
        versionName "1.0"
    }
...
}
```
Finally set the **versionCode** to the code you previously computed.

The full version of your application should now be: **BuildConfig.VERSION_NAME + “.” + BuildConfig.VERSION_CODE**.

A full implementation can be found [here](https://github.com/florinmuscalu/AndroidSamples), and the code for the current article in in **build.config**.