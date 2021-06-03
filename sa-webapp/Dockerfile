FROM openjdk:11-jdk

WORKDIR /app

COPY . .

RUN ./mvnw install

# Setting this to point to the host's localhost
ENV SA_LOGIC_API_URL http://host.docker.internal:5000

EXPOSE 8080

CMD ["java", "-jar", "target/sentiment-analysis-web-1.0-SNAPSHOT.jar", "--sa.logic.api.url=${SA_LOGIC_API_URL}"]
