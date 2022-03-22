# Final Project: Attack, Defense & Analysis of a Vulnerable Network

## Blue Team

As Blue Team we configured watcher alerts in Kibana ahead of time so that we can see how they act as the attack is happening. These alerts could also be viewed in the Discovery page by creating a related index pattern for the Discovery page to pull from so that we could view the network traffic associated with them.
After conducting the attack, we needed to find evidence of the attacks in Kibana. We used what we found to tailor new watcher alerts based on signatures that we deemed important. 

This part relates to the [Defensive Report](/Defensive%20Report.md).

## Red Team

The goal of the Red Team was to gain root access to Target 1 using the Kali VM and to "capture flags" along the way. To do this, the username and password of the account with sudo privileges granted to python needed to be discovered, and then the escalation to root could occur by exploiting a python vulnerability which required having the aforementioned sudo privileges for python.

This part relates to the [Offensive Report](Offensive%20Report.md).

## Wireshark Activity

In this part, we were tasked to act as if the following scenario was playing out

"You are working as a Security Engineer for X-CORP, supporting the SOC infrastructure. The SOC analysts have noticed some discrepancies with alerting in the Kibana system and the manager has asked the Security Engineering team to investigate.

Yesterday, your team confirmed that newly created alerts are working. Today, you will monitor live traffic on the wire to detect any abnormalities that aren't reflected in the alerting system.

You are to report back all your findings to both the SOC manager and the Engineering Manager with appropriate analysis." 

This part relates to the [Network Report](/Network%20Report.md).

Details can be found in the [Project Presentation](https://docs.google.com/presentation/d/1FHGCIpeklxHBZqKLHTWi228rQrTHEQ1V/edit?usp=sharing&ouid=110315788476304063614&rtpof=true&sd=true)
