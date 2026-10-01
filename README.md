# CST8915 Lab 2

**Student Name**: Connor Dickson    
**Student ID**: 041085826
**Course**: CST8915 Full-stack Cloud-native Development
**Semester**: Fall 2026

---

## Demo Video

🎥 [Watch Demo Video](https://youtu.be/Hs6HqIpRmmE)

---
## Disclaimer: Azure only allowed me to allocate 3 VMs.

## Reflection Questions

### What changes were made to order-service and product-service?

The changes made to the services to comply with the configuration aspect of the 12 Factor application were that variables that had been hard-coded into the applications were replaced, and moved to an envrinment variable file where they are strictly separated from the code. The Backing services to the application were changed to only be accessed via URL, RabbitMQ specifically requiring credentials for the order-service to access it.

### Why is it important to use environment variables instead of hard coding configurations?

It is important to use environment variables instead of hard-coding configurations as the variables necessary for the app to function will likely not stay the same during each deployment. Having separate environment variables makes the app significantly more portable than it would be with hard-coded data. 

### Why are separate repositories important for each microservice?

Keeping each microservice in its own repository is good as it makes deployment of individual services much easier. A team for each microservice can manage a single repository, maintaining only the codebase that they are tasked with working on. This increases the scalability and agility of each service indepently.

---

## Challenges and Learnings (Optional)

The most time consuming challenge I faced was an issue with the services not communicating through with each other when having to programmatically make http requests. When I attempted to troubleshoot by pinging each service from another one there were no connection issues apparent, so the fact that it only happened when the services were attempting to send requests made me think it was an issue with the environment variables. After looking and confirming that everything looked as though it should be working. I changed the names of the .env files as I had named them after the services they were associated with (ex: store-front.env). After that the http requests went through without issue.

---

## Service repositories
[Order-service](https://github.com/ConnorD3/order-service)
[Product-service](https://github.com/ConnorD3/product-service)
[Store-front](https://github.com/ConnorD3/store-front)

---

## Acknowledgments

Bedmutha, A. (2025, February 25). *Should each microservice have a separate git repository?*. Medium. https://medium.com/@bedmuthaapoorv/should-each-microservice-have-a-separate-git-repository-fc64c57784a0

Wiggins, A. (2017a). III. Config. The twelve-factor app. https://12factor.net/config

Wiggins, A. (2017b). IV. Backing services. The twelve-factor app. https://12factor.net/backing-services

During the reading of the instructions, Google AI was used to assist in understanding and breaking down the lab instructions
