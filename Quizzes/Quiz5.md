# Quiz 5

1. T/F By giving the system a hostname with hostnamectl, my machine can now be found in a DNS lookup by any system connected to the internet.

   - False. This does not mention additional steps of creating a record on a name server. Just changing the hostname alone does not provide the network as a whole information on how to find the machine.

2. T/F In a haproxy config file, the global section defines the set of servers to distribute content to.

   - False. `backend` would be the more accurate description. `frontend` could also be the reference given the wording.

3. T/F Application Delivery Controllers can be configured to connect client requests to different pools depending on the content requested; there can be a pool of servers that deal with clients requesting /api URLs and another pool for clients requesting /blog

   - True. We can check the URI (the end part of the URL)

4. Name two load balancing allocation strategies (how the proxy distributes connections to the server pool)

   - round robin
   - weighted round robin
   - least connections
   - least response time

5. Name a strategy to copy files to remote servers.

   - `scp`, `sftp`, copy paste

6. What port is haproxy listening for connections on?
   - 80
