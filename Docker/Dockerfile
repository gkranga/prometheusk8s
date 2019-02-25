FROM tomcat:8.0-jre8
COPY OnlineShoppingPortal.war /usr/local/tomcat/webapps/
COPY jmx_prometheus_javaagent-0.11.0.jar /root/
COPY config.yaml /root/
RUN chmod -R o+x /root
RUN chmod 777 /root/jmx_prometheus_javaagent-0.11.0.jar /root/config.yaml
ENV JAVA_OPTS="$JAVA_OPTS -javaagent:/root/jmx_prometheus_javaagent-0.11.0.jar=8080:/root/config.yaml"
EXPOSE 8080 
CMD ["catalina.sh", "run"] 
