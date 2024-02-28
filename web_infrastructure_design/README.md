<p align="center">
    <img [Web infrastructure design] src="https://itinfrastructure.report/images/Resources/9b490421-bb43-400d-b1b4-98d831cf82f7_orchestration-of-infrastructure-in-a-hybrid-environment.jpg">
</p>

----------

# <p align="center">Web infrastructure design</p>

----------

## ➤ Menu:

* [➤ Description]()
* [➤ Resources]()
* [➤ General]()
* [➤ Requirements]()
* [➤ Tasks]()
* [➤ Author]()

----------

## ➤ Description:



----------

## ➤ Concepts

For this project, we expect you to look at these concepts:

* [Network basics](https://intranet.hbtn.io/concepts/791)
* [Server](https://intranet.hbtn.io/concepts/799)
* [Web Server](https://intranet.hbtn.io/concepts/800)
* [DNS](https://intranet.hbtn.io/concepts/803)
* [Load balancer](https://intranet.hbtn.io/concepts/804)
* [Monitoring](https://intranet.hbtn.io/concepts/805)

## ➤ Resources:

Read or watch:

* Network basics concept page
* Server concept page
* Web server concept page
* DNS concept page
* Load balancer concept page
* Monitoring concept page
* [What is a database](https://intranet.hbtn.io/rltoken/7Pp0_Mdit6r_ZdRGKAwcqw)
* [What’s the difference between a web server and an app server?](https://intranet.hbtn.io/rltoken/YqKvabbDDtSjnHMV9g1gHw)
* [DNS record types](https://intranet.hbtn.io/rltoken/kZXE57FUOK-cqmLfN3CWfg)
* [Single point of failure](https://intranet.hbtn.io/rltoken/56OIJ23o5mqSaSeLEwxzJg)
* [How to avoid downtime when deploying new code](https://intranet.hbtn.io/rltoken/lxwkY5pRIVzatMPXwx6yew)
* [High availability cluster (active-active/active-passive)](https://intranet.hbtn.io/rltoken/rITwKN4AKP1hXZl2FKcAcw)
* [What is HTTPS](https://intranet.hbtn.io/rltoken/iEaO7X54UemiSN9z8TtFVA)
* [What is a firewall](https://intranet.hbtn.io/rltoken/P2A36USOkcekiqHsCzTefQ)

----------

## ➤ Requirements:

General

* A README.md file, at the root of the folder of the project, is mandatory
* For each task, once you are done whiteboarding (on a whiteboard, piece of paper or software or your choice), take a  picture/screenshot of your diagram
* This project will be manually reviewed:
* As each task is completed, the name of that task will turn green
* Upload a screenshot, showing that you completed the required levels, to any image hosting service (I personally use imgur but feel free to use anything you want).
* For the following tasks, insert the link from of your screenshot into the answer file
* After pushing your answer file to GitHub, insert the GitHub file link into the URL box
* You will also have to whiteboard each task in front of a mentor, staff or student - no computer or notes will be allowed during the whiteboarding session
* Focus on what you are being asked:
* Cover what the requirements mention, we will explore details in a later project
* Keep in mind that you will have 30 minutes to perform the exercise, you will get points for what is asked in requirements
* Similarly in a job interview, you should answer what the interviewer asked for, be careful about being too verbose - always ask the interviewer if going into details is necessary - speaking too much can play against you
* In this project, again, avoid going in details if not asked

----------

## ➤ Quiz:

<details>
<summary>Questions:</summary>

**Question #0**
What is a server?

* * A server is a device, a virtual device or computer program for providing functionality for other programs or devices, called “clients”.

* A server is a software that serves web pages.

* A server is returning information to other computers when asked.

**Question #1**
What is a web server?

* A web server is a software or physical device serving web pages over HTTP.

* * A web server is a software that serves web pages to clients upon their request, it does this over the protocol HTTP.

* A web server is a software that serves web pages to clients upon their request.

**Question #2**
What is a codebase?

* A list of software libraries.

* * Is the collection of source code that is used to build a software system.

* Is the most important files of a software system.

**Question #3**
What is a database?

* Is a collection of text files that are stored so that it can be easily accessed, updated and managed by the local application.

* Is a collection of information that is stored on a physical server and organized so that it can be easily accessed, updated and managed.

* * Is a collection of information that is stored and organized so that it can be easily accessed, updated and managed.

**Question #4**
What is a DNS?

* A list of domain names.

* * A system to translate domain names into IP addresses.

* A system that contain all Internet IPs.

**Question #5**
What is HTTPS?

* A faster version of HTTP.

* A version of HTTP that protect your personal information.

* * A version of HTTP that secure the traffic between your browser and the website by encrypting it.

**Question #6**
What is TCP/IP?

* * Transmission Control Protocol/Internet Protocol, is a suite of communications protocols used to interconnect network  devices on the Internet or any private network.

* Transmission Control Protocol/Internet Protocol, is a suite of communications protocols used to interconnect network devices on the Internet.

* Transmission Control Protocol/Internet Protocol, is a suite of communications protocols used to interconnect network devices on private network.
</details>

----------

## ➤ Tasks:

### 0. Simple web stack

A lot of websites are powered by simple web infrastructure, a lot of time it is composed of a single server with a [LAMP stack](https://intranet.hbtn.io/rltoken/OtZFy7tXzJmziqfiXKT5lA).

On a whiteboard, design a one server web infrastructure that hosts the website that is reachable via `www.foobar.com`. Start your explanation by having a user wanting to access your website.

Requirements:

* You must use:
 * 1 server
 * 1 web server (Nginx)
 * 1 application server
 * 1 application files (your code base)
 * 1 database (MySQL)
 * 1 domain name `foobar.com` configured with a `www` record that points to your server IP `8.8.8.8`

* You must be able to explain some specifics about this infrastructure:
 * What is a server
 * What is the role of the domain name
 * What type of DNS record `www` is in `www.foobar.com`
 * What is the role of the web server
 * What is the role of the application server
 * What is the role of the database
 * What is the server using to communicate with the computer of the user requesting the website

* You must be able to explain what the issues are with this infrastructure:
 * SPOF
 * Downtime when maintenance needed (like deploying new code web server needs to be restarted)
 * Cannot scale if too much incoming traffic
 
 Please, remember that everything must be written in English to further your technical ability in a variety of settings.

Repo:

* GitHub repository: holbertonschool-system_engineering-devops
* Directory: web_infrastructure_design
* File: 0-simple_web_stack

Please review your task manually with the following checklist
README.md exists and is not empty

<details>
<summary>Checklist</summary>

* README.md exists and is not empty
* The student drew a server on the diagram
* The student explained that a server is generally located in a data center
* The student explained that a server can be physical or virtual
* The student explained that a server runs an OS
* The student drew a web server on the diagram
* The student explained that a web server’s role is to serve web pages (static content)
* The student explains that an application server’s role is to compute dynamic content
* The student drew a code base on the diagram
* The student drew a database on the diagram
* The student explains that a database’s role is to store application data
* The student drew application files (code base) on the diagram
* The student explained that the DNS’s role is to translate the record of a domain name into an IP address
* The student explained that www.foobar.com is an A record because it resolves to an IP address
* The student explained that this server is a single point of failure because nothing is redundant
* The student explained that the website would be temporarily down when new code is deployed and the web server needs * to be restarted
* The student explained that this infrastructure cannot scale and will not be able to handle traffic that would exceed the server capacity
* The student explained that the server is communicating over a network (TCP/IP)
* The student’s repository contains a link to a diagram about this task (do not check the accuracy of it)
* The student drew an application server on the diagram

</details>

### 1. Distributed web infrastructure

On a whiteboard, design a three server web infrastructure that hosts the website www.foobar.com.

Requirements:

* You must add:
 * 2 servers
 * 1 web server (Nginx)
 * 1 application server
 * 1 load-balancer (HAproxy)
 * 1 set of application files (your code base)
 * 1 database (MySQL)

* You must be able to explain some specifics about this infrastructure:
 * For every additional element, why you are adding it
 * What distribution algorithm your load balancer is configured with and how it works
 * Is your load-balancer enabling an Active-Active or Active-Passive setup, explain the difference between both
 * How a database Primary-Replica (Master-Slave) cluster works
 * What is the difference between the Primary node and the Replica node in regard to the application

* You must be able to explain what the issues are with this infrastructure:
 * Where are SPOF
 * Security issues (no firewall, no HTTPS)
 * No monitoring

Please, remember that everything must be written in English to further your technical ability in a variety of settings.

Repo:

* GitHub repository: holbertonschool-system_engineering-devops
* Directory: web_infrastructure_design
* File: 1-distributed_web_infrastructure

Please review your task manually with the following checklist

<details>
<summary>Checklist</summary>

* A server containing a web server, application server, database, and code base so that there is redundancy with the other server
* A load balancer is added to distribute traffic between the 2 servers (or failover)
* Explain if the load balancer is configured to have an active-active or active-passive setup (their choice)
* The MySQL Master-Replica cluster used replication to keep data synchronized
* The Master database node can accept reads/writes while the Replica can only accept reads
* The load balancer is still a single point of failure
* There is no firewall on servers
* Traffic is unencrypted
* No monitoring
* The student’s repository contains a link to a diagram about this task (do not check the accuracy of it)

</details>

### 2. Secured and monitored web infrastructure

On a whiteboard, design a three server web infrastructure that hosts the website www.foobar.com, it must be secured, serve encrypted traffic, and be monitored.

Requirements:

* You must add:
 * 3 firewalls
 * 1 SSL certificate to serve www.foobar.com over HTTPS
 * 3 monitoring clients (data collector for Sumologic or other monitoring services)
* You must be able to explain some specifics about this infrastructure:
 * For every additional element, why you are adding it
 * What are firewalls for
 * Why is the traffic served over HTTPS
 * What monitoring is used for
 * How the monitoring tool is collecting data
 * Explain what to do if you want to monitor your web server QPS
* You must be able to explain what the issues are with this infrastructure:
 * Why terminating SSL at the load balancer level is an issue
 * Why having only one MySQL server capable of accepting writes is an issue
 * Why having servers with all the same components (database, web server and application server) might be a problem

Please, remember that everything must be written in English to further your technical ability in a variety of settings.

Repo:

* GitHub repository: holbertonschool-system_engineering-devops
* Directory: web_infrastructure_design
* File: 2-secured_and_monitored_web_infrastructure

Please review your task manually with the following checklist

<details>
<summary>Checklist</summary>

* Firewall filters network traffic in and out a machine
* HTTPS is setup so that if someone intercepts the traffic, it cannot be read
* Monitoring can be used to check if something is broken or slow
* The monitoring setup is composed of a client collecting data and sending it to the monitoring system
* Configure monitoring to:
collect web server data
have an alert triggered if QPS is getting out of control
* Terminating SSL at the load balancer level is an issue because the traffic between the load balancer and the web servers is unencrypted
* Having only one MySQL server capable of accepting writes is an issue because if the master goes down, the application cannot write to the database anymore
* The student’s repository contains a link to a diagram about this task (do not check the accuracy of it)
* Having servers with all the same components (database, web server and application server) might be a problem because their consumption will not grow the same way between each of them (we might want to have more database servers than application servers for instance).
* Having servers with all the same components (database, web server and application server) might be a problem because when there is maintenance performed on a server for a specific component, it will affect other components that are on it
* The student drew a firewall on the diagram
* Load-balancer is a SPOF

</details>

### 3. Scale up

Readme

* [Application server vs web server](https://intranet.hbtn.io/rltoken/QHWrcB0kVYwbgWCsL57mkQ)

Requirements:

* You must add:
 * 1 server
 * 1 load-balancer (HAproxy) configured as cluster with the other one
 * Split components (web server, application server, database) with their own server
* You must be able to explain some specifics about this infrastructure:
 * For every additional element, why you are adding it

Please, remember that everything must be written in English to further your technical ability in a variety of settings.

Repo:

* GitHub repository: holbertonschool-system_engineering-devops
* Directory: web_infrastructure_design
* File: 3-scale_up

Please review your task manually with the following checklist

<details>
<summary>Checklist</summary>

* The student drew additional servers
* The student drew an additional load-balancer
* The student explains that the load balancer is configured as a cluster so that if one fails, the other takes over
* The student’s repository contain a link to a diagram about this task (do not check the accuracy of it)
* The student adds servers containing a single component inside them (such as a web server, application server or database)

</details>

----------

## ➤ Author:

- Amandine KEMP