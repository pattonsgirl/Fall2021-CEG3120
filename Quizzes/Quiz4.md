# Quiz 4

1. Command to stop the ssh service (and therefore prevent anyone from using SSH):
   Note: you can test this, but you might have to reboot the AWS instance after ;)

2. Managers of the most general part of a domain name (com, org, edu, io). Domain names are then distrubuted to domain registrars, such as Namecheap and GoDaddy, who charge fees for reserving the given unique / specific domain name (xkcd.com, wright.edu, github.io)

3. Describe what the following iptable command will create a rule to do:
   `iptables -A INPUT -s 130.108.0.0/16 -p tcp --destination-port 80 -j ACCEPT`

4. T/F Root domain servers keep an up to date list of every hostname and IP address for all the systems in the world.

5. T/F Resources created as a stack in CloudFormation can also be deleted as a stack - you don't need to manually delete the resources.

6. T/F Given the following chain, systems connecting from 130.108.0.0/16 can connect to port 80 / http:
   Note: dpt:http means default port for http (80)

```
Chain INPUT (policy ACCEPT)
target     prot opt source               destination
DROP       tcp  --  anywhere             anywhere             tcp dpt:http
ACCEPT     tcp  --  130.108.0.0/16       anywhere             tcp dpt:http
```

Commands to recreate quiz scenarios:
iptables -A INPUT -s 0.0.0.0/0 -p tcp --destination-port 80 -j DROP
iptables -A INPUT -s 130.108.0.0/16 -p tcp --destination-port 80 -j ACCEPT
