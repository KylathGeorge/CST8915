# CST8915: Lab 3

## Name: Kylath Mamman George

## Student Number: 041198835

### Youtube Link

[Lab 3 Youtube Link](https://www.youtube.com/watch?v=9S035f52u4Y)

### Reflection Questions

**1. What challenges did you encounter when configuring environment variables in the GitHub Actions workflow?**

Following the instructions didn't make it too difficult to find out where to add the variables, however in the instructions it was mentioned to replace part of the code with your app service name, rather than just using the default domain provided by Azure Apps Services.

There was another issue in where I learned that flask apps in python may have trouble starting itself.  I could see that the app deployed because it took me to the deployed default page, which linked to the deployment center. I learned how to enable log streams for troubleshooting purposes and how to add a start command using gunicorn for python. I opted to add the command directly in Azure rather than creating a start.txt. After adding gunicorn as a dependency and as a start command in azure app services, the product service would start but get stuck loading and return a 404 error. In the log streams I could see that the gunicorn command started the app but it could not do anything after that. I had to manually access the product service default domain with "/products" at the end once, and then it worked everytime after that. After some research it seemed like there may have been because Flask only sent CORS headers for "GET/products" and the browser decided to send a preflight request of "OPTIONS/products" which didn't return the correct headers. After manually accessing the "/products", the browser may have cached the GET response, which is why it worked everytime after that. I tried this in a different browser to check if it was caching, however it worked everytime so I'm assuming it did a direct GET so there was no preflight. I am not entirely sure this was the way understand it, but it seems to have worked.

**2. How does deploying microservices on Azure Web App Service differ from running them locally?**

Using Azure Web App services comes with ease of use to build the microservice and deploy it. It automatically integrates the workflow into your github repository if using one and deploys your app. There is continuous deployment, meaning once you commit and push your changes to your github repository, the workflow is automatically rebuilt and deployed. A default domain is provided for your web app by Azure Web App services as well to use. Environment variables are very easy to include without having to configure a .env file.

**3.Why is it important to use environment variables for configurations in a cloud environment?**
