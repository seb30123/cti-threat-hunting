# CTI Threat Intelligence 

![Status](https://img.shields.io/badge/Status-En%20cours-orange)

Repo Mapping MITRE ATT&CK sur des groupes de hackers réels.  
Chaque dossier contient un profil complet, un tableau de mapping TTPs, une layer ATT&CK Navigator et les sources utilisées.

---

## Groupes analysés

| Groupe | Origine | Motivation | Statut | Techniques mappées |
|--------|---------|------------|--------|-------------------|
| [APT28 / Fancy Bear](./groups/APT28-FancyBear/) |  Russie (GRU) | Espionnage / Sabotage | Complet | 20 |
| [APT44 / Sandsworm Team](./groups/APT44-SandSworm/) |  Russie (GRU) | Sabotage / Espionnage / Extorsion | Complet | 48 |
| LockBit |  International | Cybercrime |  À faire | — |
| Lapsus$ |  UK/Brésil | Extorsion|  À faire | — |
| Noname057 |  Russie | * |  À faire | — |
| LazarusGroup |  Corée du Nord | * |  À faire | — |
| Volt Typhoon |  Chine | * |  À faire | — |
| BlackCat/ ALPHV | * | * |  À faire | — |
| TA505 | * | *|  À faire | — |
| Cl0p | * | * |  À faire | — |
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
|   |   APT28-FancyBear/
|   |   ├── README.md
|   |   ├── profile.md
|   |   ├── ttps-mapping.md
|   |   ├── gap-analysis.md
|   |   ├── navigator-layer.json
|   |   ├── iocs.csv
|   |   └── sources/links.md
│   └── (autres groupes à venir)
└── 
```
 
---
**structure de la construction des fichiers :** 

La création de ces fichiers par groupe  commence par le téléchargement de la matrice MITRE présente dans le fichier [MITRE_ATT&CK_LAYER_EXAMPLE](./groups/APT28-FancyBear/MITRE_ATT&CK_LAYER_EXAMPLE/). Ensuite, nous ajoutons au fur et à mesure les sources que nous trouverons dans le fichier [links.md](./groups/APT28-FancyBear/sources/links.md) pour garder une trace de notre documentation. Après cela, nous allons structurer le contenu du groupe ciblé, au sein de [ttps-mapping.md](./groups/APT28-FancyBear/ttps-mapping.md) que nous avons trouvé sur le site MITRE ATT&CK, ce qui nous permettra de faire une comparaison avec ce que nous avons pu trouver durant les recherches. Tout cela sera présenté dans [gap_analysis.md](./groups/APT28-FancyBear/gap-analysis.md). Il y aura aussi les techniques trouvées durant nos recherches non référencées sur la matrice MITRE. Enfin, nous allons lister l'ensemble des IOCs trouvés dans un fichier csv [iocs.csv](./groups/APT28-FancyBear/iocs.csv) et faire le profil du groupe à l'aide des informations que l'on a récupérés [profile.md](./groups/APT28-FancyBear/profile.md). 


*Toutes les données sont issues de sources publiques.*
