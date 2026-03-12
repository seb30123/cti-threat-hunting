# CTI Threat Intelligence — Projet 5

![ATT&CK](https://img.shields.io/badge/MITRE%20ATT%26CK-v14-red)
![License](https://img.shields.io/badge/License-TLP%3AWHITE-white)
![Status](https://img.shields.io/badge/Status-En%20cours-orange)

Repo d'apprentissage CTI — Mapping MITRE ATT&CK sur des groupes de hackers réels.  
Chaque dossier contient un profil complet, un tableau de mapping TTPs, une layer ATT&CK Navigator et les sources utilisées.

---

## Groupes analysés

| Groupe | Origine | Motivation | Statut | Techniques mappées |
|--------|---------|------------|--------|-------------------|
| [APT28 / Fancy Bear](./groups/APT28-FancyBear/) | 🇷🇺 Russie (GRU) | Espionnage | ✅ Complet | 20 |
| Sandworm | 🇷🇺 Russie (GRU) | Sabotage | 🔄 En cours | — |
| LockBit | 🌍 International | Cybercrime | ⬜ À faire | — |
| Lapsus$ | 🇬🇧 UK/Brésil | Extorsion | ⬜ À faire | — |

---

## Structure du repo

```
cti-threat-intelligence/
├── README.md                        ← Ce fichier
├── groups/
│   ├── APT28-FancyBear/
│   │   ├── README.md
│   │   ├── profile.md
│   │   ├── ttps-mapping.md
│   │   ├── gap-analysis.md
│   │   ├── navigator-layer.json
│   │   ├── iocs.csv
│   │   └── sources/links.md
│   └── (autres groupes à venir)
└── templates/
    ├── group-profile-template.md
    ├── ttps-mapping-template.md
    └── iocs-template.csv
```

---

## Méthodologie

1. Lire les sources officielles (MITRE, ANSSI, Mandiant, Microsoft MSTIC)
2. Extraire les comportements bruts
3. Mapper chaque comportement → technique ATT&CK avec niveau de confiance
4. Créer la layer ATT&CK Navigator
5. Comparer avec la layer officielle MITRE (gap analysis)

---

*Toutes les données sont issues de sources publiques TLP:WHITE. Usage pédagogique uniquement.*
