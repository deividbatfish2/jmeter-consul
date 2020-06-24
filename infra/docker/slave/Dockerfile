FROM deividbatfish2/jmeter-consul-base:v2
LABEL Author="Deivid Teixeira"
ARG COMUNICATION_PORT=60000
EXPOSE 1099 ${COMUNICATION_PORT}
COPY slave-service.json /etc/consul.d
CMD ["java", "-Xms256m", "-Xmx1024m"]
CMD ["./jmeter-server", "-Jserver.rmi.ssl.disable=true", "-Jserver.rmi.localport=${COMUNICATION_PORT}"]