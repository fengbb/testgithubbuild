#FROM dockerharbor.hc360.org/base/jdk1.6-tomcat6
FROM dockerharbor.hc360.org/base/jdk1.8
RUN rm -rfv /etc/localtime && \
    cp -fv /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
ENV LANG=zh_CN.GB18030 JAVA_HOME=\/usr\/local\/jdk1.8.0_121  JAVA_OPTS="-Xms128m -Xmx256m"
ENV PATH=$PATH:$JAVA_HOME/bin
COPY config  /usr/local/config
COPY microservice-gateway-zuul-0.0.1-SNAPSHOT.jar  /usr/local/microservice-gateway-zuul-0.0.1-SNAPSHOT.jar
#ADD server.xml  /usr/local/tomcat6/conf/server.xml
#ADD context.xml  /usr/local/tomcat6/conf/context.xml
WORKDIR /usr/local/
EXPOSE 80
#ENTRYPOINT ["java","-jar","mscompany-0.0.1-SNAPSHOT.jar"]
ENTRYPOINT ["sh","-c","java $JAVA_OPTS -jar microservice-gateway-zuul-0.0.1-SNAPSHOT.jar"]
#EXPOSE 22  
#EXPOSE 8080 
#CMD ["/usr/sbin/sshd", "-D"]