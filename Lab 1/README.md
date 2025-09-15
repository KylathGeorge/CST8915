# CST8915: Lab 1

## Name: Kylath Mamman George

## Student Number: 041198835

### Youtube Link:-

### Order Service

**1.What is the service responsible for?**

-The order service is a service that is responsible for dealing with the customer orders.

**2.Which language/framework does it use?**

-This service uses Node.js.

**3.How does it interact with the other services?**

-It receives orders from the store front and sends the orders to the RabbitMQ message queue. When an order is sent, the order data is extracted from the body of the request. A channel is created with RabbitMQ and queue formed where the order is sent and it is converted to a JSON string. Once this is completed a response is sent to the client confirming that the order was received.

### Product Service

**-What is the service responsible for?**
   
**-Which language/framework does it use?**

**-How does it interact with the other services?**

### Store Front

**-What is the service responsible for?**

**-Which language/framework does it use?**

**-How does it interact with the other services?**
