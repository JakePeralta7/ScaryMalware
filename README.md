# ScaryMalware

This is a mini-malware I developed in Python as a PoC in order to implement techniques I've learned about

## So, What this malware do?
1. Copies itself to the user profile's folder as .pyw file (run without a visible window) and hides himself (using attrib +h)
2. Checks if someone tried to access the script (the malware himself) and stops if touched
3. Sends a message to the user every 15 seconds "Hello, I'm your malware"
4. Kills known analysis tool
5. Creates persistency as a schedueled task (runs every three hours)
6. Creates persistency in the user's startup folder
7. Runs some reconnaissance commands

## PoC mapped by MITRE ATT&CK
### [Reconnaissance](https://attack.mitre.org/tactics/TA0043/)
The malware executes various commands that helps him understand the network (where he is, what his privelges are)
### [Persistence](https://attack.mitre.org/tactics/TA0003/)
- The malware creates a [schedueled task](https://attack.mitre.org/techniques/T1053/005)
- The malware copies himself to the user's [startup folder](https://attack.mitre.org/techniques/T1547/001/)
### [Defense Evasion](https://attack.mitre.org/tactics/TA0005/)
- The malware [hides himself](https://attack.mitre.org/techniques/T1564/001/) using attrib +h
- The malware kills known analysis tools