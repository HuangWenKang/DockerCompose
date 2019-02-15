FROM maven:3.5-jdk-8

COPY node_modules/wait-for-it.sh/bin/wait-for-it /wait-for-it.sh
RUN chmod +x /wait-for-it.sh
WORKDIR /app
ENV WAITHOST=mysql WAITPORT=3306
ENTRYPOINT /wait-for-it.sh $WAITHOST:$WAITPORT --timeout=0 \
&& mvn clean spring-boot:run
