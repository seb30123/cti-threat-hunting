# Gap Analysis — LockBit vs MITRE Officiel

**Date :** 2026-03
**Références MITRE :** S1199 (LockBit 2.0), S1202 (LockBit 3.0), S1200 (StealBit)
**Techniques dans ma layer :** 34

---

## Résultats globaux

| Catégorie | Nombre |
|-----------|--------|
| Techniques dans ma layer | 34 |
| Techniques MITRE non couvertes | ~10 |
| Taux de couverture de ma layer | ~35% |

---

## Techniques confirmées par MITRE 

| ID | Technique | Confirmé |
|----|-----------|---------|
| T1566 | Phishing |  MITRE S1202 |
| T1190 | Exploit Public-Facing Application |  CISA + MITRE |
| T1133 | External Remote Services |  CISA |
| T1059.001 | PowerShell |  MITRE S1202 |
| T1059.003 | Windows Command Shell |  CISA |
| T1548.002 | Bypass UAC |  MITRE S1202 |
| T1574.002 | DLL Side-Loading |  MITRE S1202 |
| T1562.009 | Safe Mode Boot |  CISA + MITRE |
| T1070 | Indicator Removal |  CISA |
| T1027 | Obfuscated Files |  MITRE S1202 |
| T1003.001 | LSASS Memory |  arxiv 2025 |
| T1134 | Access Token Manipulation |  arxiv 2025 |
| T1083 | File Discovery |  CISA |
| T1046 | Network Service Discovery |  CISA |
| T1021.002 | SMB/Admin Shares |  CISA + Senseon |
| T1021.001 | RDP |  Senseon |
| T1484.001 | Group Policy Modification |  arxiv 2025 |
| T1041 | Exfil Over C2 |  MITRE S1200 |
| T1560.001 | Archive via Utility |  Senseon |
| T1567.002 | Exfil to Cloud Storage |  Senseon |
| T1020 | Automated Exfiltration |  MITRE S1200 |
| T1219 | Remote Access Software |  Senseon |
| T1071.001 | Web Protocols C2 |  MITRE S1202 |
| T1486 | Data Encrypted for Impact |  CISA + MITRE |
| T1490 | Inhibit System Recovery |  CISA + MITRE |
| T1657 | Financial Threat (leak) |  CISA |
| T1498 | Network DoS (triple extorsion) |  Trend Micro |

---

## Techniques MITRE importantes non couvertes

| ID | Technique | Pourquoi manquée | Où chercher |
|----|-----------|-----------------|-------------|
| T1078 | Valid Accounts | Utilisation credentials volés/achetés — non annoté précisément | CISA AA23-165A p.8 |
| T1055 | Process Injection | Injection dans processus légitimes | DFIR Report analyses |
| T1036 | Masquerading | Renommage outils malveillants | MITRE S1202 exemples |
| T1112 | Modify Registry | Modification registre post-intrusion | CISA Advisory |
| T1490 (variante) | vssadmin + wmic shadow copy delete | Commandes spécifiques non annotées | MITRE S1202 |

---


