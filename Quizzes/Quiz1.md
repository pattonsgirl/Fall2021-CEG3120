# Quiz 1

1. What is the IP address to your AWS instance?
    - Once you have created your stack, go to your instances.  Click the checkmark next to your instance, and look at the pop up thing along the bottom.  Look for the "Public IPv4 address" field - your public IP address to sign in to the system is there

2. What is the password to view Webex recordings (all of them)?
    - `Ceg3120-F21`

3. What file, for a given user, stores the public keys that are authorized for connections as that user?
    - Accepted answers: `authorized_keys`, `.ssh/authorized_keys`, `~/.ssh/authorized_keys`
    - For each home directory, the user can have an `authorized_keys` file stored in their `.ssh` folder.  This file holds a list of all public keys that can connect to a system.  Those who want to connect as that user need to use a private key that corresponds to a public key that is stored on the system being connected to.
    - `.ssh` is just a folder.  There are files inside.  Private keys stay on systems you are making connections with.  Public keys need to be stored in a specific file on systems you are connecting to, and that file is the `authorized_keys` file in the `.ssh` folder of the user you are connecting with.
    - `known_hosts` comes from the `Would you like to connect to the system (yes/no)` prompt.  When you first connect to a server, an entry is placed in your (not the remote system's) `.ssh/known_hosts` file.  This listing has a fingerprint of systems you have connected to.  This fingerprint is checked everytime you make a connection to ensure that the remote system has not been replaced.
    - References to private or public keys are singular.  Private keys stay on systems you are making connections with.  Public keys need to be stored in a specific file on systems you are connecting to, and that file is the `authorized_keys` file in the `.ssh` folder of the user you are connecting with.

4. To make a connection to a system, such as me connecting to the AWS instance, which key type do I need to have on my system, the private key or the public key?
    - Private keys stay on systems you are making connections with.  
    - Public keys need to be stored in a specific file on systems you are connecting to, and that file is the `authorized_keys` file in the `.ssh` folder of the user you are connecting with.

5. What is the URL for your GitHub classroom repo?
    - `https://github.com/WSU-kduncan/ceg3120-YOURGITHUBUSERNAME`
    - `https://github.com/pattonsgirl/Fall2021-CEG3120` - this is where I'm putting course material stuff.  You don't have access to mess with it ;)
    - `https://github.com/WSU-kduncan/ceg3120-pattonsgirl-1` - this is mine, where pattonsgirl is my github username.  What's yours?
