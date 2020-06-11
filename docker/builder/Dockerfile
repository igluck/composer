FROM tomcat:9



RUN apt update && apt install -y \
    git \
    maven \
    \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /build



RUN git clone https://github.com/jenkinsci/jenkins.git && \
    cd jenkins && \
    mvn -am -pl war,bom -DskipTests -Dspotbugs.skip clean install
RUN cp jenkins/war/target/jenkins.war /mnt/jenkins.war
