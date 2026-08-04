#Overview

This project uses PowerShell to automate the creation of multiple Hyper-V virtual machines for repeatable lab and testing environments with the mindset of preparing VMs for a business ( also known as clients ) for their customers ( also known as end users ). It was built to reduce manual setup and work within limited local system resources.

#Problem It Solves. 

~Reduces the amount of manual creation of VMs.
~For smaller business, cost effective with tools already on windows machine assigning to clients.
~Uniformity of VMs when working with a company whether MSP size to enterprise level.

#Why This Project Exists

~Currently on local machine with 16 GBs of RAM and with browser and can only run 3 VMs at a time ( this is including the server created which can see more information about in Windows-Server_Active-Directory-Environments repo). 

#Features

~Prepared a golden image on windows 11 OS to copy from ( baseline of how VMs for customers should be structured unless otherwise noted from clients )
~Joins domains
~Renames VM to avoid conflict of overriding previous created VM
~Currently VMs are associated to internal switch
~To limit strain on local machine, golden image only using 2 GB of RAM

#Requirements

~Hyper-V enabled which is standard on windows 10 ( if on windows 11 will need to go to " Turn Windows Features On or Off " to enable hyper-v )
~PowerShell
~Admin Credentials for domain
~Golden Image ( will need to update location of golden image in " win11VMs-renameVMs-joindomain " script )

#How to use it

~When on local machine > run Powershell as admin
~

#What I learned. Show growth, especially around Hyper-V, scripting, and working within system limits.

#Limitations or known issues. Be honest about what it does not handle yet.

#Future improvements. Mention what you plan to add next, like bulk input files, logging, validation, or better error handling.

#Screenshots or examples. Even one screenshot of console output or Hyper-V Manager helps a lot.

