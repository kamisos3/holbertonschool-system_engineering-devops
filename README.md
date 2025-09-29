# Web Infrastrcuture Design

▶ **Introduction**

The web infrastructure is the foundation that lets websites and web applications to work by connecting them to the users and the computer using servers. Here you'll find an explanation on three infrastructure designs and how each the users input interacts with the server, DNS (Domain Name System) and database with their roles and defintions. Please feel free to enter the directory /web_infracstructure_design/ to access each diagram.

▶ **Table of Contents**

- [Simple Web Stack](#simplewebstack)
- [Distributed Web Infrastructure](#distributedwebinfrastructure)
- [Secured and Monitored Web Infrastructure](#securedandmonitoredwebinfrastructure)
- [Author](#author)

# I - Simple Web Stack

- The user makes a HTTP request by typing www.foobar.com
- The DNS converts the HTTP adress into an IP adress 8.8.8.8 to connect and retrieve the information.
- Ngnix Web Server gets the request to handle it.
- Servers are computers or systems that distribute data over the network; they host the web server, application server, applications files/codebase and the database.
- If the content changes in real-time, Ngnix will pass it through the Application Server.
- MySQL is queried to save or call the information needed from the database.
- This accesses the Application Files, the codebase in which the applications functions are kept.

# II - Distributed Web Infrastructure

- The user makes an HTTP request, this is goes trough a Load Balancer, HAProxy.
- The Load Balancer is a distribution algorithm added to distribute traffic across multiple servers; 'Server 1' and 'Server 2'. They work two ways, both of the servers are active and handle requests simultaneosly or one is active, and the other server is standing by.
- The servers contain identical an Ngnix Web Server, Application Server, and the Application Files to distrubute the load.
- These servers then query MySQL to retrieve or load information from the Database Cluster.
- The SPOF (Single Points of Failure) are in the Load Balancer and Database Cluster because they are not monitored, doesn,t handle HTTPS or has network segmentation.

# III - Secured and Monitored Web Infrastructure

- This structure now has a 'Firewall 1' within the Load Balancer that handles HTTPS, a SSL certificate that is added  to encrypt the data between the users and the website. This is required a a security standard.
- HTTPS is the Hypertext Transfer Protocol Secure that encrypts and authenticate the users information.
- The Load Balancer also has one of three Monitoring Clients, this one is to track traffic distribution and performance.
- 'Firewall 1' and 'Firewall 2' protect the servers, adding more layers of security.
- Firewalls are security systems that monitor network traffic to block and prevent cyber-attacks.
- 'Server 1' and 'Server 2' have a Monitoring Client each to verify their health and management, this also helps to optimize their performance.

▶ Author

Kami Sostre [https://github.com/kamisos3]