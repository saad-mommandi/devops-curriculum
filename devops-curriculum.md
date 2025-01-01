# Programming

A DevOps engineer should be able to understand other people's code and occasionally write code. If you're starting from scratch, it can be a bit intimidating since there's a lot of different concepts involved. 

You should understand:
- The basics of the Object-Oriented Programming (OOP) paradigm
- The syntax of a programming language
- APIs
- Basic web application structures with Create, Read, Update, Delete (CRUD) features

Learning all this from scratch is not a trivial task. It does need some legwork and you need to develop a foundation or else learning it piecemeal will be unnecessarily complicated. 

## Learning Approach

**Recommended resource:**  
[Python and Flask Bootcamp](https://flexential.udemy.com/course/python-and-flask-bootcamp-create-websites-using-flask/)

This course touches on all four points above. It's about 20 hours long, but it *doesn't* need to be completed before beginning the actual DevOps portion of the syllabus. 

I recommend a pace of 2-3 hours a week of video—assuming that studying the material and really learning it (not just copy-pasting what the instructor does) will take an extra 2-3 hours a week. This is roughly the equivalent of a single college course in terms of effort. 

**Other resources:**  
[Python Official Documentation](https://docs.python.org/3/tutorial/index.html)  
The Python documentation is dry but it's a great resource if you have any questions about language features. Use this as a reference if you run into code you don't understand.

**Note:** You do not need to complete this before moving on to the next sections.

---

# What is DevOps

If you watch some YouTube videos, you'll quickly realize that you'll get as many different definitions of what DevOps is as videos you watch. I'll keep it simple: **DevOps is really about one thing—Increasing an organization's ability to deliver applications smoothly and quickly.**

There are a few key domains that really define modern-day DevOps. Learning each of these distinct domains will give you the technical skills to succeed in the field.

## Learning Approach

This curriculum is designed to be followed in a progression for each domain:

1. Read through any provided links under each domain.
2. If any tools were mentioned, go through the getting-started tutorials for each tool to lab out their simple examples and understand how they work.
3. **Lab 1:** Work on the independent lab exercise.
4. **Lab 2:** Integrate that lab work into the Python application you're building.

**Note on the labs:**  
Many labs you'll find online are really exercises in following instructions, and they leave the user with very little to no understanding of what they just did. To mitigate that, the labs below are formatted differently. Instead of step-by-step instructions, you'll be given two things:
1. **How your end product should look**  
2. **A list of hints** for concepts or technologies you might have to read up on.

The idea is to force you to do the work and figure it out partially by yourself. In my experience, this is one of the best ways to learn something.

---

# DevOps Domains

## Intermezzo: Cloud Services

**Note on intermezzos:**  
Intermezzos are sprinkled throughout this section covering necessary technologies to understand that don't quite qualify as an actual DevOps domain. Rather, they're the required foundational knowledge needed. 

**Why It Matters**
- **Scalability:** Cloud platforms allow you to dynamically scale based on demand.
- **Flexibility:** Cloud services offer a wide range of tools for compute, storage, networking, and more.
- **Cost Efficiency:** Pay-as-you-go models allow businesses to pay only for what they use, avoiding large upfront investments.

### The Tools

- **Amazon Web Services (AWS):** The most widely adopted cloud platform.
- **Microsoft Azure:** A strong contender for enterprise cloud solutions.
- **Google Cloud Platform (GCP):** Known for data analytics and AI/ML services.

### Key Concepts to Understand

1. **Compute Services:**
    - Virtual machines (e.g., AWS EC2, Azure Virtual Machines).
2. **Networking:**
    - Virtual Private Cloud (VPC).
    - Security Groups.
3. **Storage:**
    - File storage (e.g., AWS EFS).

### Lab Work: Deploy a Web Server on AWS

**Goal:** Use AWS to provision a virtual machine (EC2) and host a static web page, making it accessible from the internet.

**End State:**  
You will have an EC2 instance with a running web server (e.g., Apache or Nginx). The web server will serve a static HTML page, accessible via a public IP address or DNS.

**Hints:**
- Familiarize yourself with the AWS console and EC2 instance creation.
- Research and configure security groups to allow HTTP traffic.
- Use SSH to access your instance and install a web server.
- Deploy a basic HTML file to the web server’s document root.

### Lab Work: Deploy a Web Application on AWS (Part 2)

**Goal:** Extend your previous lab to deploy your Python-based application from the programming course on AWS.

**End State:**  
Your EC2 instance will run your Python application, accessible via a public URL. At this point in the programming course, this might be a simple "hello world" page served by Flask. 

**Hints:**
- Install Python and required dependencies on your EC2 instance.
- Use your Flask app from the programming course as the application to deploy.
- Research how to configure Nginx as a reverse proxy to forward traffic to your Flask app.

## Infrastructure Automation

Infrastructure automation is the process of using code or configuration files to manage infrastructure instead of manually configuring resources. This practice is called **Infrastructure as Code (IaC)**.

### Why It Matters

- **Consistency:** Reduces human error by automating repetitive tasks.
- **Version Control:** Infrastructure configurations are stored in code, which can be tracked, reviewed, and rolled back like application code. This prevents **configuration drift**.
- **Scalability:** Quickly provision or update resources to meet growing demands.
- **Speed:** Automating infrastructure provisioning significantly reduces setup time for new environments.

### The Tools

- **Terraform:**  
  A popular IaC tool that allows you to define infrastructure components like servers, load balancers, and networking configurations in files. Terraform integrates with multiple cloud providers and is the industry leader for IaC solutions.
    
- **Ansible:**  
  A configuration management and automation tool. While Terraform focuses on provisioning infrastructure, Ansible is used to configure and manage existing systems. For example, Terraform might create a virtual machine, while Ansible ensures that VM has the necessary software, scheduled tasks, and configurations.

### Key Concepts to Understand

1. **Declarative vs. Imperative Approaches**
   - **Declarative (e.g., Terraform):** Describe the desired state, and the tool figures out how to achieve it.
   - **Imperative (e.g., traditional scripts):** Specify every step needed to reach the desired state.

2. **Idempotency**
   - Applying the same configuration multiple times results in the same outcome, ensuring predictable results.

3. **Infrastructure Life Cycle Management**
   - **Provisioning:** Creating infrastructure resources.
   - **Configuration:** Setting up software, networking, and system settings.
   - **Destruction:** Deleting resources when no longer needed.

---

### Lab Work: Provision an EC2 Instance Using Terraform

**Goal:** Create a Terraform configuration to provision an EC2 instance on AWS.

**End State:**  
You will have an EC2 instance running on AWS, accessible via SSH. The instance can be created and destroyed using Terraform commands.

**Hints:**

- Familiarize yourself with Terraform syntax and providers.
- Research how to define AWS services like EC2, VPC, and Security Groups with Terraform.
- Test your configuration using Terraform commands (`init`, `plan`, and `apply`).

---

### Lab Work: Configure the EC2 Instance Using Ansible

**Goal:** Use Ansible to install and configure a web server on the EC2 instance provisioned in the previous lab.

**End State:**  
The EC2 instance will run a web server (e.g., Nginx), serving a basic HTML page. Configuration is fully automated using an Ansible playbook.

**Hints:**

- Learn how to create an Ansible inventory file for managing your instance.
- Write a playbook to install Nginx and copy an HTML file to the server’s document root.
- Test the playbook by running it against your EC2 instance.

---

### Lab Work: Deploy Your Flask Application Using Terraform and Ansible

**Goal:** Use Terraform to provision the infrastructure for your Flask application and Ansible to configure the EC2 instance to run your Flask app. The application should be accessible via a public URL.

**End State:**  
You will have an EC2 instance provisioned by Terraform and configured by Ansible to serve your Flask application. The app should be running behind a web server (e.g., Nginx) acting as a reverse proxy and accessible from the internet.

**Hints:**

- Extend your Terraform configuration to include:
  - Security groups to allow HTTP/HTTPS traffic.
  - An Elastic IP to provide a consistent public endpoint.
- Create an Ansible playbook that:
  - Installs Python, Flask, and required dependencies.
  - Sets up Nginx as a reverse proxy to forward requests to the Flask app.
  - Deploys your Flask application files to the server.
- Familiarize yourself with how to run Flask applications in production (e.g., using Gunicorn).

---

## Intermezzo: Version Control

Version control is an essential tool for many modern DevOps practices. It enables collaboration, tracking changes, and maintaining code history. It is the backbone of modern software development and deployment workflows, and since we're focusing on improving development and deployment, it's part and parcel of the job.

### Why It Matters

- **Collaboration:** Multiple people can work on the same codebase without overwriting each other’s changes.
- **Change Tracking:** Easily track who made what changes, when, and why.
- **Rollback:** Quickly revert to previous versions of code if issues arise.
- **Integration:** Essential for CI/CD pipelines and automated deployments.

### The Tool: Git and GitHub

- **Git:**  
  A distributed version control system that allows you to manage your codebase locally and synchronize it with remote repositories.

- **GitHub:**  
  A popular platform for hosting Git repositories, enabling collaboration, issue tracking, and project management.

### Key Concepts to Understand

1. **Repositories:** Where your code and history are stored. These can be local (on your machine) or remote (on GitHub).
2. **Commits:** Snapshots of your codebase at a specific point in time.
3. **Branches:** Parallel versions of your codebase for isolated development (e.g., feature branches).
4. **Pull Requests:** A mechanism to propose and review changes before merging them into the main branch.
5. **Merging:** Integrating changes from one branch into another.

---

### Lab Work: Set Up a GitHub Repository and Commit Code

**Goal:** Create a GitHub repository for your Python Flask project and practice using Git commands to manage and push code to the repository.

**End State:**  
You will have a GitHub repository containing your Flask project. The repository will include meaningful commit messages and a structured history of changes.

**Hints:**

- Install Git on your machine and configure it with your GitHub credentials.
- Useful Git commands:
  - `git init`: Initialize a local repository.
  - `git add`: Stage changes for commit.
  - `git commit`: Save changes locally with a message.
  - `git push`: Push changes to the remote GitHub repository.
- Explore the GitHub interface for creating repositories, cloning, and viewing commit history.

**Note:** From this point forward, as you continue developing your Python Flask application, keep track of your code in a GitHub repository.

## CI/CD: Continuous Integration and Continuous Deployment

CI/CD is a cornerstone of modern DevOps. It enables teams to build, test, and deploy applications in an automated fashion. By automating workflows, CI/CD reduces the time between writing code and serving it to end-users.

### Why It Matters

- **Automation:** CI/CD automates repetitive tasks like testing, building, and deploying code, freeing up time for developers to focus on the product.
- **Speed:** Accelerates the software delivery process by integrating, testing, and deploying changes quickly.
- **Quality Assurance:** Automated tests and consistent deployment pipelines reduce bugs and user errors.
- **Collaboration:** Encourages smaller, incremental code changes that are easier to review and integrate.

---

### The Tools

- **GitHub Actions:**  
  A CI/CD solution tightly integrated with GitHub. It allows you to define workflows directly in your repository to automate tasks like testing, building, and deploying your application.

- **Jenkins:**  
  A widely used, open-source CI/CD tool with extensive plugin support. It provides flexibility and control over pipelines, suitable for complex enterprise setups.

- **GitLab CI/CD:**  
  Built into GitLab, it offers an integrated solution for managing pipelines, from code integration to deployment.

- **CircleCI, Travis CI, and Others:**  
  Hosted and managed CI/CD services that simplify setup and maintenance for smaller teams or projects.

---

### Key Concepts to Understand

1. **Continuous Integration (CI):**
   - Automatically tests and validates code changes whenever new commits are pushed to the repository.
   - Ensures early detection of issues, reducing integration headaches.

2. **Continuous Deployment (CD):**
   - Automatically deploys validated changes to production or staging environments.
   - Reduces manual intervention and minimizes the risk of human error.

3. **Workflows and Pipelines:**
   - Define sequences of automated steps (e.g., build, test, deploy) that execute whenever a trigger event occurs, such as a new commit or pull request.

4. **Triggers:**
   - Events like code pushes, pull requests, or scheduled intervals that initiate workflows.

---

### Lab Work: Set Up CI/CD with GitHub Actions

**Goal:** Automate testing and deployment of your Python Flask application using GitHub Actions.

**End State:**  
Your repository will have a GitHub Actions workflow that automatically:

- Runs tests for your Flask app when new code is pushed.
- Deploys the app to your provisioned EC2 instance (from previous labs) after passing tests.

**Hints:**

- Learn how to write a `.github/workflows/ci.yml` file to define your CI/CD pipeline.
- Define steps to:
  - Set up Python and install dependencies.
  - Run tests using a test framework like `pytest`.
  - Deploy the application (e.g., using SSH or Ansible commands).
- Explore GitHub Actions’ marketplace for reusable actions like setting up Python or deploying to AWS.

---

### Lab Work: Explore Jenkins as a CI/CD Alternative

**Goal:** Set up a Jenkins server to automate the same CI/CD pipeline as in the GitHub Actions lab.

**End State:**  
You will have a Jenkins pipeline that:

- Pulls the latest code from your repository.
- Runs tests and builds the Flask application.
- Deploys it to the same EC2 instance.

**Hints:**

- Install and configure Jenkins on a local VM or cloud instance.
- Use Jenkins’ Pipeline as Code feature to define your workflow in a `Jenkinsfile`.
- Explore Jenkins plugins for Git integration, Python setup, and SSH deployments.

---

By completing these labs, you’ll gain practical experience with CI/CD using GitHub Actions and Jenkins. While GitHub Actions provides simplicity and tight integration with GitHub, Jenkins offers flexibility.

---

## Containers and Microservices

Containers and microservices are essential in modern software development and deployment. Containers provide a consistent, portable environment for applications. Microservices architecture enables building scalable and modular applications by decomposing them into smaller, loosely coupled services.

### Why It Matters

- **Portability:** Containers allow applications to run consistently across different environments, reducing compatibility issues.
- **Scalability:** Microservices enable independent scaling of components. Scale up during traffic surges and scale down during off-peak periods to save costs.
- **Resilience:** Microservices improve fault tolerance by isolating failures to specific services. Containers can be rebuilt quickly without server reconfiguration.

---

### The Tools

- **Docker:** A leading containerization platform that packages applications and their dependencies together.
- **Kubernetes:** A container orchestration platform that automates deployment, scaling, and management of containerized applications.
- **Docker Compose:** A tool for defining and running multi-container Docker applications using a YAML file. Kubernetes can be complex, so Docker Compose is a good starting point.

---

### Key Concepts to Understand

1. **Containerization:**
   - Containers package an application along with its dependencies, ensuring consistency regardless of the underlying infrastructure.

2. **Docker Images:**
   - Immutable templates used to create containers. Think of them as snapshots of an application.

3. **Microservices Architecture:**
   - Decomposing applications into smaller, independently deployable services that communicate via APIs.

4. **Container Orchestration:**
   - Managing multiple containers in production environments, ensuring reliability and scalability.

5. **Networking in Containers:**
   - Understanding how containers communicate within and across hosts.

---

### Lab Work

#### Lab 1: Set Up a Docker Container to Serve a Web Page

**Goal:** Create and run a Docker container that serves a static web page.

**End State:**  
A Docker container running a web server (e.g., Nginx or Apache) serves a static HTML page, accessible via localhost.

**Hints:**

- Learn how to create a `Dockerfile` to define the container image.
- Use an official web server image (e.g., `nginx`) as the base.
- Place an HTML file in the appropriate directory in the container.
- Use Docker CLI commands (`docker build`, `docker run`, etc.) to build and run the container.

---

#### Lab 2: Containerize Your Python Flask Application

**Goal:** Package your Python Flask application into a Docker container.

**End State:**  
A Docker container running your Flask application, accessible via a public endpoint or localhost.

**Hints:**

- Extend the `Dockerfile` to:
  - Use a Python base image.
  - Copy your Flask application files into the container.
  - Install dependencies using `pip`.
  - Define a command to run the Flask application.
- Research Docker Compose to manage environment variables and networking if your app has multiple components (e.g., a database).

---

By completing these labs, you will gain hands-on experience with containerization and understand how to apply it to real-world applications. Containers and microservices serve as the foundation for more advanced topics like orchestration and scaling.

## Monitoring and Logging

Monitoring and logging are a core part of ensuring system issues can be detected and resolved quickly. Proper monitoring provides developers with insights into system performance, health, and resource usage, while logging captures detailed records of application and system behavior. Both are critical to quick development and form part of a robust DevOps solution.

---

### Why It Matters

- **Proactive Problem Solving:** Monitoring helps identify and resolve issues before they affect users.
- **Troubleshooting:** Logs provide detailed records to debug and understand unexpected behavior.
- **Automation:** Alerts enable automated responses to specific conditions, reducing downtime.

---

### The Tools

- **Prometheus:** A powerful open-source monitoring system.
- **Alertmanager:** Part of the Prometheus ecosystem. It handles alerts, routes them, and sends notifications.
- **Grafana:** A visualization tool that integrates with Prometheus to create dashboards and graphs.
- **Docker Compose:** A Docker tool that allows the combination of Prometheus, Alertmanager, and Grafana with your applications, enabling deployment of groups of containers together.

---

### Key Concepts to Understand

1. **Metrics:** Quantifiable data points representing performance (e.g., CPU usage, request latency).
2. **Alerts:** Notifications triggered when specific thresholds are crossed or conditions are met.
3. **Dashboards:** Visual representations of metrics for quick understanding of system health.

---

### Lab 1: Monitor a Test Web Server Using Prometheus, Alertmanager, and Grafana

**Goal:** Set up the Prometheus stack in Docker to monitor a basic web server and display metrics on a Grafana dashboard.

**End State:**  
You will have a monitoring system running in Docker, tracking metrics like request count and response time for a web server, with an alert triggered for high latency.

**Hints:**

1. **Set Up the Stack:**
   - Use Docker Compose with the [prometheus-community/docker-compose-stack](https://github.com/prometheus-community/docker-compose).

2. **Deploy a Web Server:**
   - Spin up a simple web server (e.g., using Nginx or Python’s `http.server`) alongside the Prometheus stack.

3. **Use an Exporter:**
   - Use [blackbox_exporter](https://github.com/prometheus/blackbox_exporter) for HTTP checks.

4. **Create Dashboards:**
   - Use Grafana to create dashboards visualizing response time, request count, and uptime.

5. **Set Up Alerts:**
   - Define alerting rules in Prometheus for conditions like response latency >500ms.
   - Configure Alertmanager to send notifications when alerts are triggered.

---

### Lab 2: Monitor Your Flask Application

**Goal:** Extend the monitoring stack to collect and visualize metrics from your Flask application, including custom application-specific metrics.

**End State:**  
Your monitoring stack will track metrics for your Flask application, including request count, response time, and custom business metrics. Alerts will notify you of issues like high error rates.

**Hints:**

1. **Instrument Your Flask App:**
   - Use the [Prometheus client library for Python](https://github.com/prometheus/client_python) to instrument your Flask app.
   - Add a `/metrics` endpoint to expose metrics.

2. **Define Custom Metrics:**
   - Track metrics like total requests (`Counter`), response latency (`Histogram`), and application-specific metrics (e.g., failed login attempts).

3. **Update Prometheus Configuration:**
   - Configure Prometheus to scrape metrics from your Flask app’s `/metrics` endpoint.

4. **Enhance Dashboards:**
   - Update Grafana dashboards to include Flask-specific metrics and trends over time.

5. **Set Up Alerts:**
   - Create alerts for conditions like:
     - Response latency >1s.
     - Error rates exceeding a certain threshold.

---

## Where To Go From Here

If you've completed all the labs, you're equipped with the basic knowledge and tools needed to succeed in the field. Where you go from here depends on your interests and career goals. Here are some suggestions:

- **Learn Kubernetes:** Container orchestration with Kubernetes is an in-demand skill. Start with labs to deploy applications and manage scaling, networking, and storage.
- **Explore Advanced CI/CD:** Expand your pipelines with security scans, automated rollbacks, or blue-green deployments.
- **Improve Observability:** Learn tools like the ELK stack (Elasticsearch, Logstash, Kibana) or explore distributed tracing with tools like Jaeger or OpenTelemetry.
- **Certifications:** Consider certifications like Kubernetes CKA, AWS DevOps Professional, or HashiCorp Terraform Associate to validate your skills.

The DevOps field is vast—keep exploring and building to stay ahead!
