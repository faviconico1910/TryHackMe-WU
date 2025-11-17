## Task 3: Splunk Components
Splunk has three main components: Forwarder, Indexer, and Search Head.

***Forwarder***:  is a lightweight agent, collect the data and send it to the Splunk instance. The forwarder collects the data from the log sources and sends it to the Splunk Indexer. 
Some of the key data sources are:
- Web server generating web traffic.
- Windows machine generating Windows Event Logs, PowerShell, and Sysmon data.
- Linux host generating host-centric logs.
- Database generating DB connection requests, responses, and errors.

***Indexer***: Splunk Indexer plays the main role in processing the data it receives from forwarders. It parses and normalizes the data into field-value pairs, categorizes it, and stores the results as events, making the processed data easy to search and analyze.

***Search Head***: The searches are done using the SPL (Search Processing Language), a powerful query language for searching indexed data. When the user performs a search, the request is sent to the indexer, and the relevant events are returned as field-value pairs.
The Search Head also allows you to transform results into presentable tables and visualizations such as pie, bar, and column charts.

## Task 4: Navigating Splunk

Question:
- In the Add Data tab, which option is used to collect data from files and ports? ```Monitor```

## Task 5: Adding Data

Below is a chart listing from the Splunk documentation detailing each data source category.

<img width="1093" height="459" alt="image" src="https://github.com/user-attachments/assets/eac5b501-52fa-4421-a1a3-d493f7ce686f" />


Question
- Upload the data attached to this task and create an index "VPN_Logs". How many events are present in the log file? ```2862```
- How many log events are captured by the user Maleena? ```60```
- What is the username associated with IP 107.14.182.38? ```Smith```

<img width="1357" height="662" alt="image" src="https://github.com/user-attachments/assets/e070c90b-48d6-47e5-821f-113d9736cf1b" />

- What is the number of events that originated from all countries except France? ```2814```
- How many VPN events were associated with the IP 107.3.206.58? ```14```

<img width="1716" height="333" alt="image" src="https://github.com/user-attachments/assets/df4b4ffb-5c14-4021-8121-f2756e1fcc3a" />

