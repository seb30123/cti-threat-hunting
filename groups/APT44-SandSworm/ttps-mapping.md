# TTPs Mapping — Sandworm Team / APT44

**Dernière mise à jour :** 2026-03
**Evidence cutoff :** 5 mars 2026
**Techniques Enterprise identifiées :** 43
**Techniques ATT&CK for ICS :** 5
**Source primaire :** Pautov 2026 [R1–R30] + MITRE G0034 + recherches complémentaires

---

## Légende

| Niveau | Signification |
|--------|---------------|
| **HIGH** | Comportement explicitement documenté dans source primaire (Observed/Reported) |
| **MEDIUM-HIGH** | Forte convergence multi-sources avec gaps forensiques mineurs |
| **MEDIUM** | Convergence partielle, contradictions non résolues ou source unique |

> **Note APT44** : La concentration de techniques **Impact (T14xx/T15xx)** est le marqueur distinctif du groupe. C'est la principale différence structurelle avec tous les autres APT dans MITRE.

---

## ATT&CK Enterprise

| # | Comportement observé | Source [R#] | Technique ATT&CK | ID | Tactic | Confiance |
|---|---------------------|-------------|------------------|----|--------|-----------|
| 1 | Exploitation de CVE-2014-4114 via documents Office piégés (zero-day) | R9, R15 | Exploit Public-Facing Application | T1190 | Initial Access | HIGH |
| 2 | Exploitation edge software exposé (FortiGate VPN, ConnectWise, Zimbra, Exchange, Confluence, WatchGuard) | R10, R23, R29 | Exploit Public-Facing Application | T1190 | Initial Access | HIGH |
| 3 | Compromission edge infrastructure internet-facing pour accès initial (VPN, firewalls) | R10, R23, R29 | External Remote Services | T1133 | Initial Access | HIGH |
| 4 | Réutilisation/abus credentials locaux sur devices edge/OT | R23 | Valid Accounts: Local Accounts | T1078.003 | Initial Access | HIGH |
| 5 | Distribution de DynoWiper/DcRAT via logiciels piratés trojanisés (KMS activators, supply chain software) | R1, R29 | Supply Chain Compromise: Software | T1195.002 | Initial Access | HIGH |
| 6 | Connexion Wi-Fi aux réseaux d'entreprises voisines de la cible réelle (Nearest Neighbor) | R29 (ATI) | Neighbor Wireless Access | T1669 | Initial Access | HIGH |
| 7 | Scripts PowerShell pour téléchargement/exécution payloads et collecte credentials | R23, CISA | PowerShell | T1059.001 | Execution | HIGH |
| 8 | cmd.exe pour exécution commandes système (vssadmin, cipher, bcdedit, netsh, reg save) | R23 | Windows Command Shell | T1059.003 | Execution | HIGH |
| 9 | WMI pour exécution distante sur systèmes compromis | Mandiant APT44 | WMI | T1047 | Execution | HIGH |
| 10 | Déploiement services système pour exécution distante (PsExec) | R23 | System Services: Service Execution | T1569.002 | Execution | HIGH |
| 11 | Clés de registre Run/RunOnce pour persistence du backdoor | ESET, MITRE G0034 | Registry Run Keys | T1547.001 | Persistence | HIGH |
| 12 | Persistence firmware (Cyclops Blink — survit aux resets device) | R13, R26 | Pre-OS Boot: System Firmware | T1542.001 | Persistence | HIGH |
| 13 | Tâches planifiées Windows pour relancer malware et déployer wipers via GPO | R21, R23 | Scheduled Task/Job | T1053.005 | Persistence | HIGH |
| 14 | Obfuscation PowerShell et code malveillant (suppression historique : Set-PSReadLineOption -HistorySaveStyle SaveNothing) | R23 | Obfuscated Files or Information | T1027 | Defense Evasion | HIGH |
| 15 | Process masquerading Linux : [kworker:0/1] depuis exécutables user-space (Cyclops Blink) | R13 | Masquerading: Match Legitimate Name | T1036.005 | Defense Evasion | HIGH |
| 16 | Injection règles iptables pour ouvrir ports contrôlés par l'attaquant (Cyclops Blink) | R13 | Impair Defenses: Disable/Modify Firewall | T1562.004 | Defense Evasion | HIGH |
| 17 | Modification configuration FortiGate pour persistence et accès | R23 | Impair Defenses: Disable/Modify Network Device Firewall | T1562.013 | Defense Evasion | HIGH |
| 18 | Perturbation outils de sécurité pendant opérations destructrices | R23 | Impair Defenses: Disable or Modify Tools | T1562.001 | Defense Evasion | HIGH |
| 19 | Modification permissions fichiers/répertoires par scripts wipers | R23 | File and Directory Permissions Modification | T1222 | Defense Evasion | HIGH |
| 20 | Suppression/effacement indicateurs par scripts (cleanup post-exfiltration) | R23 | Indicator Removal: File Deletion | T1070.004 | Defense Evasion | HIGH |
| 21 | Capture réseau passive sur edge devices compromis (.pcap / tcpdump) pour interception credentials | R29 | Network Sniffing | T1040 | Credential Access | HIGH |
| 22 | Dump mémoire LSASS pour collecte credentials post-compromise | R23 | OS Credential Dumping: LSASS Memory | T1003.001 | Credential Access | HIGH |
| 23 | Dump NTDS.dit + hives SAM/SYSTEM/SECURITY via reg save et vssadmin | R23 | OS Credential Dumping: NTDS | T1003.003 | Credential Access | HIGH |
| 24 | Abus tickets Kerberos (Diamond Ticket — modification PAC sur TGT légitime chiffré KRBTGT AES256) | R23 | Steal or Forge Kerberos Tickets | T1558 | Credential Access | HIGH |
| 25 | Reconnaissance réseau interne avant stade destructeur | R23 | Network Service Discovery | T1046 | Discovery | HIGH |
| 26 | Collecte informations interfaces réseau et Wi-Fi à portée (Nearest Neighbor) | R29 | System Network Configuration Discovery: Wi-Fi Discovery | T1016.002 | Discovery | HIGH |
| 27 | Déplacement latéral via RDP (Remote Desktop Protocol) | R23, R29 | Remote Desktop Protocol | T1021.001 | Lateral Movement | HIGH |
| 28 | Transfert fichiers et déplacement via SMB (Admin$, C$) | R23 | SMB/Windows Admin Shares | T1021.002 | Lateral Movement | HIGH |
| 29 | Collecte fichiers locaux d'intérêt stratégique | Mandiant APT44 | Data from Local System | T1005 | Collection | HIGH |
| 30 | Compression données collectées (Compress-Archive PowerShell) avant exfiltration | R23 | Archive Collected Data: Archive via Utility | T1560.001 | Collection | HIGH |
| 31 | Vol configuration réseau et données équipements (firewall config dump) | R23 | Data from Config Repository: Network Device Config | T1602.002 | Collection | HIGH |
| 32 | Exfiltration via services cloud publics (Google Drive, Nearest Neighbor) | R23 | Exfiltration Over Web Service: Cloud Storage | T1567 | Exfiltration | HIGH |
| 33 | Exfiltration output scripts via Slack webhook | R23 | Exfiltration Over Web Service: Exfiltration Over Webhook | T1567.004 | Exfiltration | HIGH |
| 34 | C2 via HTTP/HTTPS (ports 80/443) | R13, R14, ESET | Web Protocols | T1071.001 | Command & Control | HIGH |
| 35 | Canal C2 chiffré asymétrique (Cyclops Blink TLS per-message, Kapeka AES-256) | R13, R27 | Encrypted Channel: Asymmetric Crypto | T1573.002 | Command & Control | HIGH |
| 36 | Proxy interne et Tor relay dans chaînes d'incident | R23 | Proxy | T1090 | Command & Control | HIGH |
| 37 | Destruction destructrice wipers famille (KillDisk, NotPetya, AcidRain, CaddyWiper, SwiftSlicer, ZEROLOT, DynoWiper) | R16, R21, R22, R23 | Data Destruction | T1485 | Impact | HIGH |
| 38 | Wipe structure disque et RAID/config (DynoWiper, wiper famille) | R23 | Disk Wipe: Disk Structure Wipe | T1561.002 | Impact | HIGH |
| 39 | Suppression sauvegardes Windows (vssadmin, bcdedit, wbadmin) avant destruction | R2, R11 | Inhibit System Recovery | T1490 | Impact | HIGH |
| 40 | Redémarrage forcé pour complétion wiper | R22, R23 | System Shutdown/Reboot | T1529 | Impact | HIGH |
| 41 | Défacement ~15 000 sites géorgiens + interruption broadcast (2019) | R7, R8 | Defacement: External Defacement | T1491.002 | Impact | HIGH |
| 42 | Déploiement ransomware Prestige contre transport/logistique européen | R1, R27 | Data Encrypted for Impact | T1486 | Impact | Medium |
| 43 | Modification GPO (Default Domain Policy, ScheduledTasks.xml, Files.xml) pour déploiement domain-wide wipers | R2, R21, R23 | Domain Policy Modification: Group Policy | T1484.001 | Impact/Persistence | HIGH |
| 44 | Compromission supply chain M.E.Doc (NotPetya) et developer software Eastern Europe | R1, R4 | Supply Chain Compromise: Software | T1195.002 | Resource Development | HIGH |
| 45 | Création/opération personas hacktivist (CARR, XakNet, Infoccentr) sur Telegram | R1, R25 | Establish Accounts: Social Media | T1585.001 | Resource Development | MEDIUM-HIGH |
| 46 | Masquerade infrastructure (hide infrastructure, relay via compromised third parties) | R23 | Hide Infrastructure | T1665 | Resource Development | HIGH |
| 47 | Ingestion tools/staging chain (.ps1 → .exe déployé via GPO) | R23 | Ingress Tool Transfer | T1105 | Command & Control | HIGH |

---

## ATT&CK for ICS

| # | Comportement observé | Source | Technique ICS | ID ICS | Confiance |
|---|---------------------|--------|---------------|--------|-----------|
| ICS-1 | Exécution commandes OT via CLI contre composants industriels (scilc.exe, arguments non-maintenance) | R3, R23 | Command-Line Interface | T0807 | HIGH |
| ICS-2 | Accès services distants edge-to-OT (FortiGate → management OT) | R23 | External Remote Services | T0822 | HIGH |
| ICS-3 | Module DoS Industroyer ciblant Siemens SIPROTEC via CVE-2015-5374 (paquet UDP 18 bytes → port 50000 → firmware update mode → perte protection) | R15 | Denial of Service | T0835 | HIGH |
| ICS-4 | Corruption firmware RTU (bytes insérés causant reboot loops, factory reset attaquant pour effacer traces) | R23 | Module Firmware | T0839 | HIGH |
| ICS-5 | Connexion à devices automation industriels et RTUs | R23 | Remote Services | T0886 | HIGH |

---

## Techniques récentes 2024–2026 (nouvelles ou mises à jour)

| ID | Technique | Comportement | Source | Première doc |
|----|-----------|-------------|--------|-------------|
| T1669 | Neighbor Wireless Access | Connexion Wi-Fi entreprises voisines pour accès initial sans trace directe | Volexity / ATI [R29] | Nov 2024 |
| T1567.004 | Exfil Over Webhook | Exfiltration output via Slack webhook | CERT Polska [R23] | Déc 2025 |
| T1562.013 | Disable Network Device Firewall | Modification config FortiGate pour persistence | CERT Polska [R23] | Déc 2025 |
| T0839 | Module Firmware (ICS) | Corruption firmware RTU avec reboot loops | CERT Polska [R23] | Déc 2025 |
| T1195.002 | Supply Chain Software | DcRAT via KMS piratés trojanisés | EclecticIQ [R29] | Jan 2025 |

