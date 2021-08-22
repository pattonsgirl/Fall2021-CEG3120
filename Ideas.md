adding text
Discord bot (https://realpython.com/how-to-make-a-discord-bot-python/):

    Project 1:
    Set up an API key, create basic bot to confirm working connection
    Bot challenge: create something unique
        Objective: learn to use an example to craft your own flair

    Project ?:
    Branch to make additions to python code
        Create an error handler, send log somewhere?

Server setup:

    Project 1:
    Use linux system on AWS for hosting git repositories.  Share ssh keys appropriately so authentication occurs over SSH
        Repository URL should be in format git@server_name:/username/repository
        Files to investigate:
        /etc/hosts
        ~/.ssh/config
        ~/.ssh/authorized_keys

Cloud Knowledge base:

    Project 2:
    Manually create a VPC, subnet, and security group.  Add an EC2 instance to the VPC with an Ubuntu AMI.
    Create a cloud formation that automates this process.
        Note: use AMI in template, use specific port list, open to public & "home" ip

    Project 3 (MAKE REPO PUBLIC):
    Cloud formation w/ 3 servers
        1 proxy + install haproxy
        2 webservers + install apache2
    Add config files to git repo, have CF insert them into respective servers

Continuous Integration

    Project 4 (add in to cloud kb):
    Use original linux system on AWS to host website git repo.
    Write a hook that updates to web servers in project 3 when push is made to main branch
        Check security groups, update ssh permissions to allow linux system connection
        Investigate `scp` or `rsync`
