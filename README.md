## A Zuul Based API Proxy

First clone this repos and run (or push to Pivotal Cloud Foundry, [PWS](https://run.pivotal.io/))

# [Howdy Spring Boot](https://github.com/corbtastik/howdy-boot)
# [Howdy Kotlin](https://github.com/corbtastik/howdy-kotlin)
# [Howdy Nodejs](https://github.com/corbtastik/howdy-nodejs)
# [Howdy Python](https://github.com/corbtastik/howdy-python)

Then clone and run the proxy

./mvnw spring-boot:run

Test the APIs with curl

See:
``src/main/resources/application.yml``

For API endpoints being proxied.

Uses Spring Cloud Zuul to proxy all the Howdy apps above and bring them under the same API umbrella. This demonstrates how you can pull together microservices implemented in different languages, each exposing a different part of an API.
