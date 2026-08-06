                                                  ##Overview


This project uses PowerShell to automate the creation of multiple Hyper-V virtual machines for repeatable lab and testing environments with the mindset of preparing VMs for a small business or startup ( also known as clients ) for their customers ( also known as end users ). It was built to reduce manual setup and work within limited local system resources.


##Problem It Solves 

~Reduces the amount of manual creation of VMs.

~Limiting amount of cost of hardware for each customer.

~For smaller business, cost effective with tools already on windows machine when assigning to clients.

~Uniformity of VMs based on clients request.


##Why This Project Exists

~Many startup companies do not know where to start when it comes to the IT side of things and from research they can see that price can grow exponentially. The dream is there and the niche will be profitable but no tools to attract customers. With this project, will have enough resources to gain some traction and conduct meetings with potential investors in scaling the business. 

~Currently on local machine with 16 GBs of RAM and with browser open, can only run 3 VMs at a time ( this is including the server created which can see more information about in Windows-Server_Active-Directory-Environments repo).


##Features

~Prepared a golden image on windows 11 OS to copy from ( baseline of how VMs for customers should be structured unless otherwise noted from clients )

~Joins domain

~Renames VM to avoid conflict of overriding previous created VM

~Currently VMs are associated to internal switch

~To limit strain on local machine, golden image only using 2 GB of RAM


##Requirements

~Hyper-V enabled which is standard on windows 10 ( if on windows 11 will need to go to " Turn Windows Features On or Off " to enable hyper-v )

~PowerShell

~Admin Credentials for domain

~Golden Image ( will need to update location of golden image in " win11VMs-renameVMs-joindomain " script )


##How to Use It

***Steps provided will need to be tweaked in script choosing own server created on Hyper-V, admin credentials on server, static ip address of server, location of storing VMs and VDHX on local machine, and ensuring following switch manager setup as well as memory settings to match output***

~Open Hyper-V > turn on server

~On PowerShell as admin > run script and let the automation occur


##What I Learned

~When I initially started this project, the focus was limiting the amount of cost from a small business prospective or even startup. So, utilizing local machine with limited RAM in creating multiple VMs which would turn on > complete configuration then turn off to allow the next VM to be created. This is the base and once start discussing further with client, can determine if should go strictly cloud or buy a physical server or higher ram workstation to run more VMs at once.

~I understood that it is a lot easier to create one golden image as standard for client which will be distributed to all customers saving time and resources. Once created if need to make changes, such as adding apps, or network drive mappings, that can be done from a Service Desk Tier 1 -3 rather than System Admins.

~I learned about simplicity is key in speeding time of creations when need multiple VMs in one sitting. 


##Limitations or Known Issues 

~There is only one golden image which cloned VMs follow same user password which is a huge security risk. 

~Due to the amount of time it takes for each VM to spool ( for 10 VMs can take about 30 - 45 minutes ) which is not ideal but I see this more of a hindrance when initially creating VMs. Usually businesses know who is being on-boarding and will need VM so, can keep a small pool of additional VMs and add more as needed over time. 

~Another security flaw is using global password on server when prompted for joining domain with each cloned VM. 


##Future Improvements

~For cloned VMs with same password for each account: this can be mitigated when Service desk team updates password for customer. This is also going to be handled and discussed further in ad-user-onboarding repo. I will also update the script here to dynamically ask me what password to set user so, password will be changed as soon as start working internally on VM.

~Update Script to lessen time of start and stop of VMs ( finding that sweet spot ) so, spooling of multiple VMs in one sitting is faster.

~Under the ad-user-onboarding repo, will create a field where local admin rights for Service Desk members or who is authorized to setup VMs to limit exposure for global admin credentials. 

~Update script where I put admin credential one time so, do not have to sit in front of machine for each VM created and have to keep putting the credential ( Not a huge issue but once update more time to work on something else as this is running ).

~Upgrade RAM on local machine to test more bulk VMs to do a stress test with over 10 VMs at once.
  
  ~Can also transition to Azure Virtual Desktop or AWS which can still be cost efficient and limiting RAM resources which many hybrid or cloud based companies are moving too.

##Screenshots

~Golden Image Memory Settings which is replicated for each VM

<img width="585" height="582" alt="Screenshot 2026-08-03 220504" src="https://github.com/user-attachments/assets/f2a13a38-83c1-47ac-9d64-e15bb19e8ffc" />

~Golden Image Settings

<img width="887" height="756" alt="Screenshot 2026-08-03 220421" src="https://github.com/user-attachments/assets/32f28847-45b1-40ec-a108-07db99a41be2" />

~Virtual Switch Manager Settings

<img width="577" height="637" alt="Screenshot 2026-08-03 220630" src="https://github.com/user-attachments/assets/d0de3fa9-85f5-4406-884d-ed976b6bb2bd" />

