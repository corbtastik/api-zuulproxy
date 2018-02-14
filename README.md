## A Zuul Based API Proxy

The purpose of this project is to front several microservices implemented in different languages running in cloud foundry.  One of the benifites of microservices is the power of choice.  If you're a java geek then use java, python hey go for it, kotlin even better!  Use what you and your team are comfortable with.  The thing is...the more you use the harder it becomes to operationalize.  Enter Cloud Foundry...it helps provide developer choice yet maintain operational sanity.

This demo provides an API front to the following microservices:

[howdy-akka](https://github.com/corbtastik/howdy-akka)
[howdy-boot](https://github.com/corbtastik/howdy-boot)
[howdy-nodejs](https://github.com/corbtastik/howdy-nodejs)
[howdy-kotlin](https://github.com/corbtastik/howdy-kotlin)
[howdy-python](https://github.com/corbtastik/howdy-python)

1. Clone this repo
1. Clone the microservice repos above
1. If nessesary build each project (akka, boot and kotlin)
1. Login to Cloud Foundry ([Pivotal Web Services](https://run.pivotal.io/) is an excellent choice)
1. cf push each microservice (you may need to specify random-route in manifest.yml)
1. Record the end-point for each microservice
1. Clone this repo
1. Add the end-point(s) into manifest.yml
1. Build ./mvnw clean package
1. cf push (you may need to specify random-route in manifest.yml)
1. test calls through the api-proxy


Then clone and run the proxy

./mvnw spring-boot:run

Test the APIs with curl

See:
``src/main/resources/application.yml``

For API endpoints being proxied.

Uses Spring Cloud Zuul to proxy all the Howdy apps above and bring them under the same API umbrella. This demonstrates how you can pull together microservices implemented in different languages, each exposing a different part of an API.
