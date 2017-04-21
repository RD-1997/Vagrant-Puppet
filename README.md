# Vagrant-Puppet
Auto installation and configuration of a puppet master/agent connection. 


# Step 1
You will need to download Vagrant and the appropriate box which is: Puppetlabs/centos-7.2-64-puppet

# Step 2
Once you have done that just copy the the files into a folder of own preference. 

# Step 3
Write the command: 

> vagrant up --provision

The puppetmaster and agent will now be installed and configured.

# Step 4 
Once everything is succesfully completed, ssh to your master with the command: 

> vagrant ssh master

# Step 5
Write the following commands:

> sudo su
> puppet cert list 

This will list all of the incoming certificate requests from puppet agents, in our case we only have one puppet agent. Once you see the hostname of the puppet agent showing up along with the fingerprint, write the following command:

> puppet cert sign hostnameofpuppetagent

Voila, the certificate has been signed and your puppetagent is succesfully connected to the puppetmaster. 


# Possible Error
If you can't make a connection with the puppet master try to change the static IP's in the vagrantfile to an IP that is in your network range. Also make sure that you are using the right box. 
