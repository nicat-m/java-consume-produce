## JAVA simple app connect to kafka with sasl_ssl

```
# Set env

kafka.bootstrapServers=broker1.local:9092,broker2.local:9092,broker3.local:9092
kafka.username=${SASL_USER}
kafka.password=${SALS_PASS}
kafka.truststoreLocation=${TRUSTSTORE_PATH}
kafka.truststorePassword=${TRUSTSTORE_PASS}

# Build
mvn clean install

# Run

java -jar target/demo-0.0.1-SNAPSHOT.jar

# Test producer

curl -X POST http://localhost:8080/kafka/produce \
  -H "Content-Type: application/json" \
  -d '{"key": "user1", "message": "simple java app"}'

# Test consumer

curl http://localhost:8080/kafka/consume
```