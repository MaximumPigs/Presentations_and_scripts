# Cyber Security - something something presumption of compromise

## Intro

## The Arpanet - 1969
- Used exclusively for researchers to remotely access supercomputers
- Consisted of only University and Government computers.
- Its own dedicated network, free from external access
- Plain text - Telnet and FTP were the first protocols
- Password free - only password protected in 1971
- A trusted network, used by trusted individuals, with a high knowledge barrier to entry.

How do you protect this information?

- The same way kingdoms protected a castle - physical security. Keep the untrusted outside.

## The Internet - 1983

- TCP/IP was designed, which allowed multiple networks to talk to eachother.
- Arpanet was divided into two parts.
  - Military and Defence (MILNET)
  - Civiliian (University)
- The "internetworking" of these two was shortened to "Internet"
- Not available to the general public, but many networks became interconnected.
- Interconnected computers were no longer part of an exclusive network.
  - Leveraged passwords as a form of access control.
  - Trusted computers could access other trusted computers, as the operator had already verified their identity.

### The Cuckoo's egg
- To gain access to the "trusted" internet, someone would need to satisfy 3 conditions;
  - Have access to a terminal with internet connectivity (University, business etc.)
  - Know how to operate the terminal
  - Prove your identity to the destination network
- Enter Markus Hess - A computer technician
  - Did not operate alone, but was the leader of a small group
  - Had access and knowledge
    - Also knew that Unix operating systems had multiple administrator accounts, and their default passwords.
  - Scanned the internet for Unix systems, and attempted to login using Default Password
  - Once in, he could then move to other Unix systems due to their trust of eachother.
  - Gained access to aprox. 400 military computers, and sold the information he found to the KGB for aprox. US $54000
  - Marckus was prosecuted, received his punishment and that was that - The malicious actor had been dealt with and the Arpanet could be trusted again.

## The riff raff of the intenet - 1991

- With the invention of the "World Wide Web" the internet opened to the public.
- The introduction of the internet to civilians meant that the barrier to entry was significantly lowered.
- Adoption of the internet as a business tool meant previously trusted networks were now part of a larger, untrusted network.
- Could no longer assume that others on the internet were trusted.
- How do you stop untrusted people from coming in to your trusted space?
  - The same way people have been doing it for centiries - a big perimeter wall, and guards at the gates.
- Firewalls invented around this time (1988 - 1991), in order to keep untrusted out of trusted business networks.
- Intrustion Detection System was also invented around this time, to detect unauthorised network access attempts

## Bank robbery - 1994

- With thousands of businesses now within reach from your home computer, surely there is money to be made for less upstanding citizens (and non-citizens)?
- Just as a big perimeter wall has been the go-to method for defending a piece of land since walls were invented, so too has the tried and true method of stealing enormous amounts of money in one go - a good old fashined bank heist.
- In 1994 Vladimir Levin, and accomplices, stole more than 10 million USD over aproximately 40 business transactions using the banks dial-up wire transfer network and compromised credentials.
- While this attack did not occur over the internet, it highlighted that the world outside was untrustworthy, and more needed to be done to keep the untrusted out.

## Bolstering the walls

- From about 1994 through to the early 2000s an emphasis was put on encryption. SSH was invented to replace Telnet, SFTP to replace FTP and SSL to pave the way to encrypted web browsing. All of these could be used to keep communication confidental and protect the authentication process.
- In 1996 the first VPN was invented, providing a way of connecting trusted networks together over the untrusted internet.
- Sometime in the early 2000's Web Application Firewalls became popular in protecting websites from outside attack.
- The walls separating trusted from untrusted were stronger than ever.
- Goverments and Banks were a big target, but most other businesses flew under the radar. Apart from some company secrets, they didn't have much worth "haking" them for.

Except it didn't work.  
  
This concept relied on the assumption that a strong perimeter defence was sufficient to keep untrusted out, and by virtue of eliminating the untrusted, everything inside was deemed trustworthy.

## Money == Motivation

- Cryptolocker 2013
- Changed the threat landscape
- Small to medium businesses became just as much of a viable target as governments and banks
- Criminal syndicates formed around ransomware and extortion
- A significant rise in the number of businesses (networks) being breached.

Sidenote - Ransomware is not the only reason to target an organisation

- Hacktivism
- Nation state / geo-political / warfare
- Rivaling businesses

## The amount of money extorted from businesses is rising every year, Why isn't it working?

The industry made a realisation.

- Breach of a perimeter is inevitable.
  - Not possible
  - Not likely
  - Not probable
  - Inevitable.

By implicitly trusting everything in your own network, an attacked only needs to breach one layer of security. Once they are in, they can easily reach their objective.

Both previous examples show where a perimeter has been breached, and the attacker went on unhindered and undetected to their objective.

## It's not game over once your network has been popped.

- Did the attacker reach their objective?
  - If not, it's a win.
  - How do we prevent an attacked from reaching their objective, when they inevitably breach the perimeter?
  - First we need to understand the anatomy of a breach.

## The anatomy of a breach

- Lockheed Martin - Cyber Kill Chain
- Mitre Att&ck
  - Tactic
  - Technique
  - Procedure

## Sidenote - Prevention vs Detection

- Prevention
  - Pros - Stops an attacker from completing a step
  - Cons - Must be used like a scalple, can prevent legitimate traffic and cause more damage than it prevents
- Detection
  - Pros - Can take action to stop an attack from continuing
  - Cons - Not automated, requires people

Prevention is nice, but you MUST detect.  
If we fail to prevent, we can still detect.  
If we fail to detect, It's over.

## Initial Access

- Perimeter security can mostly be condensed into a single tactic in the Mitre Att&ck framework - initial access.
- The act of breaching a perimeter.
- A whole business exists around this.
  - Initial Access Broker
  - Gain, and sell initial access
    - How would an attacker gain initial access?
      - Phishing
      - Credentials
      - Exposed services
      - Vulnerable services
    - How would a defender prevent this?
      - Mail filtering
      - User training
      - Block Macros and other dangerous files
      - Application Whitelisting
      - Patching
    - How would a defender detect this?
      - Difficult to detect successful initial access, mostly prevention at this stage.
      - Detection of subsequent steps would imply initial access has been gained.

- Perimeter security is still very important to prevent 99.99% of initial access

  - How would an attacker gain initial access?
    - Phishing
    - Exploit exposed 
  - How would a defender prevent this?
    - Outbound firewall rules
    - Network Intrusion Prevention Systems
    - Host based outbound firewall rules
    - Protected DNS
  - How would a defender detect this?
    - Outbound traffic monitoring
    - Network Intrusion Detection Systems
    - Host based monitoring
    - Outbound Packet inspection
    - Persistent / Consistent outbound connections

## Diff: Foothold vs Objective

- Once an attacker breaches the perimeter, they are rarely anywhere near their objective
- Where are they now? And where do they need to be?
- To understand the attackers next steps, we need to know what they are aiming for.
  - Data centric security
    - Identify critical business systems
    - What could your business not afford to lose?

## First things first, survive the reboot.

- Attacker needs to maintain a foothold and gain uninterrupted control of a system.

  - Command and Control
    - How would an attacker effectively control a system?
      - Reverse Shell
      - C2 server (Cobalt Strike / Sliver) - Beaconing
    - How would a defender prevent this?
      - Outbound firewall rules
      - Network Intrusion Prevention Systems
      - Host based outbound firewall rules
      - Protected DNS
    - How would a defender detect this?
      - Outbound traffic monitoring
      - Network Intrusion Detection Systems
      - Host based monitoring
      - Outbound Packet inspection
      - Persistent / Consistent outbound connections

Sidenote: The second we begin to look internally for evidence that an attacker has already breached the perimeter - we immediately lose the trust we once had for the "trusted" environment.

  - Defence Evasion
    - How would and attacker avoid being detected by EDR, SOC, etc?
      - Disable EDR tools
      - "Live off the land"
      - Process hollowing
      - Masquerading
    - How would a defender prevent this?
      - Tamper protection
      - Removing unused software
    - How would a defender detect this?
      - Unusual directories of known softare
      - Unusual parent processes of known software

  - Persistence
    - How would an attacker ensure they still have access after the computer reboots.
      - Scheduled tasks
      - ASEPs
    - How would a defender prevent this?
      - Difficult to prevent, scheduled tasks and many ASEPs are available to unprivileged users
    - How would a defender detect this?
      - Query ASEPs and compare
      - Sysinternals AutoRuns

## Upwards and Inwards

- Attacker now has access to an unprivileged account, on an endpoint with no interesting data. They need information about their environment, more privileged permissions, and to move towards their objective.

  - Discovery


  - Privilege Escalation
    - How does an attacker escalate their privilege?
      - Steal creds
        - Credential Access
      - Exploit a software vulnerability
    - How would a defender prevent this?
      - EDR
      - Reduce local admin access
      - Protect admin accounts (Prevent NTLM hashes being stored)
      - Application whitelisting
    - How would a defender detect this?
      - Unusual access to LSASS service
      - Unusual processes spawned by software
      - Process spawned under a different user account to the parent
      - Unusual login by privileged user account

Sidenote: Monitoring privilege escalation is often percieved as a distrust of staff as it involves questioning their activity within the environment. It is not the staff member who is distrusted, it's the privileged account being monitored that is distrusted as the staff member may not be in control of it.

