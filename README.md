# AWS & Docker — Applied Cloud Computing

Hands-on cloud engineering portfolio built on AWS and Docker, covering microservices
architecture, containerization, serverless computing, cloud-hosted databases, and
infrastructure deployment. Every project was deployed and verified on live cloud
infrastructure and local container environments.

## Projects

### 1. E-Commerce Microservices — Docker Compose & Polyglot Persistence
Built and orchestrated a fully containerized e-commerce backend with three independent
microservices — User, Product, and Order — communicating via REST APIs, managed
collectively with Docker Compose across 6 running containers.

- Implemented **polyglot persistence**: PostgreSQL for transactional User and Order
  services (structured, relational data with strict consistency) and MongoDB for the
  Product service (flexible, document-oriented data)
- Verified inter-service communication via `curl` REST calls and inspected live
  container logs using `docker logs`
- Queried both PostgreSQL databases directly using `psql` inside running containers
  and MongoDB collections using `mongosh`
- Managed full container lifecycle: build, orchestrate, inspect, tear down

`Docker` · `Docker Compose` · `Flask` · `Node.js` · `PostgreSQL` · `MongoDB` · `REST APIs`

---

### 2. Docker Images & Compose — Custom Builds, Jenkins, Flask App
Progressed from writing basic Dockerfiles to building and running production-style
containerized applications, with hands-on CI/CD tooling exposure.

- Built custom Docker images iteratively using Alpine Linux — from a hard-coded echo
  command to executing shell scripts to running interactive processes as PID 1
- Containerized a Flask Python web application with `requirements.txt`, port mapping,
  and a multi-page interactive UI served from within the container
- Deployed a Jenkins CI/CD server as a Docker container, configured plugins, and
  created an admin account via the web UI
- Deployed WordPress + MySQL as a multi-container stack using Docker Compose with
  persistent volume mounts and environment variable configuration

`Docker` · `Dockerfile` · `Docker Compose` · `Flask` · `Python` · `Jenkins` · `MySQL` · `YAML`

---

### 3. EC2 + RDS — Cloud Database Integration
Deployed a cloud-hosted relational database on AWS RDS and connected it to an EC2
web server to serve dynamic data through a Flask application.

- Architected two-tier security group setup (`sgWEB` + `sgRDS`) to enforce network
  isolation — RDS only accepts inbound connections from the web security group on
  port 3306
- Provisioned a MySQL RDS instance (`db.t3.micro`) and connected to it from EC2
  using the MySQL CLI via endpoint URL
- Created database schema, inserted data, and ran queries using a `.sql` script
  executed directly against the RDS instance
- Integrated RDS data retrieval into Flask's `server.py` using `PyMySQL`, rendering
  Titanic dataset records dynamically in an HTML table via Jinja2 templates

`AWS RDS` · `MySQL` · `EC2` · `Flask` · `Python` · `PyMySQL` · `Jinja2` · `Security Groups`

---

### 4. AWS S3, Lambda & Serverless — Event-Driven Architecture
Built and invoked serverless functions using AWS Lambda and configured S3 as both
a static web host and an event trigger for automated workflows.

- Provisioned and managed S3 buckets using the AWS CLI — created, listed, uploaded
  objects, and force-deleted non-empty buckets
- Hosted a static website on S3 with public access bucket policy configured via
  AWS Policy Generator (IAM JSON)
- Created and invoked a `helloworld` Lambda function via AWS CLI, verified
  `response.json` output and monitored execution logs in CloudWatch
- Built an event-driven Lambda function (`listen_to_s3_new_object`) triggered
  automatically on S3 object creation — verified trigger timing and filename capture
  in CloudWatch log streams

`AWS Lambda` · `Amazon S3` · `AWS CLI` · `CloudWatch` · `IAM` · `Serverless` · `Event-Driven Architecture`

---

### 5. EC2 + Elastic Load Balancer — Scalable Web Architecture
Deployed a horizontally scalable Flask web application across two EC2 instances behind
an Application Load Balancer, demonstrating high-availability infrastructure patterns.

- Created a custom AMI from a configured EC2 instance and launched two identical
  instances (`HW1Part2Instance_1` and `HW1Part2Instance_2`) from that image
- Registered both instances into an ELB target group and configured an Application
  Load Balancer with multiple availability zones and security groups
- Verified load distribution by refreshing the ELB DNS URL and observing traffic
  routing alternating between the two instance hostnames
- Implemented dynamic HTML rendering using Flask's Jinja2 template engine to
  display EC2 instance hostname in the served web page

`AWS EC2` · `Elastic Load Balancer` · `AMI` · `Flask` · `Python` · `systemd` · `Jinja2`

---

### 6. Docker Fundamentals & EC2 Basics
Foundational hands-on work with Docker container management and AWS EC2 instance
provisioning, covering core concepts used throughout all other projects.

- Managed Docker container and image lifecycle: pull, run, inspect, stop, remove,
  prune — via both CLI and Docker Desktop UI
- Ran CentOS containers with controlled CPU limits (`--cpus="4"`) and observed
  process-level CPU saturation using `top` across multi-core systems
- Launched an EC2 `t3.micro` instance (Amazon Linux), configured security groups
  for SSH (port 22) and HTTP (port 80), installed Apache (`httpd`), and served a
  static webpage
- Transferred files to EC2 using `scp` with `.pem` key authentication

`Docker` · `AWS EC2` · `Linux` · `Apache` · `SSH` · `Security Groups` · `AMI`

---

## Tech Stack

`AWS EC2` · `AWS RDS` · `AWS S3` · `AWS Lambda` · `CloudWatch` · `IAM` · `ELB` ·
`Docker` · `Docker Compose` · `Flask` · `Python` · `Node.js` · `PostgreSQL` · `MongoDB` ·
`MySQL` · `PyMySQL` · `Jinja2` · `Jenkins` · `REST APIs` · `Linux` · `Bash` · `YAML`

## Concepts Demonstrated

- Microservices architecture and service orchestration
- Polyglot persistence and database selection by access pattern
- Containerization and custom Docker image creation
- Serverless and event-driven architecture
- Cloud-hosted relational databases with network isolation
- Horizontal scaling with load balancing
- CI/CD tooling (Jenkins)
- IAM and security group configuration
- Static and dynamic web hosting on AWS