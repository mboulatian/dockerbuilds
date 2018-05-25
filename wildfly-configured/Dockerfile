FROM tradelogger/wildfly
LABEL maintainer="Misak Boulatian"
RUN rm ${WILDFLY_HOME}/standalone/configuration/standalone-ee8.xml
ADD standalone-ee8.xml ${WILDFLY_HOME}/standalone/configuration/