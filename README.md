# Notes


Below are notes that are primarily focused around security, pen testing, and Linux.

# NMAP

NMAP is used to map a host or network to primarily determine what services and ports are available. The simplest nmap command takes an IP, CIDR or DNS name for which to scan.  NMAP can saves to 3 file types:
- .xml / XML file type
- .nmap / standard nmap file
- .gnmap / grepable nmap file

If you use `-oA <scan_filename>` nmap will output to all three of the above file types.

## Scan a CIDR
```
nmap 192.168.1.0/24
```

## Scan 192.168.1.5 for all TCP ports 
-p- all ports (1-65535)

-sS is TCP SYN Scan

```
nmap -p- -sS 192.168.1.5
```


## Scan 192.168.1.5 for all TCP ports, host os, service versions
-p- all ports (1-65535)

-A- Fingerprint host os, get service versions, and script scanning

-sS is TCP SYN Scan

```
nmap -p- -A -sS 192.168.1.5
```

## Scan 192.168.1.5 for all UDP ports 
```
nmap -p- -A -sU 192.168.1.5
```

## Scan 192.168.1.5 for all TCP ports, output to all three file types
```
nmap -p- -A -sT 192.168.1.5 -oA <scan_filename>
```

## Enumerate website via nmap
```
nmap -script http-enum.nse <host>
```
