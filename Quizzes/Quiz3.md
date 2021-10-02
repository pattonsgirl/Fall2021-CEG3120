# Quiz 3

1. T/F A Discord Bot can run on a Discord server without an authorization (OAuth) token
    - False.  The Discord API (discord.py) needs authorization to access the Discord server

2. T/F A Pull Request can be used to merge content between branches
    - True.  Pull Requests can be set to merge between two branches.  You need to confirm the merge for the merging to occur

3. I have created a file that contains secrets, added it for tracking, commited my changes, and pushed my changes to GitHub.  What steps do I need to take to undo my mistake (remove the file from tracking and GitHub)?
    - remove the file from tracking (git rm filename or git rm --cached filename)
    - list the file in the .gitignore file
    - commit and push the modifications

4. A ____ is a piece of software that I can run my code through in order to check for consistent code practices.  They are not debuggers, but can warn me of unused variables, fix formatting, and reorder imported / included libraries.  While they exist for most languages, we have looked at black, isort, and pylint for python code.
    - linter
    - static analysis tool
    - compilers compile code.  They are needed for compiled languages.  Compilers do not care about baest practices, just if you code as written can be compiled into an executable program
    - hooks can be used to run linters
    - unit tests are a piece of code I create - unit tests are not usually used for best practices, more towards if your code you are working on integrating will break the ecosystem of code you are adding to

5. What does a subnet mask allow me to define?
    - a subnet mask defines the **range of IP addresses** that can be used within a network or subnet
    - This can then define 
        - a range of IPs that are / are not allowed inbound access on a firewall
        - a range of IPs that are / are not allowed to be communicated with via outbound access on a firewall
        - a range of IPs for routing traffic based on certain rules (routing table)

6. We have identified that IPv4 address are finite - private subnets allow us to "stretch" the number of addresses by attaching a single public IP to a router, for example, and then uses that public IP for all world communications to and from the private network.  What allows for this translation of private to public IPs (and back again)?
    - NAT = Network Address Translation
    
7. What subnet mask correlates with 120.3.90.5/16?
    - 255.255.0.0
    - /16 means 16 bits are set.  16 / 8 = 2.  2 sets of 8 bits are set.  Bits are set from the start
    - 11111111.11111111.00000000.00000000
    - 120.3.255.255	is the broadcast address, which is a bit flipped complement of the subnet mask