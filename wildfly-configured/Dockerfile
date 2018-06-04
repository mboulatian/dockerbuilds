FROM tradelogger/wildfly
LABEL maintainer="Misak Boulatian"
ENV DB_HOST localhost
ENV DB_PORT 5432
ENV DB_NAME trades
ENV DB_USER web
ENV DB_PASSWORD abc123 
RUN rm ${WILDFLY_HOME}/standalone/configuration/standalone-ee8.xml
ADD standalone-ee8.xml ${WILDFLY_HOME}/standalone/configuration/
