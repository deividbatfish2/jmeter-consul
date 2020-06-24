FROM jmeter-base:latest
LABEL Author="Deivid Teixeira"
ARG COMUNICATION_PORT=60000
EXPOSE 1099 ${COMUNICATION_PORT}
CMD ["java", "-Xms256m", "-Xmx1024m"]
CMD ["./jmeter-server", "-Jserver.rmi.ssl.disable=true", "-Jserver.rmi.localport=${COMUNICATION_PORT}"]