FROM openjdk:14-alpine
LABEL Author="Deivid Teixeira"
WORKDIR /jmeter
ARG JMETER_VERSION=5.2.1
RUN wget "https://downloads.apache.org//jmeter/binaries/apache-jmeter-${JMETER_VERSION}.tgz" && \
    tar -xvzf apache-jmeter-${JMETER_VERSION}.tgz && \
    wget "https://repo1.maven.org/maven2/kg/apc/cmdrunner/2.2/cmdrunner-2.2.jar" -O apache-jmeter-5.2.1/lib/cmdrunner-2.2.jar && \
    wget "https://repo1.maven.org/maven2/kg/apc/jmeter-plugins-manager/1.4/jmeter-plugins-manager-1.4.jar" -O apache-jmeter-5.2.1/lib/ext/jmeter-plugins-manager-1.4.jar && \
    java -cp apache-jmeter-5.2.1/lib/ext/jmeter-plugins-manager-1.4.jar org.jmeterplugins.repository.PluginManagerCMDInstaller && \
    apache-jmeter-5.2.1/bin/PluginsManagerCMD.sh install jpgc-redis && \
    apache-jmeter-5.2.1/bin/PluginsManagerCMD.sh install bzm-hls && \
    rm -rf apache-jmeter-5.2.1.tgz
ENV JMETER_HOME=/jmeter/apache-jmeter-${JMETER_VERSION}
ENV JMETER_BIN=${JMETER_HOME}/bin
ENV PATH $PATH:$JMETER_BIN
WORKDIR ${JMETER_BIN}