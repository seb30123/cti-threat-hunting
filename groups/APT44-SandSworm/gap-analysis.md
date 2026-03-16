# Gap Analysis — Sandworm APT44 vs MITRE G0034

**Date :** 2026-03
**Layer MITRE référence :** attack.mitre.org/groups/G0034/
**Techniques dans ma layer :** 43 Enterprise + 5 ICS = 48

---

## Résultats globaux

| Catégorie | Nombre |
|-----------|--------|
| Techniques Enterprise dans ma layer | 43 |
| Techniques ICS dans ma layer | 5 |
| Confirmées par MITRE G0034 | ~38 |
| Issues de sources 2024–2026 (non encore dans MITRE) | 5 |
| Techniques MITRE que je n'ai pas couvertes | ~35+ |
| Taux de couverture Enterprise | ~55% |


---

## Apport exclusif des sources 2024–2026

Ces techniques **n'existaient pas ou n'étaient pas attribuées à APT44** dans les versions antérieures de MITRE :

| ID | Technique | Comportement documenté | Source | Date |
|----|-----------|----------------------|--------|------|
| T1669 | Neighbor Wireless Access | Connexion Wi-Fi entreprises voisines pour Initial Access sans trace réseau directe | Volexity "Nearest Neighbor" | Nov 2024 |
| T1567.004 | Exfiltration Over Webhook | Output scripts exfiltrés via Slack webhook | CERT Polska | Déc 2025 |
| T1562.013 | Disable Network Device Firewall | Modification config FortiGate pour persistence | CERT Polska | Déc 2025 |
| T0839 | ICS Module Firmware | Corruption firmware RTU (reboot loops, factory reset anti-forensics) | CERT Polska | Déc 2025 |
| T1195.002 (nouveau contexte) | Supply Chain Software | Distribution DcRAT via KMS piratés trojanisés en Ukraine | EclecticIQ | Jan 2025 |

---

## Point de vigilance : Incident Pologne décembre 2025

**ESET** attribue DynoWiper à Sandworm avec **confiance moyenne**.
**CERT Polska** documente un chevauchement avec l'infrastructure historiquement trackée comme Berserk Bear (CrowdStrike), Ghost Blizzard (Microsoft), Dragonfly/TEMP.Isotope (Symantec/Secureworks), Static Tundra.

> Ces labels représentent des **modèles de tracking différents** pour un cluster d'activités chevauchant — pas un groupe unique formellement attribué. Maintenir la divergence d'attribution explicite dans le confidence modeling. Les TTPs restent prioritaires indépendamment du label final.

---

## Techniques confirmées par MITRE 

| ID | Technique | Source | 
|----|-----------|-----------|
| T1190 | Exploit Public-Facing Application | R9, R10, R23, R29 |  
| T1133 | External Remote Services | R10, R23 | 
| T1195.002 | Supply Chain Compromise | R1, R4 | 
| T1059.001 | PowerShell | R23, CISA | 
| T1059.003 | Windows Command Shell | R23 | 
| T1047 | WMI | Mandiant | 
| T1542.001 | System Firmware | R13, R26 | 
| T1547.001 | Registry Run Keys | ESET | 
| T1053.005 | Scheduled Task | R21, R23 | 
| T1036.005 | Masquerading | R13 | 
| T1027 | Obfuscated Files | R23, Mandiant | 
| T1562.004 | Disable/Modify Firewall | R13 |
| T1040 | Network Sniffing | R29 | 
| T1003.001 | LSASS Memory | R23 | 
| T1003.003 | NTDS.dit | R23 | 
| T1558 | Kerberos Ticket Abuse | R23 | 
| T1021.001 | RDP | R23, R29 | 
| T1021.002 | SMB/Windows Admin Shares | R23 | 
| T1560.001 | Archive via PowerShell | R23 | 
| T1567 | Exfil Cloud Storage | R23 | 
| T1071.001 | Web Protocols C2 | R13, R14 | 
| T1573.002 | Encrypted Channel | R13, R27 | 
| T1090 | Proxy | R23 | 
| T1485 | Data Destruction | R16, R21–R23 | 
| T1561.002 | Disk Structure Wipe | R23 | 
| T1490 | Inhibit System Recovery | R2, R11 | 
| T1529 | System Shutdown/Reboot | R22, R23 | 
| T1491.002 | External Defacement | R7, R8 | 
| T1484.001 | Domain Policy Modification | R2, R21, R23 |
| T1486 | Data Encrypted for Impact | R1, R27 | 
| T1005 | Data from Local System | Mandiant | 
| T1046 | Network Service Discovery | R23 | 
| T1105 | Ingress Tool Transfer | R23 |
| T1602.002 | Network Device Config | R23 |

---

## Techniques MITRE non présente 

| ID | Technique | Pourquoi manquée | Source |
|----|-----------|-----------------|-------------|
| T1078 | Valid Accounts (général) | Comportement présent mais non annoté précisément | Mandiant APT44 p.15, CISA |
| T1566.001 | Spearphishing Attachment | Documenté mais non extrait dans cette analyse | CERT-UA, ESET, MITRE G0034 |
| T1553 | Code Signing / Trust | Kapeka utilise du code signé pour éviter les AV | WithSecure [R27] |
| T1070.003 | Clear Command History | Comportement anti-forensics adjacent à T1027 | R23 CERT Polska |
| T1046 | Network Scanning (complet) | Partiellement couvert | Nearest Neighbor [R29] |
| T1083 | File and Directory Discovery | Reconnaissance locale documentée | CERT-UA rapports |

---
