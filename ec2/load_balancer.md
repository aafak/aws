A load balancer in AWS is a service that distributes incoming network traffic across multiple targets,
such as EC2 instances, containers, IP addresses, or Lambda functions, to ensure high availability and
reliability of applications.

AWS provides different types of load balancers under the Elastic Load Balancing (ELB) service to handle
various use cases and application needs.

Types of AWS Load Balancers
AWS offers three main types of load balancers:

**Application Load Balancer (ALB):**
Operates at the Application Layer (Layer 7) of the OSI model.
Best suited for HTTP and HTTPS traffic.
Supports advanced routing, such as host-based and path-based routing.
Allows you to route traffic to different microservices or applications based on URL paths or hostnames.
Ideal for modern architectures, including microservices and containerized applications.

**Network Load Balancer (NLB):**
Operates at the Transport Layer (Layer 4).
Designed for handling TCP and UDP traffic with very high performance.
Capable of managing millions of requests per second with ultra-low latencies.
Suitable for high-throughput, low-latency applications, such as gaming or real-time data processing.

**Gateway Load Balancer (GWLB):**
Operates at Layer 3.
Used to route and inspect traffic flows, making it ideal for integrating third-party network virtual appliances, such as firewalls and monitoring solutions.
Routes and scales appliance traffic efficiently.

**Key Features of AWS Load Balancers**
Automatic Scaling: ELB can scale its capacity automatically based on incoming traffic, ensuring that applications remain available.
Health Checks: Continuously monitors the health of registered targets to ensure traffic is only routed to healthy targets.

Security Integration: Integrates with AWS Identity and Access Management (IAM), Amazon VPC, and security groups, allowing you to control network access to your applications.
SSL Termination: ALB and NLB support SSL/TLS termination to offload the SSL workload from your application instances.
Use Cases for AWS Load Balancers

High Availability: By distributing traffic across multiple instances, load balancers help prevent downtime during maintenance or failure of instances.
Scalability: Load balancers facilitate handling increased traffic by distributing load across instances that automatically scale based on demand.

Microservices Architecture: ALBs are often used for applications following microservices architecture, where different paths/routes serve different services.
Secure and Efficient Traffic Handling: NLBs are often used for applications that require high-speed, low-latency connections, like gaming servers or financial applications.
