##Docker

Make sure you have a local Docker installed and running, then type:

- $ ./mvnw spring-boot:build-image

## Images
All the steps below needs a docker user, as you can see  in the code I'm using my personal one but I highly  recommend use your personal account.
- https://hub.docker.com/u/dockerUser
- Currency Exchange Service 
	- dockerUser/mmv2-currency-exchange-service:0.0.1-SNAPSHOT
- Currency Conversion Service
	- dockerUser/mmv2-currency-conversion-service:0.0.1-SNAPSHOT
- Eureka
	- dockerUser/mmv2-naming-server:0.0.1-SNAPSHOT
- API GATEWAY
	- dockerUser/mmv2-api-gateway:0.0.1-SNAPSHOT

## URLS

#### Currency Exchange Service
- http://localhost:8000/currency-exchange/from/USD/to/INR

#### Currency Conversion Service
- http://localhost:8100/currency-conversion/from/USD/to/INR/quantity/10
- http://localhost:8100/currency-conversion-feign/from/USD/to/INR/quantity/10

#### Eureka
- http://localhost:8761/

#### Zipkin
- http://localhost:9411/

#### API GATEWAY
- http://localhost:8765/currency-exchange/from/USD/to/INR
- http://localhost:8765/currency-conversion/from/USD/to/INR/quantity/10
- http://localhost:8765/currency-conversion-feign/from/USD/to/INR/quantity/10
- http://localhost:8765/currency-conversion-new/from/USD/to/INR/quantity/10

#### Commands
```
docker run -p 9411:9411 openzipkin/zipkin:2.23
docker push docker.io/dockerUser/mmv2-currency-exchange-service:0.0.1-SNAPSHOT
docker-compose --version
docker-compose up
docker push dockerUser/mmv2-naming-server:0.0.1-SNAPSHOT
docker push dockerUser/mmv2-currency-conversion-service:0.0.1-SNAPSHOT
docker push dockerUser/mmv2-api-gateway:0.0.1-SNAPSHOT
watch -n 0.1 curl http://localhost:8000/sample-api
```