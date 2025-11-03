## Task 2: Windows Domains
Window Domain is a group of users and computers under the administration of a given business.
Active Directory is a directory service that provides a central database for managing network resources, including users, computers, and groups.
The server that runs the Active Directory services is known as a Domain Controller (DC).

Questions:

- In a Windows domain, credentials are stored in a centralised repository called...: Active Directory
- The server in charge of running the Active Directory services is called...: Domain Controller

# Task 3: Active Directory
Users, groups, machines, ...

Questions:

- Which group normally administrates all computers and resources in a domain?: Domain Admins
  
- What would be the name of the machine account associated with a machine named TOM-PC? TOM-PC$

- Suppose our company creates a new department for Quality Assurance. What type of containers should we use to group all Quality Assurance users so that policies can be applied consistently to them?: Organizational Units.

## Task 4: Managing Users in AD
Delegation: grant users specific privileges to perform advanced tasks on OUs without needing a Domain Administrator to step in. For example, grant delegate control to Phillip who's working in IT Department.

<img width="971" height="818" alt="image" src="https://github.com/user-attachments/assets/2ba904c9-5697-475f-af42-fe3cda0b570c" />

<img width="980" height="875" alt="image" src="https://github.com/user-attachments/assets/c74f2c17-8b41-4468-b4a8-b7d1904be4e2" />

Change password using ```phillip account``` via RDP ``` PS C:\Users\phillip> Set-ADAccountPassword sophie -Reset -NewPassword (Read-Host -AsSecureString -Prompt 'New Password') -Verbose ```

Force a password reset at the next logon ```PS C:\Users\phillip> Set-ADAccountPassword sophie -Reset -NewPassword (Read-Host -AsSecureString -Prompt 'New Password') -Verbose```

Login to sophie account, retrive the flag

<img width="956" height="747" alt="image" src="https://github.com/user-attachments/assets/74a7175e-a78c-4a76-88ef-68138a847ce6" />

Questions

- What was the flag found on Sophie's desktop? THM{thanks_for_contacting_support}

- The process of granting privileges to a user over some OU or other AD Object is called...: Delegation

## Task 5: Managing Computers in AD

Questions:

-  After organising the available computers, how many ended up in the Workstations OU? 7

- Is it recommendable to create separate OUs for Servers and Workstations? yay

## Task 6: Group Policies
GPOs are simply a collection of settings that can be applied to OUs. GPOs can contain policies aimed at either users or computers, allowing you to set a baseline on specific machines and identities

Questions

- What is the name of the network share used to distribute GPOs to domain machines? SYSVOL

## Task 7: Authentication methods
2 protocols are used for network authentication in windows domains

- **Kerberos**: Used by any recent version of Windows. This is the default protocol in any recent domain.
- **NetNTLM**: Legacy authentication protocol kept for compatibility purposes.
- **Ticket Granting Ticket (TGT)** along with a **Session Key**

Question:
- Will a current version of Windows use NetNTLM as the preferred authentication protocol by default? nay

- When referring to Kerberos, what type of ticket allows us to request further tickets known as TGS? Ticket Granting Ticket

- When using NetNTLM, is a user's password transmitted over the network at any point? nay, password is never transmitted through the network for security.

## Task 8: Trees, Forests and Trust
Tree: If you have two domains that share the same namespace (thm.local in our example), those domains can be joined into a Tree.
If our thm.local domain was split into two subdomains for UK and US branches, you could build a tree with a root domain of thm.local and two subdomains called uk.thm.local and us.thm.local, each with its AD, computers and users. 

<img width="1218" height="963" alt="image" src="https://github.com/user-attachments/assets/89ed425e-fa57-4100-9bca-ed07f640d364" />

The *Enterprise Admins* group will grant a user administrative privileges over all of an enterprise's domains. Each domain would still have its Domain Admins with administrator privileges over their single domains and the Enterprise Admins who can control everything in the enterprise

Forest: The union of several trees with different namespaces into the same network is known as a forest.

Trust Relationships: having a trust relationship between domains allows you to authorise a user from domain THM UK to access resources from domain MHT EU.

Questions:
- What is a group of Windows domains that share the same namespace called? Tree
- What should be configured between two domains for a user in Domain A to access a resource in Domain B? A Trust Relationship


