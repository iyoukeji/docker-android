# Docker Android

Android SDK in Docker, nice for CI builder use.

[![Build Status](https://travis-ci.org/iyoukeji/docker-android.svg?branch=master)](https://travis-ci.org/iyoukeji/docker-android) [![Image Layers](https://imagelayers.io/badge/iyoukeji/android:latest.svg)](https://imagelayers.io/?images=iyoukeji/android:latest 'Get your own badge on imagelayers.io')

# Supported tags and respective `Dockerfile` links

* [`base`, `latest` (android-base/Dockerfile)](https://github.com/iyoukeji/docker-android/blob/master/android-base/Dockerfile)
* [`r23` (android-r23/Dockerfile)](https://github.com/iyoukeji/docker-android/blob/master/android-r23/Dockerfile)
* [`react-native` (android-react-native)](https://github.com/iyoukeji/docker-android/blob/master/android-react-native/Dockerfile)

# Usage

Working with bash in interactive mode.

```shell
docker run -it --rm -v /path/to/your/project:/home/workspace bash
```

Run Gradle build

```shell
docker run --rm -v /path/to/your/project:/home/workspace sh -c 'cd /home/workspace && gradle package'
```

# Version Information

* Gradle 2.14 (Environment variable is `GRADLE_VERSION`)
* Android SDK r24.4.1 (Environment variable is `ANDROID_SDK_VERSION`)
* `r23` contains `build-tools-23.0.3`, `android-23` (Environment variable is `ANDROID_SDK_PACKAGE`)
* `react-native` contains `nodejs-6.3`

# Issues

If you have any problems with or questions about this image, please contact us through a [GitHub issue](https://github.com/iyoukeji/docker-android/issues).


