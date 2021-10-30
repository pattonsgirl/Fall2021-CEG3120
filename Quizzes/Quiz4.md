# Quiz 4

1. Command to stop the ssh service (and therefore prevent anyone from using SSH):
   Note: you can test this, but you might have to reboot the AWS instance after ;)

   - `sudo systemctl stop ssh`
   - `sudo iptables -P INPUT DROP`
   - `sudo iptables -A INPUT -p tcp --dport 22 -s 0/0 -j DROP`

2. Managers of the most general part of a domain name (com, org, edu, io). Domain names are then distrubuted to domain registrars, such as Namecheap and GoDaddy, who charge fees for reserving the given unique / specific domain name (xkcd.com, wright.edu, github.io)

   - Top Level Domains / ICANN

3. Describe what the following iptable command will create a rule to do:
   `iptables -A INPUT -s 130.108.0.0/16 -p tcp --destination-port 80 -j ACCEPT`

   - add a rule to the INPUT chain (inbound traffic rule)
   - inbound traffic from 130.108.0.0/16 subnet
   - tcp protocol
   - rule is specifically for port 80
   - rule is to ACCEPT traffic from this subnet

4. T/F Root domain servers keep an up to date list of every hostname and IP address for all the systems in the world.

   - False - they keep a record of the top level domains servers
   - hostnames are a per server type name. A root server would not directly know "wright.edu". It would point to a TLD for edu, which would then point to a domain server with records for wright.edu

5. T/F Resources created as a stack in CloudFormation can also be deleted as a stack - you don't need to manually delete the resources.

   - True. You can select a stack, then click Delete. This will delete everything made by the stack

6. T/F Given the following chain, systems connecting from 130.108.0.0/16 can connect to port 80 / http:
   Note: dpt:http means default port for http (80)

```
Chain INPUT (policy ACCEPT)
target     prot opt source               destination
DROP       tcp  --  anywhere             anywhere             tcp dpt:http
ACCEPT     tcp  --  130.108.0.0/16       anywhere             tcp dpt:http
```

      - False - the first rule in the chain will drop all traffic to port 80. The 130.108.0.0/16 allow rule is second, which would not get read or made an expection

Commands to recreate quiz scenarios:
iptables -A INPUT -s 0.0.0.0/0 -p tcp --destination-port 80 -j DROP
iptables -A INPUT -s 130.108.0.0/16 -p tcp --destination-port 80 -j ACCEPT
