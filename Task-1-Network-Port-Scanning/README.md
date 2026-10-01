
# Local Network Port Scanning 🔐

A network reconnaissance project completed as part of the Elevate Labs Cybersecurity Internship.

The objective is to learn how to discover devices on an authorised local network, identify open ports, understand the services associated with them, and document potential security risks.

## Objectives

- Understand IP addresses and network ranges.
- Discover active hosts on a local network.
- Perform TCP port scanning using Nmap.
- Identify services running on discovered ports.
- Interpret scan results and understand potential security implications.
- Document findings and basic security recommendations.

## Tools Used

- Nmap
- macOS Terminal
- OrbStack / Linux virtual machine (optional)
- Wireshark (optional)
- Git and GitHub

## Project Structure

```text
elevate-labs-network-port-scan/
├── reports/
│   └── scan-results.txt
├── screenshots/
│   └── scan-terminal.png
└── README.md
```

The report and screenshot filenames may differ depending on the actual files included in the repository.

## Prerequisites

Install Nmap from the official website:

https://nmap.org/download.html

On macOS with Homebrew, you can install it using:

```bash
brew install nmap
```

Verify the installation:

```bash
nmap --version
```

## Scanning Process

### 1. Identify the Local IP Address

On macOS, check the IP address of the Wi-Fi interface:

```bash
ipconfig getifaddr en0
```

Determine the correct subnet using your network configuration or router settings.

### 2. Discover Hosts

Run host discovery against your authorised local subnet:

```bash
nmap -sn YOUR_LOCAL_SUBNET
```

Replace `YOUR_LOCAL_SUBNET` with the actual subnet you are authorised to scan.

### 3. Scan TCP Ports

To scan common TCP ports on your own machine:

```bash
nmap 127.0.0.1
```

To perform a TCP SYN scan against an authorised target:

```bash
sudo nmap -sS TARGET_IP
```

### 4. Detect Services and Save Results

```bash
nmap -sV TARGET_IP -oN reports/scan-results.txt
```

The `-sV` option attempts to identify services and versions, while `-oN` saves the output in normal text format.

Use the actual target IP address of a device you are authorised to test.

## Understanding the Results

Nmap may classify ports as:

- **Open:** A service is listening on the port.
- **Closed:** The target is reachable, but no service is listening on the port.
- **Filtered:** Nmap cannot determine the port state because packet filtering or another network condition prevents a clear response.

An open port is not automatically a vulnerability. Risk depends on the service, its configuration, exposure, and whether it needs to be accessible.

## Security Considerations

- Disable services that are not required.
- Restrict access to administrative services.
- Configure host and network firewalls appropriately.
- Keep exposed services updated.
- Avoid exposing sensitive services directly to untrusted networks.
- Investigate unexpected open ports before making changes.

## Results and Findings

Document the actual results of your scan here.

Include:

- Scan date and authorised scope
- Number of hosts discovered, if applicable
- Open ports and identified services
- Potential security concerns
- Recommended mitigations

Do not report assumed results. Update this section after reviewing your scan output.

## Ethical and Legal Disclaimer

This project is intended for educational purposes and authorised security testing only.

Scanning should be limited to devices and networks that you own or have explicit permission to assess. Do not scan third-party networks without authorisation.

## Learning Outcomes

This task provides practical experience with network reconnaissance, TCP port scanning, service identification, Nmap output interpretation, and basic network security.

## Internship

**Organisation:** Elevate Labs  
**Track:** Cybersecurity  
**Task:** Task 1 — Scan Your Local Network for Open Ports

## Author

Vaibhav Barman