FROM iyoukeji/android:base

ENV ANDROID_SDK_PACKAGE android-23, \
                        build-tools-23.0.1, \
                        build-tools-23.0.2, \
                        build-tools-23.0.3, \
                        extra-android-m2repository, \
                        extra-google-m2repository

RUN echo y | android update sdk --no-ui --all --filter "${ANDROID_SDK_PACKAGE}"
