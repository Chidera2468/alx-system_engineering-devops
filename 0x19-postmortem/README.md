0x19-postmortem
We are going to explore an incident that happened where I was unable to access my application because the load balancer had its IP address changed abruptly without my notice

Issue summary

The issue happened when the application was inaccessible because the server hosting the load balancer had the ip address changed dynamically and did not match the ip address configured in the domain names A record.

Timeline

The issue was detected on Monday 8th may, 2023 and the issue was detected once we ran the command ifconfig and checked the ip address doesn’t match the previous server ip address and we came to the conclusion that it could be the cause.

Actions taken

At this point I had to check if the haproxy server was installed and configured properly to direct traffic to the web servers.
Confirm the ssl configuration and make sure the cert file is available.
Open the cpanel of the domain name provider and configured the new ip address to the A Record.
Root Cause

The root cause of the issue was an abrupt change in the ip address of the server which didn’t allow access to the server at that specific ip address.

Corrective and Preventive measures

The corrective and preventive measures to this problem are that the ip address to the server should be fixed and not dynamic to avoid future ip address changes.
