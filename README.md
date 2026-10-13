Windows RAM Memory Forensics & Investigation Using Volatility 3

 Project Overview
 
This project demonstrates Windows memory forensics using Volatility 3 to investigate running processes, network connections, and suspicious executable memory regions.

Objectives
- Identify operating system details from a memory image.
- Analyze running processes and parent-child relationships.
- Investigate network connections.
- Identify and extract suspicious memory regions.
- Document findings using SHA-256 hashes and an investigation report.

Tools Used
- Volatility 3
- Windows Command Prompt
- CertUtil

Investigation Highlights
- Examined running processes and process relationships.
- Identified an established TCP connection from `rundll32.exe` (PID 1896) to `172.20.20.21:4444`.
- Investigated two executable-writable memory regions belonging to this process.
- Found strings associated with Meterpreter capabilities in the extracted memory dumps.
- Recorded SHA-256 hashes of both memory dumps.

Key Finding

The combined findings are suspicious and warrant further investigation. They do not conclusively prove a successful compromise.

Investigation Report
See [incident-report.md](incident-report.md) for the detailed investigation, evidence hashes, and conclusion.

Skills Demonstrated
- Windows memory forensics
- Process and network investigation
- Volatility 3
- Suspicious memory analysis
- Evidence hashing and documentation
- Incident reporting

 
