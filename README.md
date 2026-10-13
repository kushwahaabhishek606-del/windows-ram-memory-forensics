Windows RAM Memory Forensics & Investigation Using Volatility 3
Project Overview
This project demonstrates Windows memory forensics using Volatility 3 to investigate running processes, network connections, and suspicious executable memory regions.
Objectives
Identify operating system details from a memory image.
Analyze running processes and parent-child relationships.
Investigate active network connections.
Identify and extract suspicious memory regions.
Document findings using SHA-256 hashes and an investigation report.
Tools Used
Volatility 3
Windows Command Prompt
CertUtil
Investigation Highlights
Examined process activity and process relationships.
Identified an established TCP connection from rundll32.exe (PID 1896) to 172.20.20.21:4444.
Investigated two executable-writable memory regions belonging to the process.
Found strings associated with Meterpreter capabilities in the extracted memory dumps.
Calculated SHA-256 hashes for both extracted memory regions.
Key Finding
The combination of suspicious process relationships, the network connection, executable-writable memory, and Meterpreter-associated strings warrants further investigation. These findings alone do not conclusively prove a successful compromise.
Report
See incident-report.md for the investigation methodology, findings, evidence hashes, and conclusion.
Skills Demonstrated
Windows memory forensics
Process and network investigation
Volatility 3
Suspicious memory analysis
Evidence integrity and documentation
Incident reporting
 
