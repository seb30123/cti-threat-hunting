# Gap Analysis — APT28 vs MITRE G0007 Officiel

**Date de comparaison :** 2025-03  
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

## Techniques trouvées ET confirmées par MITRE ✅

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

## Techniques trouvées NON confirmées par MITRE ❓

Ces techniques sont dans ma table mais pas dans la layer MITRE. À revalider.

| ID | Technique | Justification | Verdict |
|----|-----------|---------------|---------|
| T1059.003 | Windows Command Shell | Mentionné dans Mandiant APT28 p.18 de façon indirecte — "cmd.exe usage observed" | **MEDIUM** — à garder avec note |
| T1053.005 | Scheduled Task | Microsoft MSTIC 2022 mentionne persistence via scheduled tasks mais ne cite pas APT28 explicitement | **LOW** — à revalider avec une source plus précise |

---

## Techniques MITRE que je n'ai pas trouvées 📘

Sélection des techniques importantes manquées et pourquoi.

| ID | Technique | Pourquoi manquée | Où la trouver |
|----|-----------|-----------------|---------------|
| T1542.001 | System Firmware (LoJax) | Je n'avais pas lu le rapport ESET LoJax 2018 | ESET "LoJax: First UEFI rootkit" (2018) |
| T1014 | Rootkit (Drovorub) | Rapport NSA/FBI non inclus dans mes sources initiales | NSA/FBI Advisory 20-25241601 |
| T1584.008 | Compromise Network Devices | Information récente (2023) absente de mes sources | FBI/CISA Advisory AA23-108A |
| T1071.003 | Mail Protocols (OCEANMAP) | Outil récent (2023) non inclus dans mes sources | ESET "Reading the OCEANMAP" (2023) |
| T1003.001 | LSASS Memory (credential dump) | Comportement indirect, mentionné sans détail dans Mandiant | Mandiant APT28 report p.24 |
| T1560 | Archive Collected Data | Comportement logique mais non annoté dans mes sources | À vérifier dans ESET Sednit Part 3 |

---

## Leçons apprises

1. **Les rapports ESET sur Sednit** (3 parties publiées) sont les sources les plus techniques et les plus riches pour APT28 — à lire en priorité pour la v2 de ce mapping
2. **Les alertes CISA/FBI récentes** (2022-2023) couvrent des TTPs modernes absentes des anciens rapports
3. **OCEANMAP** (C2 via IMAP) montre qu'APT28 adapte ses techniques — important de vérifier les sources récentes
4. Le comportement `cmd.exe` (T1059.003) est difficile à attribuer avec certitude car trop générique

---

## Actions pour la v2 de ce mapping

- [ ] Lire ESET "Sednit" Part 1, 2, 3 (welivesecurity.com)
- [ ] Lire NSA/FBI Advisory sur Drovorub
- [ ] Lire FBI/CISA Advisory AA23-108A (routeurs compromis)
- [ ] Lire ESET OCEANMAP report (2023)
- [ ] Revalider T1053.005 et T1059.003 avec sources précises
- [ ] Passer de 20 à 35+ techniques documentées

---

*Comparaison effectuée manuellement via attack.mitre.org/groups/G0007/ — layer officielle MITRE téléchargeable sur la même page*
