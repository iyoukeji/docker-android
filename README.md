# Docker Android

Android SDK in Docker, nice for CI builder use.

[![Build Status](https://travis-ci.org/iyoukeji/docker-android.svg?branch=master)](https://travis-ci.org/iyoukeji/docker-android) [![Image Layers](https://imagelayers.io/badge/iyoukeji/android:latest.svg)](https://imagelayers.io/?images=iyoukeji/android:latest 'Get your own badge on imagelayers.io')

## Supported tags and respective `Dockerfile` links

* [`base`, `latest` (android-base/Dockerfile)](https://github.com/iyoukeji/docker-android/blob/master/android-base/Dockerfile)
* [`r23` (android-r23/Dockerfile)](https://github.com/iyoukeji/docker-android/blob/master/android-r23/Dockerfile)
* [`react-native` (android-react-native)](https://github.com/iyoukeji/docker-android/blob/master/android-react-native/Dockerfile)

## Usage

Working with bash in interactive mode.

```shell
docker run -it --rm -v /path/to/your/project:/home/workspace bash
```

Run Gradle build

```shell
docker run --rm -v /path/to/your/project:/home/workspace sh -c 'cd /home/workspace && gradle package'
```

## Version information

* Gradle 2.14 (Environment variable is `GRADLE_VERSION`)
* Android SDK r24.4.1 (Environment variable is `ANDROID_SDK_VERSION`)
* `r23` contains `android-23`, `build-tools-23.0.1`, `build-tools-23.0.2`, `build-tools-23.0.3`, `extra-android-m2repository`, `extra-google-m2repository` (Environment variable is `ANDROID_SDK_PACKAGE`)
* `react-native` contains `nodejs6`

## Customize your Android SDK packages

Create your own `Dockerfile`, build from `iyoukeji/android:base` or `iyoukeji/android:base`, and add SDK packages:

```
FROM iyoukeji/android:base
ENV ANDROID_SDK_PACKAGE android-19, \
                        extra-android-m2repository, \
                        extra-google-m2repository

RUN echo y | android update sdk --no-ui --all --filter "${ANDROID_SDK_PACKAGE}"
```

## Issues

If you have any problems with or questions about this image, please contact us through a [GitHub issue](https://github.com/iyoukeji/docker-android/issues).
