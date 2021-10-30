# Project 5 Rubric

/ 24

## CloudFormation template ( / 10)

Note: 1 pt per bullet

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

## README.md documentation for configuration ( / 14)

1. Create an `/etc/hosts` file on each system that correlates hostnames to private IPs  
   Description on how file is configured ( / 1)
2. Document how to SSH in between the systems utilizing their private IPs. ( / 1)
3. **_HAProxy configuration & documentation requirements_** ( / 5)
   - How to install package
     - Yes, your template should preinstall the package. Write it again for your documentation
   - What file(s) where modified & their location
   - What configuration(s) were set (if any)
   - How to restart the service after a configuration change
   - Resources used (websites)
4. **_Webserver 1 & 2 configuration & documentation requirements_** ( / 5)
   - How to install package
     - Yes, your template should preinstall the package. Write it again for your documentation
   - What file(s) where modified & their location
   - What configuration(s) were set (if any)
   - How to restart the service after a configuration change
   - Resources used (websites)
5. From the browser, when connecting to the proxy server, take two screenshots. ( / 2)
   - one screenshot that shows content from "server 1"
   - one screenshot that shows content from "server 2"
