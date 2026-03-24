# LockBit — CTI Profile


| Champ | Valeur |
|-------|--------|
| **Nom** | LockBit |
| **Aliases** | ABCD (2019), LockBit Red (2.0), LockBit Black (3.0), LockBit Green, LockBit Neo (4.0), ChuongDong (5.0) |
| **Type** | Ransomware-as-a-Service (RaaS) — Cybercriminel pur |
| **ID MITRE** | [S1202 (LockBit 3.0)](https://attack.mitre.org/software/S1202/) / [S1199 (LockBit 2.0)](https://attack.mitre.org/software/S1199/) |
| **Leader identifié** | Dmitry Yuryevich Khoroshev, alias LockBitSupp / putinkrab (démasqué mai 2024) |
| **Actif depuis** | Septembre 2019 |
| **Motivation** | Extorsion financière |
| **Modèle** | RaaS : LockBit fournit l'infra + le ransomware, les affiliés attaquent et partagent les rançons |
| **Version actuelle** | **LockBit 5.0 "ChuongDong"** (septembre 2025) |

**Lockbit étant de nouveau actif, il n'y a toujours pas de profil effectué sur Lockbit 5.0 sur Mitre**
## Résumé

LockBit est le groupe RaaS le plus prolifique jamais documenté. Entre 2021 et 2024, il représentait 20 à 30% de toutes les attaques ransomware mondiales. La France est le **3e pays le plus ciblé** dans le monde. Malgré l'Opération Cronos (fév. 2024), LockBit est revenu avec LockBit 5.0 en septembre 2025, revendiquant 96 attaques en décembre 2025 seul.

## Fichiers

| Fichier | Description |
|---------|-------------|
| `profile.md` | Identité, leadership, victimologie, France, timeline, arsenal |
| `ttps-mapping.md` | Techniques ATT&CK mappées avec sources |
| `gap-analysis.md` | Comparaison MITRE officiel |
| `navigator-layer.json` | Layer ATT&CK Navigator |
| `iocs.csv` | IOCs documentés |
| `sources/links.md` | Sources complètes |
| `LockBit_CTI_Report.pdf` | Rapport PDF complet |

## Techniques ATT&CK — Résumé

| Tactic | Nb |
|--------|----|
| Initial Access | 5 |
| Execution | 3 |
| Persistence | 2 |
| Defense Evasion | 5 |
| Credential Access | 3 |
| Discovery | 2 |
| Lateral Movement | 3 |
| Collection | 2 |
| Exfiltration | 3 |
| Command & Control | 2 |
| Impact | 4 |
| **TOTAL** | **34** |

*Actualisation : mars 2026*
