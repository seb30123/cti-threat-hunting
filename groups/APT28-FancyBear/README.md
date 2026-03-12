# APT28 / Fancy Bear — CTI Profile

![ATT&CK](https://img.shields.io/badge/MITRE%20ATT%26CK-G0007-red)
![Confidence](https://img.shields.io/badge/Attribution-HIGH-red)
![Status](https://img.shields.io/badge/Status-Active-orange)
![TLP](https://img.shields.io/badge/TLP-WHITE-white)

| Champ | Valeur |
|-------|--------|
| **Nom officiel** | APT28 |
| **Aliases** | Fancy Bear, Sofacy, STRONTIUM, Forest Blizzard, Sednit, Pawn Storm |
| **ID MITRE** | [G0007](https://attack.mitre.org/groups/G0007/) |
| **Origine supposée** | Russie — GRU (Direction du renseignement militaire), Unité 26165 |
| **Actif depuis** | ~2004 (documenté publiquement dès 2007) |
| **Motivation** | Espionnage politique et militaire, désinformation, vol de données stratégiques |
| **Affiliation étatique** | HIGH — attributions officielles FR, UK, US, UE, OTAN |

---

## Résumé

APT28 est un groupe de cyberespionnage étatique russe considéré comme l'une des menaces les plus sophistiquées et les plus actives au monde. Actif depuis au moins 2004, le groupe opère au profit du renseignement militaire russe (GRU) et cible principalement les gouvernements, organisations de défense, médias et entités politiques des pays membres de l'OTAN.

En France, le groupe est suivi de près par l'ANSSI qui lui a officiellement attribué plusieurs campagnes ciblant des administrations, des acteurs de la défense, et des organisations liées aux Jeux Olympiques de Paris 2024.

---

## Fichiers de ce profil

| Fichier | Description |
|---------|-------------|
| [`profile.md`](./profile.md) | Profil détaillé : origine, victimologie, infrastructure, timeline |
| [`ttps-mapping.md`](./ttps-mapping.md) | Tableau de mapping comportements → techniques ATT&CK |
| [`gap-analysis.md`](./gap-analysis.md) | Comparaison avec la layer officielle MITRE |
| [`navigator-layer.json`](./navigator-layer.json) | Layer ATT&CK Navigator exportée |
| [`iocs.csv`](./iocs.csv) | IOCs publiquement documentés |
| [`sources/links.md`](./sources/links.md) | Toutes les sources utilisées |

---

## Techniques ATT&CK — Résumé

| Tactic | Nb techniques identifiées |
|--------|--------------------------|
| Initial Access | 3 |
| Execution | 3 |
| Persistence | 2 |
| Defense Evasion | 2 |
| Credential Access | 2 |
| Lateral Movement | 2 |
| Collection | 2 |
| Exfiltration | 1 |
| Command & Control | 2 |
| Resource Development | 1 |
| **TOTAL** | **20** |

---

*Dernière mise à jour : 2025-03 | Sources : MITRE G0007, ANSSI, Mandiant, Microsoft MSTIC*
