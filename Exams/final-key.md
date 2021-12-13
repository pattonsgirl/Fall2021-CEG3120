# CEG 3120 - Final Exam Fall 2021

## Written Answer

1. Identify 2 load balancing allocation strategies and describe how they distribute traffic among a pool of servers.

- round robin
- weighted round robin
- least connections
- least response time

2. I have a container running an application on port 444. When I run the container, I bind it to the host port 555. When I go to the public IP for the host, 45.23.90.88:555, I get an error instead of my application. Discuss something I should investigate that could be the problem.

   - firewall rules
   - permission to use port 555 on the host
     - something else using it?
   - PEMDAS of ports when container was set to run: -p 555:444 not -p 444:555

3. What is the purpose of GitHub secrets (or any secret manager)? Describe in terms of security.

   - GitHub secrets allows you to encrypt and store any confidential information like passwords and tokens to be used in other ways but cannot be read. This way if someone got ahold of your actions .yml file they would not be able to read your password or token instead they just see the placeholder variable. So this way your actions still work and nothing gets disclosed.

4. Explain the security groups rules given the following definition from a CloudFormation template and determine if the rules apply to inbound or outbound traffic:

```
ExamSecurityGroup:
    Type: 'AWS::EC2::SecurityGroup'
    Properties:
      VpcId: !Ref VPC
      SecurityGroupIngress:
        - IpProtocol: tcp
          FromPort: '-1'
          ToPort: '-1'
          CidrIp: 10.0.0.0/16
        - IpProtocol: tcp
          FromPort: '22'
          ToPort: '22'
          CidrIp: 132.45.21.98/32
        - IpProtocol: tcp
          FromPort: '443'
          ToPort: '443'
          CidrIp: 0.0.0.0/0
```

- SecurityGroupIngress = inbound rules
- Rule 1: all ports on subnet 10.0.0.0/16 (likely the VPC subnet)
- Rule 2: port 22 only from ip 132.45.21.98 (/32 means only this address)
- Rule 3: port 443 from any IP

5. What benefit(s) do workflows (like Github Actions) provide, and why are they such integral tools for modern deployment?

   - Workflows can provide automated building, testing, and deployment of projects. They are integral for modern development because they work faster than a human could, and they can be configured to handle basic stuff or more intricate tasks. Without using a workflow, you're going to fall behind other companies/organizations using one.
   - Modern deployment can involve a lot of different programs. In our class we worked on small scale projects but we were still using AWS, GitHub, and Docker Hub. Workflows like GitHub Actions allow developers to spend more time working on projects in their IDE and less time messing around with uploading their code to other repositories that aren't directly hosted on GitHub.

## Commands - interpret or craft

1. What does the following command do?
   `docker build -t foo .`

   - this will use your Dockerfile that you created which is the instructions for how you want the image to be built, then name the image foo with the period at the end that will reference the current directory that it is in.

2. Command to get the status of the docker service:

   - `sudo systemctl status docker.service`
   - `sudo service docker status`
   - `docker info` works IF docker is installed and running
   - `docker ps` gets info on status of running containers, not of docker running on the system

3. Describe the job in the following workflow:

```
name: exam-workflow
on: [push]
jobs:
  execute:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - run: apt install python3 python3-pip
      - run: pip3 install black
      - run: black my-code.py
```

- Top student answer:
- The job is named execute, and it will be a job for the OS running the latest version of Ubuntu. The job will checkout the repository to the runner, then install python3 and pip3, then it will install `black` for pip3 (I think, although the syntax might need to be `pip install black`), and finally, the job will run `my-code.py` through `black`, a python code formatter.

4. I have a running container that is bound to a port on my host. What steps do I need to take to kill and remove the container so that I can run a fresh container from new image using the same host port?

```
$ sudo docker ps # to get the names of your containers.
$ sudo docker kill <name of container> # to kill the container
  # the exited container will still have a "hold" on the port
$ sudo docker rm <name of container> # to remove it
$ sudo docker run -dit -p 80:80 foo # to start a fresh container
```

## Short Answer

1. Which load balancing configuration option will distribute traffic to a pool based on resource requested, such as "blog" or "shop"? HTTP or TCP

   - HTTP

2. In a github workflow, I need an action that will checkout my repository to the runner. What action would you recommend?

   - action/checkout@v2

3. The command: "docker \_\_ httpd:2.4" will download the httpd:2.4 image from Docker Hub.

   - pull

4. Command that will let me copy a file from one system to another (local to remote):

   - sftp
   - scp
   - push / clone assumes you have a repo set up on both ends - this is not generally true, and you should be aware of other ways to transfer files via command line

## True / False

1. In a load balancing configuration, there can be multiple frontend and backend sections, allowing the creation of multiple pools depending on resource requested.

   - True

2. In order to manipulate content on a repository (push) you need to be authenticated.

   - True.
   - This is true for both github and docker - some form of authentication needs to be provided to do actions

3. Regions in AWS will never go down.

   - False
   - This is a joke because us-east-1 went down. Just because it is in "the cloud" does not promise 100% up time

4. A container image can run on any system configured with a container engine. For example, the images we built on one system with docker installed can run on other systems if the systems have docker installed.

   - True

5. By default, apache configurations look for a default.html file in the default folder.

   - False
   - `index.html` - the "default" folder may vary depending on the configuration

6. /etc/hosts lists public keys that are allowed to connect to my system as the given user.

   - False
   - `authorized_keys` file, usually found in the .ssh folder of the username to authenticate with
