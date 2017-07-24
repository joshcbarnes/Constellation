FROM openjdk:8

MAINTAINER Michal Hynek <michal.hynek@allocadia.com>

ENV DYNAMODB_HOME /opt/dynamodb

RUN mkdir -p ${DYNAMODB_HOME}
WORKDIR ${DYNAMODB_HOME}

# unzip DynamoDB client in /opt/dynamodb
COPY dynamodb_local_latest.tar.gz ${DYNAMODB_HOME}
RUN tar -xzf ${DYNAMODB_HOME}/dynamodb_local_latest.tar.gz && rm ${DYNAMODB_HOME}/dynamodb_local_latest.tar.gz

EXPOSE 8000
ENTRYPOINT ["java", "-Djava.library.path=./DynamoDBLocal_lib", "-jar", "DynamoDBLocal.jar", "-dbPath", "/opt/dynamodb/data", "-sharedDb"]