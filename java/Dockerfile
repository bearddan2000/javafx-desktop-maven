FROM openjdk:11-jdk

RUN apt-get update \
    && apt-get install --no-install-recommends -y \
        openjfx \
        tar \
        maven \
    && apt-get upgrade -y \
    && apt-get clean \
    && rm -f /var/lib/apt/lists/*_dists_*

ARG USER_HOME_DIR="/root"

ENV DISPLAY ":0"
ENV MAVEN_HOME /usr/share/maven
ENV MAVEN_CONFIG "$USER_HOME_DIR/.m2"

COPY mvn-entrypoint.sh /usr/local/bin/mvn-entrypoint.sh
COPY settings-docker.xml /usr/share/maven/ref/

VOLUME "$USER_HOME_DIR/.m2"

ENTRYPOINT ["/usr/local/bin/mvn-entrypoint.sh"]

WORKDIR $USER_HOME_DIR

COPY ./bin/ $USER_HOME_DIR

RUN tar -zxvf src.tar.gz src && \
    chmod -R +x *

CMD ["mvn", "clean", "install", "compile", "package", "exec:java"]
