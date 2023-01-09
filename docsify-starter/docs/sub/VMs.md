# LAB-Umgebung

## Domain Controller

username: vagrant
password: vagrant

### Software

- Google Chrome
- Microsoft Advanced Threat Analytics Gateway
- Microsoft Visual C++ 2013 Redistributable (x64)
- Microsoft Visual C++ 2015-2022 Redistributable (x64)
- Microsoft Visual C++ 2015-2022 Redistributable (x86)
- Notepad++ (64-bit x64)
- Velociraptor
- WinRAR (64-bit)
- Wireshark 64-bit

- Server Manager:
    - AD DS
    - DNS
    - File and Storage Services
    - IIS
    - WSUS

## wef

username: vagrant
password: vagrant

### Software

- Google Chrome
- Microsoft Advanced Threat Analytics Gateway
- Microsoft Visual C++ 2013 Redistributable (x64)
- Microsoft Visual C++ 2015-2022 Redistributable (x64)
- Microsoft Visual C++ 2015-2022 Redistributable (x86)
- Notepad++ (64-bit x64)
- Velociraptor
- WinRAR (64-bit)
- Wireshark 64-bit

## logger

username: vagrant
password: vagrant

### Software

- Fleet Kolide
- Kibana
- Elasticsearch

# Netzwerk

```plantuml
@startuml

object DC
DC : hostname: dc
DC : ip: 10.0.2.11
DC : host-only-ip: 192.168.38.102

object WEF
WEF : hostname: wef
WEF : ip: 10.0.2.12
WEF : host-only-ip: 192.168.38.103

object Logger
Logger : hostname: logger
Logger : ip: 10.0.2.5
Logger : host-only-ip: 192.168.38.105

@enduml
```