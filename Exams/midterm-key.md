## Written Response

1. For a VPC, I have created a subnet, routing table, and security group.  I created an instance and attached an IP address to it.  But ssh isn't working to the public IP.  What did I miss?
    - The missing part is the internet gateway. This enables communication between the VPC and the internet. 
    - Additionally, check that the route table has a route for traffic using the gateway


2. What is the big deal about an OAuth token being publicly readable (such as existing in a public repository)?
    - if it is publicly readable or exposed, anyone else with the token now also has access to systems associated with that token.
    - it could also be revoked which causes headaches as well - exposed keys need to be renewed and replaced on all systems that were using them

3. Given the following Security Group configuration, describe how the inbound rules are configured and any implications of these rules (access to x is only allowed by a, b, c)
    - port 443 - only from subnet 130.108.0.0/16 (so all IPs that start with 130.108)
    - port 22 - from subnet 123.124.125.24/32 (which means only IP 123.124.125.24)
    - port 22 - from subnet 10.0.0.0/24 (IPs that start with 10.0.0) which likely applies to a VPC or subnet in the VPC
    - port 80 - from 0.0.0.0/0 (which means any IP).  This opens world public IP access to port 80
    - 0.125 pts / element

4. What is the `authorized_keys` file used for?
    - stores list of public keys that can connect as the given user

5. For the following command, provide the full path to where ship.git is located on the server:
    `git clone groot@starlord.com:nebula/ship.git`
    - repo exists in /home/groot/nebula/ship.git
    - .25 pts per folder

6. I have a `main` branch and another branch where I have been making some improvements - the other branch is named `improved`.  Write a process or set of commands to merge changes made on `improved` with `main`.
    - `git checkout main`
    - `git merge improved`

## Short Answer / Fill in the Blank

1. When a key pair is created on AWS, which part of the pair does it keep, public or private?
    - public

2. The default port number for SSH is:
    - 22

3. Translating packets from private IP addresses to public IP addresses and back is performed by: 
    - Network Address Translation (NAT)

4. Given the following information about a subnet:
    Starting address: 172.168.11.0
    Ending address: 172.168.12.255
    Subnet mask: 255.255.254.0
    Write the subnet in CIDR notation
    Hint: think in terms of specifying subnets in AWS security groups

    - 172.168.11.0/23
    - 0.2 points per correct column of info

5. Name of a hook that will run before push when a `git push` is triggered:
    - pre-push
    - pre-receive
    - (partial credit) pre-commit
    - https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks

6. Command to install a software package named `fortune` on Linux:
    - `sudo apt install fortune` or `apt install fortune`

7. Write the subnet mask given the following network prefix and CIDR notation: 152.168.123.0/16
    - 255.255.0.0

8. Changes exist on the remote repository that I don't have in my local repository.  What command will fetch and merge the changes on remote with my local copy?
    - `git pull`

9. File type used to codify input and outputs. 
Examples:
- REST APIs can return data in this format, which can then be easily parsed with code
- CloudFormation templates can use this type of file that is then filled with specifications regarding stack configuration which the AWS API can interpret
    - Answer: JSON or YAML expected

## True / False

1. Regions in the AWS cloud all have the same availability of instance types
    - False - there are different hardware types depending on region.  For example, t1.micro was not available in us-east-1, but t2.micro is.  On a larger scale, some regions will offer different CPU / RAM / GPU configurations.

2. The authorized_keys file, like most configuration files, just needs to exist somewhere on the system I am connecting to.  Location doesn't matter.
    - False - `authorized_keys` must exist in the user's home directory, where user is the username you are connecting to the system with

3. Security groups only allow you to define allowed traffic rules.
    - True - security groups only set allow rules

4. Once a file has been removed from tracking (and the change has been committed and pushed), it will no longer show in GitHub, but will remain in older commits.
    - True - if all you did is remove the file from tracking, it will still exist in the tracked history.

5. The `useradd` command will create the user specified along with their home directory and prompt for additional information about the user.
    - False - `adduser`
    - DROPPED