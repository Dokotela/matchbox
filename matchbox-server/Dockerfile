FROM bellsoft/liberica-openjdk-alpine:latest
MAINTAINER oliver egger <oliver.egger@ahdis.ch>
EXPOSE 8080

COPY ./target/matchbox.jar /matchbox.jar

ENV LANG='en_US.UTF-8' LANGUAGE='en_US:en' LC_ALL='en_US.UTF-8'
RUN mkdir -p /data/hapi/lucenefiles && chmod 775 /data/hapi/lucenefiles

ENTRYPOINT java -Xmx3072M -jar /matchbox.jar -Dspring.config.additional-location=optional:file:/config/application.yaml,optional:file:application.yaml

# used by .github/workflows/
