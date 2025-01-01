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

---

# Additional Sections

(Continue formatting the remaining sections using the same structure: **Headings**, **bold for emphasis**, **bullet points**, and **code blocks** where needed.)
