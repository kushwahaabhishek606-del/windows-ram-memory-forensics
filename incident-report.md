 Windows RAM Memory Forensics & Investigation Using Volatility 3

 1. Project Objective
To analyze a Windows memory image using Volatility 3, examine running processes and network connections, and investigate suspicious memory regions.

 2. Tools Used
- Volatility 3
- Windows Command Prompt
- PowerShell
- CertUtil (SHA-256 hashing)

 3. Investigation Performed
- Verified the integrity of the original memory image against its working copy using SHA-256.
- Identified the operating system information using `windows.info`.
- Examined running processes using `windows.pslist`.
- Investigated parent-child process relationships using `windows.pstree`.
- Examined network connections using `windows.netscan`.
- Identified suspicious executable memory regions using `windows.malfind`.
- Dumped two memory regions associated with PID 1896 (`rundll32.exe`).
- Recorded SHA-256 hashes of both extracted memory dumps.

 4. Key Findings

 Operating System
The memory image indicated a 64-bit Windows system based on Windows 7 SP1, build 7601.

 Suspicious Process
- Process: `rundll32.exe`
- PID: 1896
- Parent process: `spoolsv.exe` (PID 856)

The process relationship was considered suspicious and required further investigation.

 Network Connection
An established TCP connection was observed:

- Local endpoint: `172.20.20.9:49227`
- Remote endpoint: `172.20.20.21:4444`
- Process: `rundll32.exe` (PID 1896)

Port 4444 can be associated with remote-access or penetration-testing tools, but the port alone does not establish malicious activity.

 Memory Analysis
Two memory regions associated with PID 1896 had `PAGE_EXECUTE_READWRITE` protection. Their extracted memory dumps contained strings associated with Meterpreter capabilities, including process, network, and filesystem operations.

This combination of observations represents a strong indicator of potentially malicious activity.

 5. Evidence Hashes

Memory dump 1

File: `pid.1896.vad.0x1b30000-0x1b69fff.dmp`

SHA-256: `31d7f9cc03b604bad28d4aea556de67ae3e6fa3bc3e5777a6d5e0a6b459f5bd0`

Memory dump 2

File: `pid.1896.vad.0x1f60000-0x1fcafff.dmp`

SHA-256: `43ffef3e4be196e5c078626c07f30527fd2e8f93bc2c341d1d73a923b9e96199`

 6. Conclusion
The investigation identified suspicious process relationships, an established connection to a remote endpoint on port 4444, executable-writable memory regions, and Meterpreter-associated strings.

Together, these findings warrant further incident investigation. However, the available evidence does not conclusively establish malware execution or a successful compromise.

 7. Limitations
The investigation focused on selected process, network, and memory artifacts. The findings were not independently validated through malware sample analysis or additional endpoint evidence.

 8. Skills Demonstrated
- Windows memory forensics
- Volatility 3 analysis
- Process tree investigation
- Network connection analysis
- Suspicious memory identification
- Evidence hashing and documentation
- Incident investigation reporting