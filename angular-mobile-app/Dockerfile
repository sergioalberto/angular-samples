FROM beevelop/cordova:v7.0.0

MAINTAINER Sergio GQ <webetechnology@gmail.com>

WORKDIR /opt

RUN apt-get update
RUN apt-get install -y git

# Install OpenJDK-8
RUN apt-get update && \
    apt-get install -y openjdk-8-jdk && \
    apt-get install -y ant && \
    apt-get clean;

# Fix certificate issues
RUN apt-get update && \
    apt-get install ca-certificates-java && \
    apt-get clean && \
    update-ca-certificates -f;

# Setup JAVA_HOME -- useful for docker commandline
ENV JAVA_HOME /usr/lib/jvm/java-8-openjdk-amd64/
RUN export JAVA_HOME

RUN wget -q https://services.gradle.org/distributions/gradle-5.1-all.zip
RUN chmod 775 /opt/gradle-5.1-all.zip
RUN mkdir -p /opt/gradle-5.1/wrapper/dists/
RUN unzip gradle-5.1-all.zip -d /opt/gradle-5.1/wrapper/dists/
RUN mv /opt/gradle-5.1/wrapper/dists/gradle-5.1/bin/gradle /opt/gradle-5.1/wrapper/dists/gradle-5.1/bin/gradle4
RUN chmod 775 /opt/gradle-5.1/wrapper/dists/gradle-5.1/bin/gradle4
RUN wget -q https://repo1.maven.org/maven2/com/google/j2objc/j2objc-annotations/1.1/j2objc-annotations-1.1.jar \
    && unzip j2objc-annotations-1.1.jar -d /opt
ENV GRADLE_HOME /opt/gradle-5.1
ENV GRADLE_USER_HOME /opt/gradle-5.1
ENV PATH $PATH:/usr/bin
ENV ANDROID_HOME=/opt/android
#ENV JAVA_HOME=/usr/lib/jvm/java-8-oracle

WORKDIR /opt/android/tools/bin

RUN ./sdkmanager --update
RUN mkdir "$ANDROID_HOME/licenses"
RUN echo "d56f5187479451eabf01fb78af6dfcb131a6481e" > "$ANDROID_HOME/licenses/android-sdk-license"
RUN echo "8933bad161af4178b1185d1a37fbf41ea5269c55" >> "$ANDROID_HOME/licenses/android-sdk-license"
RUN echo "84831b9409646a918e30573bab4c9c91346d8abd" > "$ANDROID_HOME/licenses/android-sdk-preview-license"
RUN npm install -g @angular/cli

WORKDIR /workspace

ENV PATH $PATH:/opt/android/tools/bin
ENV PATH $PATH:/opt/gradle-5.1/wrapper/dists/gradle-5.1/bin/
