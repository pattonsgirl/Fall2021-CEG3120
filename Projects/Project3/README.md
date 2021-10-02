# Project 3

## Objectives:

- Understand and build a private cloud network
- Understand and build an EC2 instance
- Create a CloudFormation to your specification to remove manual creation

## Assignment Notes / Hints

Create a `Project3` folder in your GitHub Classrooms repo.  This project is mostly documentation of work, so you are welcome to work wherever you are comfortable.  I would float towards VSCode myself.

In your `Project3` folder, create a file named `README.md`  Do you work for Parts 1 & 2 here.  Part 3 will have your creating a CloudFormation template, which will be its own deliverable you need to include in your repo.  You are welcome to include Part 3 notes in your repo if you need to write notes for partial credit.

- It will be handy, but not necessary, to compare / contrast the resources you are making with the working "stack" you created way back when.  That stack is based on a template, and that template defined all of these resources - and worked.
- When asked to create "tags", you want to make a "Name" tag and then write the name in the value field.  Sometimes the "Name" tag will be autofilled for you.  Sometimes not.
- If you get to a point where you need to start over, carefully go through and delete the resources you have already created.  
    1. This is good maintainence.  Leaving behind junk is frowned upon in any industry
    2. This will keep you from leaving up resources you can be charged for (like unused instances and elastic IPs)

## Part 1 - Build a VPC

For each step below, provide a screenshot that shows the network resource has been created according to specification.  This will usually involve clicking on the resource, and showing configurations in the details menu

1. Create a VPC.  
    - Tag it with "YOURLASTNAME-VPC"
    - Specify a /24 private IP address range
2. Create a subnet
    - Tag it with "YOURLASTNAME-Subnet"
    - Specify a /28 private IP address range
    - Attach it to your VPC
3. Create an internet gateway
    - Tag it with "YOURLASTNAME-gw"
    - Attach it to your VPC
4. Create a route table
    - Tag it with "YOURLASTNAME-routetable"
    - Attach it to your VPC
    - Associate it with your subnet
    - Add a routing table rule that sends traffic to all destinations to your internet gateway
5. Create a security group
    - Tag it with "YOURLASTNAME-sg"
    - Allow SSH for a set of trusted networks including:
        - Your home / where you usually connect to your instances from
        - Wright State (addresses starting with 130.108)
        - Instances within the VPC
    - Attach it to your VPC
    - Image should include your Inbound rules
6. (If necessary, else skip) Create a key pair

## Part 2 - EC2 instances

1. Create a new instance.  Give a write up of the following information:
    - AMI selected
        - default username of the instance type selected
    - Instance type selected
2. Attach the instance to your VPC.  As discussed there are different pathways to doing this.  Say how you did it.
3. Determine whether a Public IPv4 address will be auto-assigned to the instance.  Justify your choice to do so (or not do so)
    - **NOTE** - in the next few steps, you will be required to request an Elastic IP address and associate it to the instance.  Factor that in to your discussion here.
4. Attach a volume to your instance.  As discussed there are different pathways to doing this.  Say how you did it.
5. Tag your instance with a "Name" of "YOURLASTNAME-instance".  Say how you did it.
6. Associate your security group, "YOURLASTNAME-sg" to your instance.  Say how you did it.
7. Reserve an Elastic IP address.  Tag it with "YOURLASTNAME-EIP".  Associate the Elastic IP with your instance.  Say how you did it.
8. Create a screenshot your instance details and add it to your project write up.  Example below:
![sample instance details](sample.png)
9. `ssh` in to your instance.  Change the hostname to "YOURLASTNAME-AMI" where AMI is some version of the AMI you chose.
    1. It is wise to copy config files you are about to change to filename.old  For `/etc/hostname`, for example, I would first copy the current `hostname` file to `/etc/hostname.old`
    2. You should not change permissions on any files you are modifying.  They are system config files.  You may need to access them with adminisrative privileges.
    3. Here is a helpful resource: https://www.tecmint.com/set-hostname-permanently-in-linux/ I did not modify `/etc/hosts` on mine - do so or not as you wish.
10. Create a screenshot your ssh connection to your instance and add it to your project write up - make sure it shows your new hostname.


## Part 3 - Your first CloudFormation template

I think we can agree that was a lot of menus to go through and things to check.  If you were working for, say, a web development company, and you had to do that everytime you got a new customer who wanted a webpage, there would be some frustrations.  The "cloud" agrees, and therefore cloud services created templates.  In AWS, these are called CloudFormation templates.  In these files, you layout every details of how you want your EC2 setup to be, from VPC to instances.  AWS CloudFormation can take these files as input, and feed the values into API call that create all peices.

A [base template](cf-template.yml) has been provided for you.  Due to how many things are in these templates, I would use this base and make the modifications requested.

Your deliverable is a CloudFormation template.  Make sure you include it in your repository.  Your CloudFormation template should build the following:

- 

## Submission

1. Commit and push your changes to your repository.  Verify that these changes show in your course repository, https://github.com/WSU-kduncan/ceg3120-YOURGITHUBNAME
    - Your repo should contain:
    - `images` folder (optional depending on how you implement screenshots)
    - `YOURLASTNAME-cf.yml`
    - `README.md`

2. In Pilot, paste the link to your project folder.  Sample link: https://github.com/WSU-kduncan/ceg3120-YOURGITHUBUSERNAME/blob/main/Projects/Project3
