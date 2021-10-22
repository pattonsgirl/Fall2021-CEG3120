# Project 4 Rubric

/ 12

## CloudFormation template submitted ( / 1)

## Modifications required for credit ( / 11)

1. description of template
2. ami replaced to AMI selected in project 3 / ami you are aware of choosing
3. VPC range to 10.0.0.0/16 (or successful use of /24 for extra credit)
4. subnet range to 10.0.0.0/24 (or successful use of /28 for extra credit)
5. security group setting for inbound SSH within VPC
6. security group setting for inbound SSH from home / trusted network(s)
7. security group setting for inbound SSH from WSU
8. instance setting to set "Tag" "Name" to "CF-instance"
9. instance setting to set a private IP in your subnet range
10. instance setting to change the configuration script built into the cf-template to do the following: (2 pts)
    - Install git, python3, pip3
    - Change hostname
