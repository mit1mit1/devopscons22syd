# Cloud Concepts - Draft

## What is the AWS Cloud?

AWS offers a huge variety of services, including but not limited to:

- Storage;
- Network Security;
- Blockchain;
- Machine Learning;
- Artificial Intelligence;
- Robot development platforms;
- Video production;
- Orbital satellites.

### What is cloud?

But to start from the beginning.

Most modern computing centers around a client-server model.

A client sends a request, and if the permissions are met, the server (e.g. an EC2 instance) returns the requested information.

A network is how the client talks to the server. The client and server will each have an IP address - you send your request with an IP address you would like to send it to, and then the server sends the response to your IP address.

What is the server made of? CPU which does the computations; RAM, which holds data for computation; Storage, which holds long term data; and Network related stuff, routers and so forth.

Terminology:

- Network: routers and servers connected over wires and wifi;
- Router: a networking device that forwards data packets between a computer and a network - it interprets an IP address and decides where to send a request;
- Switch: takes a packet and sends it to the correct server/client on a network.

Traditional way to build infrastructure: you put some servers in a garage, host a website. Your company grows, so you buy more and more garages and put more and more servers in it. Eventually you need to hire more and more people for maintenance, pay more for power, do more to handle failure cases. And what about the times when all this isn't used?

_Side note, AWS Principle 1: You only pay for what you use. If the server isn't returning data, you don't pay for it._

Cloud computing is the on demand delivery of resources over the internet with pay as you go pricing. You should always be able to assume that AWS will be able to provide the storage you need, and you should never need to plan for this in advance.

Cloud computing externalises all the work involved in hosting a server. It gives huge simplifications at scale.

_Side note, AWS Principle 2: Undifferentiated heavy lifting. AWS tries to cover common, time consuming and repetitive tasks._

### Deploy models of cloud

1. Private cloud: cloud services provided by a single organization, who has complete control over how it works. Can be good for meeting very specific business/security needs.

2. Public cloud (what we'll mostly care about): Cloud resources owned and operated by a third-party provider (e.g. Google Cloud, AWS), delivered over the internet.

3. Hybrid cloud: keep some servers on prem and extend some capabilities to the cloud. Gives some nice flexibility.


### Characteristics of cloud computing

1. On demand self service;
    - Users can provision resources without any action by AWS. 
2. Broad network access;
    - Resources can be accessed by diverse platforms.
3. Multi-tenancy and resource pooling;
    - Multiple customers can share infrastructure and applications and still have security - this provides:
4. Rapid elasticity and scalability.
  - Automatic and quick to acquire and dispose of resources. 
5. Measured service - pay for what you use.

### Advantages of cloud computing

1. Trade capital up front expense for operational on demand expense.
2. Benefit from efficiency of the large scale of cloud providers.
3. Stop having to guess capacity.
4. Increased speed and agility.
5. Stop having to manage Data Centers.
6. Go global in minutes.

### What cloud offers

- Flexibility: change resource types when needed;
- Cost-effectiveness: guarantee you'll only pay for what you use;
- Scalability: accommodate larger loads by adding resources easily;
- Elasticity: can scale in and out when needed;
- High availability and fault-tolerance: because of the scale of cloud services, you aren't going to crash because of a smoke alarm in your garage;
- Agility: it is very quick to develop, test and launch software on cloud.

### Types of Cloud Computing

1. Infrastructure as a service (IaaS). This provides building blocks for cloud IT - networking computers, data storage space, computing power, etc.. Think S3 or EC2.
2. Platform as a service. This removes the need to worry about underlying infrastructure, and lets focus on deployment and management of your applications. Think Elastic Beanstalk, Heroku
3. Software as a service. This is straight up giving you the software you need via the cloud. Think Gmail, Dropbox.

### AWS Pricing Fundamentals

1. Compute - you pay for your exact compute time.
2. Storage - you pay for data stored in the cloud.
3. Data transfer out of cloud - data going into the cloud is free, data out is paid for.

### What is EC2?



## What is the AWS Cloud value proposition?

Benefits of cloud:

- Trade upfront expense (running a data center or server) for variable expense (pay AWS based on the number of requests your lambda gets, ...).
  - This means you don't have to pay for on-premises resources and their maintenance.
  - This also means you don't have to guess capacity.
- Benefit from economies of scale. Aggregated usage makes AWS more efficient than everyone running their own data center.
- Increase speed of development and agility to get new resources.
- Deploy applications such that they can be accessed globally with low latency.