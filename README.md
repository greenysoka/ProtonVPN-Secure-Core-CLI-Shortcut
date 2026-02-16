# ProtonVPN Privacy CLI Shortcut

This small Bash CLI tool quickly connects to privacy-friendly ProtonVPN servers.

It provides a simple command to connect to random servers in selected privacy-friendly countries or specific Secure Core routes without manually selecting servers every time.

## Modes

1. **Standard Mode (Default):** Connects to a random server in a privacy-friendly country (Switzerland, Iceland, Norway, Sweden, etc.).
2. **Secure Core Mode (`-sc`):** Routes traffic through a hardened Proton-owned server before exiting in another country.

More about Secure Core:
https://protonvpn.com/vpn-servers#secure-core


## Selected privacy-friendly countries

The following countries were selected based on general privacy reputation, legal environment, and history of data-retention policies.  
This is a personal selection, not an official ranking.

- Switzerland – Strong privacy laws, outside the EU, independent legal system.
- Iceland – Very strong freedom of expression and data protection environment.
- Norway – Non-EU country with solid privacy protections and stable legal system.
- Sweden – Secure Core infrastructure location with strong rule of law.
- Romania – Constitutional court repeatedly struck down mandatory data retention laws.
- Finland – Generally strong privacy standards and stable legal framework.
- Estonia – Modern digital infrastructure with transparent governance.
- Luxembourg – Privacy-friendly reputation and stable EU legal environment.


## Secure Core routes used (with `-sc`)

- Austria: CH-AT#2 (to connect to my own country)
- Estonia: SE-EE#1, CH-EE#2
- Luxembourg: CH-LU#2
- Norway: IS-NO#1, SE-NO#1, CH-NO#2
- Finland: SE-FI#1, CH-FI#2
- Romania: SE-RO#1, CH-RO#1, CH-RO#2


## Features

- **One-command connection** to privacy-friendly jurisdictions
- Optional **Secure Core** routing (`-sc`)
- Interactive menu
- Quick disconnect
- Minimal setup


## Usage

**Make the file executable:**

```bash
chmod +x vpn
```


**Run the commands:**

### Connect to a random standard VPN server in preferred countries:
```bash
~$ vpn
```

Example:
```bash
greenysoka@fedora:~$ vpn
Connecting to random server in: LU
Connected to LU#17 in Luxembourg, Luxembourg. Your new IP address is 5.253.204.xx.
greenysoka@fedora:~$
```

---

### Connect to a random Secure Core server:
```bash
~$ vpn -sc
```

Example:
```bash
greenysoka@fedora:~$ vpn -sc
Selected Secure Core Server: CH-NO#2
Connected to CH-NO#2 in Oslo, via Switzerland. Your new IP address is 146.70.170.xx.
greenysoka@fedora:~$
```

---

### Disconnect from the current vpn connection:
```bash
~$ vpn -d
```

Example:
```bash
greenysoka@fedora:~$ vpn -d
Disconnecting from ProtonVPN...
greenysoka@fedora:~$
```

---

### List all selected Servers and Countries:
```bash
~$ vpn -l
```

Example:
```bash
greenysoka@fedora:~$ vpn -l
--- Secure Core Servers ---
CH-AT#2
SE-EE#1
CH-EE#2
CH-LU#2
IS-NO#1
SE-NO#1
CH-NO#2
SE-FI#1
CH-FI#2
SE-RO#1
CH-RO#2

--- Standard Servers ---
CH
IS
NO
SE
RO
FI
EE
LU
greenysoka@fedora:~$
```

---

### Show the current account and your public IP address:
```bash
~$ vpn -s
```

Example:
```bash
greenysoka@fedora:~$ vpn -s
--- VPN Status ---
Account: greenysoka@pm.me
Public IP: 165.231.183.xx
------------------
greenysoka@fedora:~$
```

---

### Get a menu to select a specific VPN route:
```bash
~$ vpn -m
```

Example:
```bash
greenysoka@fedora:~$ vpn -m
1) CH-AT#2    3) CH-EE#2   5) IS-NO#1   7) CH-NO#2   9) CH-FI#2	11) CH-RO#2
2) SE-EE#1    4) CH-LU#2   6) SE-NO#1   8) SE-FI#1  10) SE-RO#1
Select a server number (or 'c' to cancel):
```

---

### Automatically configure your ProtonVPN CLI with the best privacy settings:
```bash
~$ vpn -p
```

Example:
```bash
greenysoka@fedora:~$ vpn -p
Applying maximum privacy settings...
Anonymous crash reports has been set to disabled
IPv6 has been set to disabled
Moderate NAT has been set to disabled
Kill switch has been set to standard
VPN Accelerator has been set to enabled
NetShield has been set to 'malware, ads and trackers'
Custom DNS has been set to disabled
Privacy configuration applied.
greenysoka@fedora:~$
```

---

### Show all these commands in your terminal:
```bash
~$ vpn -h
```

Example:
```bash
greenysoka@fedora:~$ vpn -h
Usage: vpn [option]
Options:
  (none) Connect to a random standard server in preferred countries
  -sc     Connect to a random Secure Core server
  -d     Disconnect VPN
  -l     List servers and countries
  -s     Show connection status and IP
  -m     Selection menu for Secure Core servers
  -p     Apply maximum privacy settings
  -h     Show help information for commands
greenysoka@fedora:~$
```

---

> **Important:** This needs the ProtonVPN CLI installed. My tool is just a shortcut but not the main product.
> Get it here: https://protonvpn.com/support/linux-vpn-setup