FROM tradelogger/java
LABEL maintainer="Misak Boulatian"
ENV JDBC_DRIVER_VERSION 42.2.2
ENV VERSION 12.0.0.Final
ENV INSTALL_DIR /opt
ENV WILDFLY_HOME ${INSTALL_DIR}/wildfly-${VERSION}
ENV DEPLOYMENT_DIR ${WILDFLY_HOME}/standalone/deployments/
ENV CONFIGURATION_DIR ${WILDFLY_HOME}/standalone/configuration
RUN useradd -b /opt -m -s /bin/sh -d ${INSTALL_DIR} serveradmin && echo serveradmin:serveradmin | chpasswd
RUN curl -O https://download.jboss.org/wildfly/${VERSION}/wildfly-${VERSION}.zip \
    && unzip wildfly-${VERSION}.zip -d ${INSTALL_DIR} \
    && rm wildfly-${VERSION}.zip 
ADD https://jdbc.postgresql.org/download/postgresql-${JDBC_DRIVER_VERSION}.jar ${DEPLOYMENT_DIR}
RUN chown -R serveradmin:serveradmin /opt \
    && chmod a+x ${WILDFLY_HOME}/bin/standalone.sh \
    && chmod -R a+rw ${INSTALL_DIR}    
USER serveradmin
ENTRYPOINT ${WILDFLY_HOME}/bin/standalone.sh -c standalone-ee8.xml -b=0.0.0.0 
EXPOSE 8080
