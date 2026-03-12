# CTI Threat Intelligence 

![Status](https://img.shields.io/badge/Status-En%20cours-orange)

Repo Mapping MITRE ATT&CK sur des groupes de hackers réels.  
Chaque dossier contient un profil complet, un tableau de mapping TTPs, une layer ATT&CK Navigator et les sources utilisées.

---

## Groupes analysés

| Groupe | Origine | Motivation | Statut | Techniques mappées |
|--------|---------|------------|--------|-------------------|
| [APT28 / Fancy Bear](./groups/APT28-FancyBear/) | 🇷🇺 Russie (GRU) | Espionnage | 🔄 En cours | - |
| Sandworm |  Russie (GRU) | Sabotage | ⬜ À faire | — |
| LockBit |  International | Cybercrime | ⬜ À faire | — |
| Lapsus$ |  UK/Brésil | Extorsion| ⬜ À faire | — |
| Noname057 |  Russie | * | ⬜ À faire | — |
| LazarusGroup |  Corée du Nord | * | ⬜ À faire | — |
| Volt Typhoon |  Chine | * | ⬜ À faire | — |
| BlackCat/ ALPHV | * | * | ⬜ À faire | — |
| TA505 | * | *| ⬜ À faire | — |
| Cl0p | * | * | ⬜ À faire | — |
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



*Toutes les données sont issues de sources publiques TLP:WHITE.*
