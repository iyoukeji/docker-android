FROM iyoukeji/android:base

ENV ANDROID_SDK_PACKAGE build-tools-23.0.3,android-23

RUN echo y | android update sdk --no-ui --all --filter ${ANDROID_SDK_PACKAGE}
