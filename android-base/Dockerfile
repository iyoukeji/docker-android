FROM java:8-jdk

ENV GRADLE_VERSION 2.14
ENV GRADLE_HOME /usr/lib/gradle
ENV ANDROID_SDK_VERSION r24.4.1
ENV ANDROID_HOME /usr/lib/android-sdk-linux

RUN apt-get update \
    && apt-get install -y lib32stdc++6 lib32z1 lib32ncurses5 \
    && rm -rf /var/lib/apt/lists/* \
    && mkdir -p /tmp/gradle && cd /tmp/gradle \
    && curl -sSLO https://services.gradle.org/distributions/gradle-${GRADLE_VERSION}-bin.zip \
    && unzip gradle-${GRADLE_VERSION}-bin.zip \
    && mv gradle-${GRADLE_VERSION} ${GRADLE_HOME} \
    && rm -rf /tmp/gradle \
    && cd ${GRADLE_HOME} \
    && ln -s ${GRADLE_HOME}/bin/gradle /usr/bin/gradle

RUN cd /tmp/ \
    && curl -sSLO https://dl.google.com/android/android-sdk_${ANDROID_SDK_VERSION}-linux.tgz \
    && tar xf android-sdk_${ANDROID_SDK_VERSION}-linux.tgz \
    && mv /tmp/android-sdk-linux /usr/lib/ \
    && cd ${ANDROID_HOME} \
    && ln -s ${ANDROID_HOME}/tools/android /usr/bin/android

CMD [ "bash" ]
