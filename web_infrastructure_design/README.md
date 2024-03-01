<p align="center">
    <img [0. Simple web stack] src="https://github.com/amandinekemp/holbertonschool-system_engineering-devops/blob/main/web_infrastructure_design/0-simple_web_stack.png">
</p>

----------

# <p align="center">0. Simple web stack</p>

----------

**Simple Web Infrastructure**

1. **User Accessing the Website:**
   A user enters the URL www.foobar.com into their browser.

2. **Server:**
   A single server hosts all components of the web infrastructure.

3. **Web Server (Nginx):**
   The web server receives HTTP requests from users and returns the corresponding web pages. In this case, Nginx is used as the web server.

4. **Application Server:**
   The application server hosts and executes the application code. It can be PHP, Python, or any other programming language. In our case, we use PHP.

5. **Application Files:**
   The application files contain the source code of our website.

6. **Database (MySQL):**
   The MySQL database stores data necessary for the website's operation, such as users, blog articles, etc.

7. **Domain Name:**
   The domain name www.foobar.com is used to access the website. It is configured with an A-type DNS record pointing to the server's IP address (8.8.8.8).

**Explanations:**

- **Server:** A server is a device or software program that provides functionality to other programs or devices, known as "clients."

- **Role of the Domain Name:** The domain name is a user-friendly identifier to access the website hosted on the server.

- **Type of DNS Record for www:** The DNS record www in www.foobar.com is a CNAME (Canonical Name) record pointing to another DNS record or an IP address.

- **Role of the Web Server:** The web server (Nginx in this case) receives requests from users and returns the corresponding web pages.

- **Role of the Application Server:** The application server executes the application code (e.g., PHP) to generate dynamic web pages.

- **Role of the Database:** The database stores and manages data used by the website, such as users and blog articles.

- **Communication with the User:** The server communicates with the user's computer using the HTTP protocol, which enables data transfer between the server and the user's web browser.

**Potential Issues:**

- **SPOF (Single Point of Failure):** If the server fails, the website becomes inaccessible as all components are hosted on a single server.
  
- **Downtime during Maintenance:** When code updates or maintenance are required, the web server needs to be restarted, resulting in website downtime.
  
- **Difficulty Scaling:** If the website experiences increased traffic, the single server may struggle to handle the load, leading to slowdowns or website downtime.

----------
layout
<p align="center">
    <img [1. Distributed web infrastructure] src="https://github.com/amandinekemp/holbertonschool-system_engineering-devops/blob/main/web_infrastructure_design/1-distributed_web_infrastructure.png">
</p>

----------

# <p align="center">1. Distributed web infrastructure</p>

----------

**Explanation:**

- **Load Balancer:** The load balancer is added to distribute incoming web traffic across multiple servers to improve performance, scalability, and reliability. It ensures that no single server becomes overwhelmed with requests and helps in achieving high availability.

- **Web Servers:** Two web servers are deployed to handle incoming HTTP requests. Having multiple web servers increases redundancy and fault tolerance, as well as distributes the load to prevent overloading a single server.

- **Application Server:** The application server is responsible for executing the application code and generating dynamic content. Separating the application logic from the web servers allows for better scalability and maintenance.

- **Database:** The database stores the website's data and is essential for dynamic web applications. Using MySQL as the database management system allows for efficient data storage and retrieval.

**Specifics:**

- **Distribution Algorithm:** The load balancer is configured with a round-robin distribution algorithm, which evenly distributes incoming requests across the available servers in a circular manner.

- **Active-Active vs. Active-Passive Setup:** The load balancer enables an Active-Active setup, where all servers actively handle incoming requests simultaneously. In contrast, an Active-Passive setup would involve one server actively serving traffic while the other remains on standby for failover.

- **Primary-Replica Database Cluster:** In a Primary-Replica (Master-Slave) database cluster, the Primary node serves as the primary read-write node, handling all write operations and replicating data to the Replica nodes. Replica nodes act as read-only copies, synchronizing data with the Primary node for redundancy and failover.

- **Difference between Primary and Replica Nodes:** The Primary node handles write operations, ensuring data consistency and integrity. The Replica nodes serve as backups and handle read operations, distributing the read workload and providing fault tolerance.

**Issues:**

- **Single Points of Failure (SPOF):** The load balancer remains a single point of failure. If the load balancer fails, it can disrupt traffic distribution and impact the availability of the website.

- **Security Concerns:** Lack of a firewall and HTTPS implementation introduces security vulnerabilities, leaving the infrastructure susceptible to unauthorized access, data breaches, and other cyber threats.

- **Monitoring:** Without proper monitoring tools and processes in place, it becomes challenging to detect and address performance issues, security breaches, and other anomalies in the infrastructure promptly.

----------

<p align="center">
    <img [2. Secured and monitored web infrastructure] src="https://github.com/amandinekemp/holbertonschool-system_engineering-devops/blob/main/web_infrastructure_design/2-secured_and_monitored_web_infrastructure.png">
</p>

----------

# <p align="center">2. Secured and monitored web infrastructure</p>

----------

**Secured and Monitored Three-Server Web Infrastructure**

7. **SSL Certificate:**
   An SSL certificate is installed on the load balancer to enable HTTPS encryption for www.foobar.com. This ensures secure communication between users' browsers and the web servers, protecting sensitive data from interception and tampering.

8. **Monitoring Clients (Data Collectors):**
   Three monitoring clients are deployed on each server to collect performance metrics, logs, and other relevant data. These clients send collected data to a monitoring tool (e.g., Sumo Logic) for analysis and visualization.

**Specifics:**

- **Firewalls:** Firewalls are added to enhance security by filtering and monitoring network traffic, preventing unauthorized access, and mitigating potential security threats such as DDoS attacks, malware, and intrusion attempts.

- **HTTPS Traffic:** HTTPS encrypts data transmitted between users' browsers and the web servers, protecting sensitive information from eavesdropping and tampering. Serving traffic over HTTPS is essential for ensuring data confidentiality and integrity.

- **Monitoring:** Monitoring is used to track the performance, availability, and security of the web infrastructure in real-time. It helps detect and troubleshoot issues, optimize resource usage, and ensure compliance with service level agreements (SLAs).

- **Data Collection:** Monitoring clients collect various types of data, including system metrics (CPU, memory, disk usage), application logs, network traffic, and security events. This data is aggregated and analyzed by the monitoring tool to provide insights into the health and performance of the infrastructure.

- **Monitoring Web Server QPS (Queries per Second):** To monitor web server QPS, you can configure the monitoring tool to collect and analyze HTTP request logs from the web servers. By tracking the number of requests received per second, you can monitor server load, identify traffic patterns, and troubleshoot performance issues.

**Issues:**

- **SSL Termination at Load Balancer Level:** Terminating SSL at the load balancer level exposes decrypted traffic within the internal network, potentially compromising data security if the internal network is breached. It also adds processing overhead on the load balancer.

- **Single MySQL Server Capable of Accepting Writes:** Having only one MySQL server capable of accepting write operations introduces a single point of failure. If the Primary server fails, write operations will be unavailable until failover occurs.

- **Uniformity in Server Components:** Deploying servers with identical components (database, web server, application server) across the infrastructure increases vulnerability to widespread failures. If a common component experiences issues, it may affect multiple servers simultaneously, leading to service disruptions.

----------

<p align="center">
    <img [3. Scale up] src="https://github.com/amandinekemp/holbertonschool-system_engineering-devops/blob/main/web_infrastructure_design/3-scale_up.png">
</p>

----------

# <p align="center">3. Scale up</p>

----------

**Scale Up Infrastructure**

1. **Application Server vs. Web Server:**
   
   - **Web Server:**
     A web server is responsible for serving static content and handling incoming HTTP requests from clients (such as web browsers). It responds to requests by returning static HTML files, images, CSS, JavaScript, etc. Nginx or Apache are commonly used web servers.

   - **Application Server:**
     An application server hosts and executes the application code, handling dynamic content generation and processing. It is responsible for executing server-side scripts, interacting with databases, and generating dynamic web pages. Examples include servers running PHP, Python, Ruby on Rails, etc.

2. **Infrastructure Setup:**

   - **Server:**
     One additional server is added to the infrastructure to accommodate the separation of components and facilitate scaling.

   - **Load Balancer (HAproxy):**
     HAproxy is configured as a cluster with another load balancer to ensure high availability and scalability. It distributes incoming traffic across multiple web servers and application servers, improving performance and reliability.

   - **Split Components:**
     Each component (web server, application server, database) is hosted on its own dedicated server to isolate resources and improve scalability, fault tolerance, and performance.

**Specifics:**

- **Additional Server:**
  Adding an extra server allows for better resource allocation and scalability. It enables the distribution of workload across multiple servers, preventing bottlenecks and ensuring high availability.

- **Load Balancer (HAproxy):**
  Configuring HAproxy as a cluster with another load balancer enhances reliability by providing redundancy. If one load balancer fails, the other can seamlessly take over, ensuring uninterrupted service availability.

- **Split Components:**
  Separating components onto dedicated servers allows for more efficient resource management and scalability. It prevents resource contention between components and facilitates independent scaling of each component based on demand.

**Explanation:**

- **Web Server and Application Server Separation:**
  Separating the web server and application server allows for better resource utilization and scalability. It enables the optimization of each server type for its specific workload, improving overall performance and reliability.

- **Load Balancer Cluster:**
  Configuring HAproxy as a cluster ensures high availability and fault tolerance. It prevents a single point of failure by distributing incoming traffic across multiple load balancers, reducing the risk of downtime and ensuring continuous service availability.

**Conclusion:**

By splitting components onto dedicated servers and configuring HAproxy as a cluster, the infrastructure achieves improved scalability, fault tolerance, and performance. This setup allows for efficient resource management and ensures high availability even during peak demand periods.

----------

## ➤ Author:

- Amandine KEMP
