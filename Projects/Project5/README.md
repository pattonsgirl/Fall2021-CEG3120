# Project 5 - ALMOST READY

- [Objectives](#Objectives)
- [Project Description](#Project-Description)
  - [Provided Resources](#Provided-Resources)
- [Part 1 - Cloud Formation Template TODOs](#Part-1---Cloud-Formation-Template-TODOs)
- [Part 2 - Setup Load Balancing TODOs](#Part-2---Setup-Load-Balancing-TODOs)
- [Resources and Warnings](#Resources-and-Warnings)
- [Submission](#Submission)
- [Rubric](Rubric.md)

## Objectives:

- Modify the CF template to meet updated requirements
- Run a website of choice using nginx or apache2
- Configure the HAProxy load balancer to direct traffic to two backend systems

## Project Description

In your repository, create a `Project5` folder.

For this project, you will be creating resources to use for a load balancing setup. This project will  
keep things simple - you will have one server accessible from the world. You will have two more servers  
that are accessible only within your VPC.

As mentioned in class, you are welcome to use your own website for this project. **However** in order to  
visually check that load balancing is working, you will need to include screenshots that show different content  
fetched from each server. If you look at the `html` files provided, which you are welcome to use, you'll  
see that one has text that is is from server 1 and the other text that it is from server 2.

### Provided Resources

The following is provided in this project folder:

- [cf-template.yml](cf-template.yml)
  - Note: this templated is updated from previous versions to get you started on this project
- [index.srv1.html](index.serv1.html)
  - Note: you can use your own webpage, but for this project you'll need the files to be "different"  
    so that you can tell the content is coming from a different server
- [index.serv2.html](index.serv2.html)

## Part 1 - CloudFormation Template TODOs

The CloudFormation template provided in this project folder is updated to get you started on this project.

All said and done, your template should do the following:

1. Modify the Security Group to have the following additional rules:
   - Access HTTP from any IP address
   - Access HTTP from within the VPC
2. Create 3 instances
3. One instance configured such that:
   - it gets an elastic ip address
   - it gets a unique private IP
   - haproxy is installed
   - the hostname is changed and unique to the system
4. Two additional instances configured such that:
   - each gets a unique private IP
   - webserver of choice is installed
   - the hostname changed and unique for each system

The deliverable for this part is the CloudFormation template included in your repo folder.

## Part 2 - Setup Load Balancing TODOs

Setup the following and add documentation or screenshots to your `README.md` file as specified.

1. Document how to SSH in between the systems utilizing their private IPs.
2. Create an `/etc/hosts` file on each system that correlates hostnames to private IPs
3. On the instance with a public ip address (which we will refer to as the proxy server), configure  
   haproxy to use the two webservers as content providers (servers that hold website content)
4. On each webserver, configure them to have a "unique" page.
5. From the browser, when connecting to the proxy server, take two screenshots.
   - one screenshot that shows content from "server 1"
   - one screenshot that shows content from "server 2"

## Resources and Warnings

- Note: feel free to share additional resources over in Discord. I'll be updating this if I see you guys sharing something useful
- [An Introduction to HAProxy and Load Balancing Concepts](https://www.digitalocean.com/community/tutorials/an-introduction-to-haproxy-and-load-balancing-concepts)
- [The Four Essential Sections of an HAProxy Configuration](https://www.haproxy.com/blog/the-four-essential-sections-of-an-haproxy-configuration/)
- [How to Install the Apache Web Server on Ubuntu 20.04](https://www.digitalocean.com/community/tutorials/how-to-install-the-apache-web-server-on-ubuntu-20-04)
- [How to Install Nginx on Ubuntu 20.04](https://www.digitalocean.com/community/tutorials/how-to-install-nginx-on-ubuntu-20-04)
- You **DO NOT** need to mess with UFW rules. You may lock yourself out of SSH access.
- You can have a maximum of **FIVE Elastic IP Addresses and FIVE VPCs**
- To manage resources & keep costs down, you will need to delete your CloudFormation stack in between build & test

## Submission

1. Commit and push your changes to your repository. Verify that these changes show in your course  
   repository, https://github.com/WSU-kduncan/ceg3120-YOURGITHUBNAME

   - Your repo should contain:
   - `YOURLASTNAME-cf.yml`
   - `README.md`

2. In Pilot, paste the link to your project folder.  
   Sample link: https://github.com/WSU-kduncan/ceg3120-YOURGITHUBUSERNAME/blob/main/Projects/Project5
