# CST8915: Lab 2

## Name: Kylath Mamman George

## Student Number: 041198835

### Youtube Link

[Lab 2 Youtube Link](https://www.youtube.com/watch?v=1x_jV4dPfak)

Order Service Repository: <https://github.com/KylathGeorge/order-service>

Product Service Repository: <https://github.com/KylathGeorge/product-service>

Store Front Repository: <https://github.com/KylathGeorge/store-front>

### Reflection Questions

**1. What changes did you make to the order-service and product-service to comply with the Configurations and Backing Services factors of the 12-Factor App methodology?**

<ins>Configuration</ins>

With order-srevice the code was changed from using hardcoded variables to using environment variables by updating index.js. A new .env file was added with the RabbitMQ connection string and the port to listen to. Another update was made to product service to the main rust file and a new .env file was added as well.

<ins>Backing Services</ins>

RabbitMQ is treated as an attached resource. This is true because the variables required to connect to it are stored in the .env files and we could at any time change these environment variables to swap out RabbitMQ for another similar system without any changes to the code because the code fetches the required variables from the .env file.

**2. Why is it important to use environment variables instead of hard-coding configurations in your application?**

Having environment variables helps out swapping backing services as mentioned above without making any changes to the code itself. This allows for easier management. Environment variables are only stored in the environment and are not checked into the code repo which makes it less likely any accidental changes are made and easier to solve any related bugs. There is a security factor as well which is really important; any credentials or sensitive information required is stored in the environment and not in the code, meaning if the code was exposed there would be little security risk of the credentials being exposed.

**3. Why is it important to have separate repositories for each microservice? How does this help maintain independence and scalability of each service?**

This allows each microservice to be loosely coupled and allows each of them to be independent and have no or little knowledge of the other services. If one service goes down due to a bug or other reasons, the other services will not be affected. This also allows for new services to be added without affecting other services. This also makes it a lot easier to manage each service and have different working builds for each service, in turn easier to manage which versions go into production for each service as they do not depend on each other.
