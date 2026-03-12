# TTPs Mapping — APT28 / Fancy Bear

**Dernière mise à jour :** 2025-03  
**Techniques identifiées :** 20  
**Sources utilisées :** MITRE G0007, ANSSI CERT-FR, Mandiant APT28 (2014), Microsoft MSTIC (Forest Blizzard), ESET, CrowdStrike  

---

## Légende — Niveaux de confiance

| Niveau | Signification |
|--------|---------------|
| **HIGH** | Comportement explicitement décrit dans au moins une source primaire |
| **MEDIUM** | Comportement fortement suggéré ou documenté dans une source secondaire |
| **LOW** | Comportement supposé ou déduit par analyse technique indirecte |

---

## Table de mapping

| # | Comportement observé | Source | Technique ATT&CK | ID | Tactic | Confiance |
|---|---------------------|--------|------------------|----|--------|-----------|
| 1 | Envoi d'emails ciblés avec pièces jointes Word/PDF contenant des macros VBA malveillantes | ANSSI 2024, Mandiant 2014 | Spearphishing Attachment | T1566.001 | Initial Access | HIGH |
| 2 | Envoi de liens vers des pages de phishing imitant Outlook, Google Drive ou OneDrive | Microsoft MSTIC 2023 | Spearphishing Link | T1566.002 | Initial Access | HIGH |
| 3 | Utilisation de credentials volés (phishing ou dark web) pour accéder directement aux systèmes | MITRE G0007, CrowdStrike | Valid Accounts | T1078 | Initial Access | HIGH |
| 4 | Exécution de scripts PowerShell encodés en base64 pour télécharger et lancer des payloads | Microsoft MSTIC, ESET | PowerShell | T1059.001 | Execution | HIGH |
| 5 | Utilisation de cmd.exe pour exécuter des commandes système et des scripts batch malveillants | Mandiant APT28 | Windows Command Shell | T1059.003 | Execution | MEDIUM |
| 6 | Incitation des victimes à ouvrir un fichier piégé (macro VBA, fichier LNK, document Office) | ANSSI, Mandiant | Malicious File | T1204.002 | Execution | HIGH |
| 7 | Ajout de clés de registre Run/RunOnce pour relancer le malware après redémarrage | ESET Sednit, Mandiant | Registry Run Keys / Startup Folder | T1547.001 | Persistence | HIGH |
| 8 | Création de tâches planifiées Windows (Scheduled Tasks) pour maintenir la persistance | Microsoft MSTIC | Scheduled Task/Job | T1053.005 | Persistence | MEDIUM |
| 9 | Obfuscation du code malveillant (chiffrement XOR, encodage base64) pour contourner les AV | Mandiant, ESET | Obfuscated Files or Information | T1027 | Defense Evasion | HIGH |
| 10 | Renommage des exécutables malveillants avec des noms de processus légitimes (svchost, winlogon) | CrowdStrike, ESET | Masquerading | T1036 | Defense Evasion | MEDIUM |
| 11 | Vol de mots de passe stockés dans les navigateurs Chrome, Firefox via X-Agent | Mandiant APT28, MITRE | Credentials from Password Stores — Browsers | T1555.003 | Credential Access | HIGH |
| 12 | Enregistrement des frappes clavier via le module keylogger de X-Agent | Mandiant APT28, ANSSI | Input Capture — Keylogging | T1056.001 | Credential Access | HIGH |
| 13 | Déplacement latéral via les partages administratifs Windows (SMB/Admin$) | MITRE G0007 | SMB/Windows Admin Shares | T1021.002 | Lateral Movement | MEDIUM |
| 14 | Envoi d'emails de phishing depuis un compte interne compromis pour toucher d'autres employés | Microsoft MSTIC 2022 | Internal Spearphishing | T1534 | Lateral Movement | MEDIUM |
| 15 | Collecte de fichiers locaux (documents bureautiques, PDFs) d'intérêt stratégique | Mandiant, ANSSI | Data from Local System | T1005 | Collection | HIGH |
| 16 | Collecte des emails via accès direct au profil Outlook local ou Exchange | ESET, Microsoft MSTIC | Local Email Collection | T1114.001 | Collection | HIGH |
| 17 | Exfiltration des données collectées via le canal C2 chiffré de X-Agent | Mandiant APT28, ESET | Exfiltration Over C2 Channel | T1041 | Exfiltration | HIGH |
| 18 | Communications C2 utilisant HTTP/HTTPS sur ports 80/443 pour paraître comme du trafic légitime | Mandiant, Microsoft MSTIC | Web Protocols | T1071.001 | Command & Control | HIGH |
| 19 | Chiffrement des communications C2 pour échapper à l'inspection réseau (X-Tunnel) | ESET Sednit, Mandiant | Encrypted Channel | T1573 | Command & Control | HIGH |
| 20 | Enregistrement de domaines imitant des organisations légitimes (typosquatting, lookalike) | Microsoft MSTIC, CrowdStrike | Domains | T1583.001 | Resource Development | HIGH |

---

## Techniques à approfondir (identifiées dans les sources mais non encore mappées)

Ces techniques apparaissent dans les sources mais demandent une analyse plus poussée avant d'être ajoutées avec confiance :

- **LoJax — UEFI Rootkit** → probablement T1542.001 (System Firmware) — source : ESET 2018
- **Drovorub (Linux rootkit)** → probablement T1014 (Rootkit) — source : NSA/FBI Advisory 2020
- **Utilisation de routeurs SOHO comme relais** → probablement T1584.008 (Compromise Infrastructure — Network Devices) — source : FBI/CISA 2023
- **OCEANMAP (C2 via IMAP)** → probablement T1071.003 (Mail Protocols) — source : ESET 2023

---

*Ce tableau est volontairement non exhaustif — APT28 utilise 50+ techniques documentées. L'objectif est d'illustrer la méthodologie de mapping, pas d'être une référence complète.*
