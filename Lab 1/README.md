# CST8915: Lab 1

## Name: Kylath Mamman George

## Student Number: 041198835

### Youtube Link:-

### Order Service

**1.What is the service responsible for?**

The order service is a service that is responsible for dealing with the customer orders.

**2.Which language/framework does it use?**

This service uses Node.js.

**3.How does it interact with the other services?**

It receives orders from the store front and sends the orders to the RabbitMQ message queue. When an order is sent, the order data is extracted from the body of the request. A channel is created with RabbitMQ and queue formed where the order is sent and it is converted to a JSON string. Once this is completed a response is sent to the client confirming that the order was received.

### Product Service

**1.What is the service responsible for?**

This serviced is responsible for showing the catalog of products, which is a list of products that is fetched using a RESTful API.

**2.Which language/framework does it use?**

It uses Rust and Cargo.
  
**3.How does it interact with the other services?**

This service uses CORS to handle requests coming from the front end. It also restricts the allowed methods, only GET methods are allowed in this case. When a GET request is made for the products, the server will return a JSON array of products which are objects. This server will listen for any incoming requests and route them to the products.

### Store Front

**1.What is the service responsible for?**

**2.Which language/framework does it use?**

**3.How does it interact with the other services?**
