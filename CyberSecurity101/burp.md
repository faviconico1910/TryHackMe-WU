# Burp Suite: The Basics
## Task 7:
There are two types of settings: Global settings (also known as User settings) and Project settings.

Global Settings: These settings affect the entire Burp Suite installation and are applied every time you start the application

Project Settings: These settings are specific to the current project and apply only during the session

1. Search: Enables searching for specific settings using keywords.
2. Type filter: Filters the settings for User and Project options.
3. Categories: Allows selecting settings by category.

## Task 8: Introduction to the Burp Proxy

Response Interception: By default, the proxy does not intercept server responses unless explicitly requested on a per-request basis. The "Intercept responses based on the following rules" checkbox, along with the defined rules, allows for a more flexible response interception.

Match and Replace: The "Match and Replace" section in the Proxy settings enables the use of regular expressions (regex) to modify incoming and outgoing requests. This feature allows for dynamic changes, such as modifying the user agent or manipulating cookies.

## Task 10: Site Map and Issue Definitions

Question: 
- What is the flag you receive after visiting the unusual endpoint? ```THM{NmNlZTliNGE1MWU1ZTQzMzgzNmFiNWVk}```

## Task 12: Scoping and Targeting

The Scope settings window allows us to control our target scope by including or excluding domains/IPs.
This section is powerful and worth spending time getting familiar with.

