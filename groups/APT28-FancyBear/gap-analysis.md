# Gap Analysis — APT28 vs MITRE G0007 Officiel

**Date de comparaison :** 2026-03  
**Layer MITRE de référence :** attack.mitre.org/groups/G0007/  
**Techniques dans ma layer :** 20  
**Techniques dans la layer MITRE officielle :** ~60 (Enterprise)  

---

## Résultats globaux

| Catégorie | Nombre |
|-----------|--------|
| Techniques trouvées ET confirmées par MITRE | 18 |
| Techniques trouvées NON listées par MITRE (à vérifier) | 2 |
| Techniques MITRE que je n'ai pas trouvées | ~40 |
| Taux de couverture de ma layer | ~30% |

> **Note :** Un taux de 30% est normal pour une première analyse. MITRE compile des années de rapports. L'objectif n'est pas l'exhaustivité mais la rigueur méthodologique.

---

## Techniques trouvées ET confirmées par MITRE 

Ces techniques sont dans ma table ET dans la layer officielle MITRE G0007.

| ID | Technique | Ma source | Source MITRE |
|----|-----------|-----------|--------------|
| T1566.001 | Spearphishing Attachment | ANSSI 2024 | Mandiant 2014, ESET |
| T1566.002 | Spearphishing Link | Microsoft MSTIC | Microsoft MSTIC |
| T1078 | Valid Accounts | MITRE | MITRE G0007 |
| T1059.001 | PowerShell | Microsoft MSTIC | Microsoft MSTIC |
| T1204.002 | Malicious File | ANSSI | ANSSI, Mandiant |
| T1547.001 | Registry Run Keys | ESET | ESET Sednit |
| T1027 | Obfuscated Files | Mandiant | Mandiant APT28 |
| T1036 | Masquerading | CrowdStrike | CrowdStrike |
| T1555.003 | Credentials from Browsers | Mandiant | Mandiant APT28 |
| T1056.001 | Keylogging | Mandiant | Mandiant, MITRE |
| T1021.002 | SMB/Windows Admin Shares | MITRE | MITRE G0007 |
| T1534 | Internal Spearphishing | Microsoft MSTIC | Microsoft MSTIC |
| T1005 | Data from Local System | Mandiant | Mandiant, ANSSI |
| T1114.001 | Local Email Collection | Microsoft MSTIC | ESET, MSTIC |
| T1041 | Exfiltration Over C2 | Mandiant | Mandiant APT28 |
| T1071.001 | Web Protocols | Mandiant | Mandiant APT28 |
| T1573 | Encrypted Channel | ESET | ESET Sednit |
| T1583.001 | Domains | Microsoft MSTIC | Microsoft MSTIC |

---

## Techniques trouvées NON confirmées par MITRE 

Ces techniques sont dans ma table mais pas dans la layer MITRE. À revalider.

| ID | Technique | Justification | Verdict |
|----|-----------|---------------|---------|
| T1059.003 | Windows Command Shell | Mentionné dans Mandiant APT28 p.18 de façon indirecte — "cmd.exe usage observed" | **MEDIUM** — à garder avec note |
| T1053.005 | Scheduled Task | Microsoft MSTIC 2022 mentionne persistence via scheduled tasks mais ne cite pas APT28 explicitement | **LOW** — à revalider avec une source plus précise |

---

*Comparaison effectuée manuellement via attack.mitre.org/groups/G0007/ — layer officielle MITRE téléchargeable sur la même page*
