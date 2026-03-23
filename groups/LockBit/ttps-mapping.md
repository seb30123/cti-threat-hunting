# TTPs Mapping — LockBit

**Dernière mise à jour :** 2026-03
**Evidence cutoff :** Mars 2026
**Techniques identifiées :** 34
**Sources :** CISA AA23-165A, MITRE S1202/S1199, Check Point Research (2025), Senseon, arxiv 2511.06429 (2025)

---


## Légende

| Niveau | Signification |
|--------|---------------|
| **HIGH** | Documenté dans sources primaires (CISA, MITRE, rapports techniques) |
| **MEDIUM** | Documenté dans sources secondaires ou pour une sous-partie des affiliés |

---

## Table de mapping

| # | Comportement observé | Source | Technique ATT&CK | ID | Tactic | Confiance |
|---|---------------------|--------|------------------|----|--------|-----------|
| 1 | Phishing ciblé pour obtenir des credentials initiaux | CISA AA23-165A | Phishing | T1566 | Initial Access | HIGH |
| 2 | Brute force RDP exposé sur internet | CISA, Check Point | Brute Force — Remote Services | T1110.001 | Initial Access | HIGH |
| 3 | Exploitation de vulnérabilités sur services exposés (Fortinet, Apache, Exchange, F5) | CISA AA23-165A | Exploit Public-Facing Application | T1190 | Initial Access | HIGH |
| 4 | Achat d'accès initiaux auprès de courtiers (Initial Access Brokers) sur forums cybercriminels | CISA, Trend Micro | External Remote Services | T1133 | Initial Access | HIGH |
| 5 | Recrutement d'insiders via le site LockBit (annonce dans la ransom note) | MITRE S1199, Trend Micro | Phishing — Spearphishing via Service | T1566.003 | Initial Access | MEDIUM |
| 6 | Exécution de scripts PowerShell pour déployer le ransomware et supprimer les sauvegardes | CISA, MITRE S1202 | PowerShell | T1059.001 | Execution | HIGH |
| 7 | Utilisation de cmd.exe pour exécuter vssadmin, bcdedit et commandes système | CISA Advisory | Windows Command Shell | T1059.003 | Execution | HIGH |
| 8 | Déploiement du ransomware via PsExec ou GPO sur tous les systèmes du domaine | Senseon, arxiv 2025 | System Services: Service Execution | T1569.002 | Execution | HIGH |
| 9 | Clés de registre Run pour maintenir la persistence post-redémarrage | MITRE S1202 | Registry Run Keys | T1547.001 | Persistence | HIGH |
| 10 | Installation d'AnyDesk ou Splashtop comme backdoor d'accès distant persistant | Senseon, CISA | Remote Access Software | T1219 | Persistence | HIGH |
| 11 | Contournement UAC pour exécuter du code avec privilèges élevés via COM interface | MITRE S1202 | Abuse Elevation Control Mechanism: Bypass UAC | T1548.002 | Defense Evasion | HIGH |
| 12 | Exploitation de Windows Defender pour sideloading de Cobalt Strike | MITRE S1202, SOC Prime | Hijack Execution Flow: DLL Side-Loading | T1574.002 | Defense Evasion | HIGH |
| 13 | Redémarrage en Safe Mode pour contourner les solutions de sécurité | CISA AA23-165A, MITRE S1202 | Boot or Logon Autostart: Safe Mode Boot | T1562.009 | Defense Evasion | HIGH |
| 14 | Suppression des logs et indicateurs d'intrusion | CISA Advisory | Indicator Removal | T1070 | Defense Evasion | HIGH |
| 15 | Obfuscation du code et arguments nécessaires à l'exécution (password argument LockBit 3.0) | CISA, MITRE S1202 | Obfuscated Files or Information | T1027 | Defense Evasion | HIGH |
| 16 | Dump des credentials via Mimikatz (LSASS memory) | arxiv 2025, Senseon | OS Credential Dumping: LSASS Memory | T1003.001 | Credential Access | HIGH |
| 17 | Token impersonation pour élévation de privilèges | arxiv 2025 | Access Token Manipulation | T1134 | Credential Access | HIGH |
| 18 | Récupération de credentials depuis les navigateurs ou fichiers locaux | CISA Advisory | Credentials from Password Stores | T1555 | Credential Access | MEDIUM |
| 19 | Enumération des fichiers, partages réseau et trusts de domaine | arxiv 2025, CISA | File and Directory Discovery | T1083 | Discovery | HIGH |
| 20 | Enumération de l'architecture réseau et des systèmes accessibles | CISA AA23-165A | Network Service Discovery | T1046 | Discovery | HIGH |
| 21 | Déplacement latéral via SMB avec Cobalt Strike ou PsExec | CISA, Senseon | SMB/Windows Admin Shares | T1021.002 | Lateral Movement | HIGH |
| 22 | Déplacement via RDP ou Splashtop remote desktop | Senseon, CISA | Remote Desktop Protocol | T1021.001 | Lateral Movement | HIGH |
| 23 | Déploiement de GPOs modifiées pour distribuer le ransomware sur tout le domaine | arxiv 2025, CISA | Domain Policy Modification: Group Policy | T1484.001 | Lateral Movement | HIGH |
| 24 | Exfiltration automatisée avec StealBit (outil maison) vers infra LockBit | MITRE S1199/S1200 | Exfiltration Over C2 Channel | T1041 | Collection | HIGH |
| 25 | Compression des données avec 7-Zip avant exfiltration | Senseon, CISA | Archive Collected Data: Archive via Utility | T1560.001 | Collection | HIGH |
| 26 | Exfiltration vers MEGA ou services de partage cloud légitimes | Senseon, MITRE S1200 | Exfiltration to Cloud Storage | T1567.002 | Exfiltration | HIGH |
| 27 | Exfiltration via StealBit vers C2 LockBit | MITRE S1200 | Automated Exfiltration | T1020 | Exfiltration | HIGH |
| 28 | Upload sur des services de partage publics (Mega, etc.) | Senseon | Exfiltration Over Web Service | T1567 | Exfiltration | HIGH |
| 29 | Utilisation d'AnyDesk comme canal C2 | Senseon, CISA | Remote Access Software | T1219 | Command & Control | HIGH |
| 30 | Cobalt Strike comme framework C2 | MITRE S1202, SOC Prime | Application Layer Protocol: Web Protocols | T1071.001 | Command & Control | HIGH |
| 31 | Chiffrement de tous les fichiers accessibles via ChaCha20 + AES/RSA | CISA, MITRE S1202, arxiv 2025 | Data Encrypted for Impact | T1486 | Impact | HIGH |
| 32 | Suppression des shadow copies et sauvegardes Windows (vssadmin, bcdedit, wbadmin) | CISA, MITRE S1202 | Inhibit System Recovery | T1490 | Impact | HIGH |
| 33 | Publication des données volées sur le data leak site LockBit si rançon non payée | CISA, cas Cannes | Data Leak / Financial Threat | T1657 | Impact | HIGH |
| 34 | DDoS contre la victime en cas de refus de payer (triple extorsion, LockBit 2.0+) | Trend Micro | Network Denial of Service | T1498 | Impact | MEDIUM |

---

## Mapping sur LockBit 5.0 (ChuongDong — sept. 2025)

| Comportement | Technique | Note |
|---|---|---|
| Extensions de fichiers chiffrés aléatoires 16 chars | T1486 | Contournement détection par extension |
| Support natif Windows + Linux + ESXi | T1486 | Multi-plateforme depuis LockBit 5.0 |
| Mécanismes anti-analyse renforcés | T1027 | Obstruction investigation forensique |
| Routines de chiffrement optimisées | T1486 | Réduction fenêtre de réponse défensive |
| Panel d'administration avec credentials individualisés | T1583 | Vetting amélioré des affiliés |
| Dépôt 500$ BTC pour accès panel | T1583 | Modèle exclusivité affiliés |

---


