# Weekly Outline for CEG 3120

## Week 1 & 2 (8/23 & 8/30)
- syllabus
- create aws stack (maybe too soon, future note?)
- terminal command reminder
- users
- permissions
- ssh keys
- git command basics
    - clone
    - init
    - add
    - commit
    - push
- Project 1 
    - host git repo on AWS instance
        - create user to see user@
        - understand structure after :
        - public key in authorized_keys
    - clone to local system
        - SSH private key exists locally
        - investigate ~/.ssh/config

## Week 3 (9/6)
- Note: this was two days for Fall due to holiday
- Project 1 review
- git extras
    - .gitignore
    - pull
    - merge conflicts
    - branching
    - Pull Requests

## Week 4 (9/13)
- git stuff
    - Pull Requests in action
    - removing files from tracking
    - GitHub handling secrets
- crash course python notes
- APIs
    - structure of a syncronous API
    - Discord Bot and asyncronous APIs
    - Requesting and using OAuth keys
- understanding system environment variables
    - PATH
- exploring running processes attached to the terminal
- Project 2
    - build a Discord bot
    - make a branch for changes to bot responses
    - explore ways to detach from terminal

- TODO: bump Project 2 to 24th?

## Week 5 (9/20? - 10/24)
- Project 2 review
- review of networking terminology
    - needs improvement
- intro to navigating AWS
    - EC2 instance types
    - images / AMI
    - networking (VPC, subnet, security group)
    - firewalls
- intro to contents of a CloudFormation Template
- Project 3
    - Manually creating the resources of a stack
    - ~~Creating a CloudFormation template~~
    - October 4th?

## Midterm week (10/11)
- one class day this week
- Midterm review 10/13
- Midterm - Friday October 15th

## X (10/18)
- Midterm review, reminder overview of CF templates
- messing with a webserver
    - apache vs nginx
    - status / control of services (systemctl)
    - service logs (apache & ssh)
    - HTTPS vs HTTP and notes on certificates
    - security groups
    - iptables? system level firewalls
    - nmap -p 1-5000 server
- load balancing and fault tolerance
    - HAproxy configurations
    - keeping backend servers private - when are public IPs needed?
    - fault tolerance of non-responsive backends

- monitoring
    - Networked systems (Grafana?)
    - cloud costs and usage

## X (10/25)

## X (11/1)
- Directory service & relational database concepts and usage
    - host db on a system?  the books API example?

## X (11/8)

## X (11/15)
- scalability
    - containers

## X (11/22)
- Note: one class day this week
- continuous development and integration
    - GitHub actions
    - docker hub
    - GitHub webhooks?

## X (11/29)

## Finals Week (12/6)

Course Learning Objectives:
1.	Understanding of what can be accomplished be using modern language features and software development practices to develop a distributed information technology system
2.	Understanding of networking roles in a distributed information technology infrastructure
3.	Use of and application of modern software development tools and methodologies and part of a team
4.	Distributed architecture and fault tolerance concepts
5.	Application programming interface design and usage
6.	Directory and relational database concepts and integration
7.	Introduction to cloud systems and modern deployment techniques
8.	Introduction to continuous development and continuous integration
Course Outline:
1.	Using the command line interface & scripting
2.	~~Networking (private vs public accessibility, sockets & ports, SSH keys)~~
3.	Understanding logs, usage of configuration files, process control
4.	~~Development tools (version management, team organization)~~
5.	Cloud infrastructure & Infrastructure as a Service (IaaS)
6.	~~Utilizing Application Programming Interfaces (APIs) & Service Oriented Architecture (SOA)~~
7.	Directory service & relational database concepts and usage
8.	Continuous integration & automating change management
9.	Continuous deployment & automating production
10.	Distributed architecture
11.	Infrastructure as Code (IaC)
12.	Fault tolerance & health monitoring
13.	Introduction to scalability, cost, and maintenance considerations


