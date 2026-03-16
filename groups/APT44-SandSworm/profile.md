# Sandsworm Team - APT44 Profil Complet

## 1. Identité

| Champ | Détail |
|-------|--------|
|Nom Principal | Sandworm Team |
| Aliases | APT44 (Google), ATK14 (Thales), BlackEnergy Group, Blue Echidna (PwC), CTG-7263 (SCWX CTU), ELECTRUM (Dragos), FROZENBARENTS (Google), Hades/OlympicDestroyer (Kaspersky), IRIDIUM (Microsoft), Qudedagh (F-Secure), Sandworm Team (Trend Micro), Seashell Blizzard (Microsoft), Telebots (ESET), TEMP.Noble (FireEye), Voodoo Bear (CrowdStrike) |
| ID MITRE ATT&CK | G0034 |
| Pays d'origine | Russie |
| Entité Commanditaire | GRU -  Unité militaire **74455**, aussi appelée GTsST (Main Center for Special Technologies). |
| Origine du nom | Le nom Sandworm fait référence aux vers dans le roman de Frank Herbert Dune. |
| Niveau de confiance | HIGH - Le 19 octobre 2020, 6 officiers de l'unité 74455 ont été inculpés par le ministère de la justice américaine dans le cadre des cyberattaques attribuées par le groupe contre les JO d'hiver de 2018 |

---

## 2. Victimologie

| Secteur | Priorité |
|---------|----------|
| Infrastructure énergétique IT+OT | ⭐⭐⭐ Critique |
| Gouvernements & militaire (Ukraine, OTAN) | ⭐⭐⭐ Critique |
| Edge & contrôle identité (VPN, FortiGate, AD) | ⭐⭐⭐ Critique |
| Chaîne logistique drones & militaire | ⭐⭐⭐ Critique |
| Télécommunications (satellite, mobile) | ⭐⭐ Élevé |
| Médias & journalisme d'investigation | ⭐⭐ Élevé |
| Processus démocratiques & élections | ⭐⭐ Élevé |
| Organisations sportives | ⭐⭐ Élevé |
| Transport, logistique, manufacturing | ⭐ Modéré |
| Supply chain logicielle | ⭐ Modéré |

**Géographie** : Ukraine (priorité absolue depuis 2014), pays OTAN, USA, France, Pologne, Géorgie. Expansion 2021–2025 : Amérique du Nord, Europe Occidentale, Moyen-Orient (ATI campaign [R29]).

### Lien France
- **2017** — NotPetya : Saint-Gobain ~220M€ pertes
- **2017** — Macron Leaks : activité APT44 identifiée dans le même réseau qu'APT28
- **2024** — Ciblage organisations françaises (rapports ANSSI)
- Classé menace prioritaire par l'ANSSI

---

## 3. Arsenal malveillant (2009–2026)

| Malware | Type | Années | Confiance | Description clé |
|---------|------|--------|-----------|-----------------|
| BlackEnergy | Backdoor/Wiper | 2007–2016 | High | 1ère génération, power grid Ukraine |
| KillDisk | Wiper MBR | 2015–2016 | High | Effacement MBR industriel |
| Industroyer | ICS Wiper | 2016 | High | Modules IEC 60870-5-101/104, IEC 61850, OPC DA + DoS SIPROTEC CVE-2015-5374 |
| NotPetya | Wiper (faux rançongiciel) | 2017 | High | Distribution M.E.Doc, ~10 Mds$ dégâts |
| Olympic Destroyer | Wiper | 2018 | High | False-flag tradecraft JO Pyeongchang |
| VPNFilter | Botnet firmware | 2018 | High | 500 000+ routeurs, 54 pays |
| GreyEnergy / Exaramel | Backdoor | 2018–2021 | High | Successeur BlackEnergy |
| Industroyer2 | ICS Wiper | 2022 | High | Cible-spécifique IEC-104, déployé avec 4 wipers compagnons |
| AcidRain | Wiper modem | 2022 | High | Viasat KA-SAT, J1 invasion Ukraine |
| Cyclops Blink | Botnet firmware | 2019–2022 | High | Persistence firmware WatchGuard/ASUS, masquerading [kworker:0/1] |
| CaddyWiper | IT Wiper | 2022+ | High | Déploiement GPO, campagne Ukraine |
| Kapeka / KnuckleTouch | Backdoor modulaire | 2022–2024 | Medium-High | 3ème génération (→GreyEnergy→Kapeka), AES-256 C2 |
| SwiftSlicer | Wiper Golang | 2023 | Medium-High | Linux/Windows |
| Infamous Chisel | Android RAT | 2023 | High | Militaires ukrainiens (Android), Tor, Dropbear SSH |
| WaveSign | Script interception Signal | 2023–2025 | High | Batch Windows, exfiltration DB Signal locale |
| AcidPour | Wiper embedded | 2024 | Medium | UBI/device-mapper Linux (attribution via Solntsepek — medium) |
| ZEROLOT / Sting / ZOV | IT Wiper rapide | 2024–2026 | Medium-High | Famille itérative, GPO-deployed |
| DynoWiper | IT Wiper | 2025–2026 | Medium-High | Logique petit/grand fichiers, incident Pologne déc. 2025 |
| LazyWiper (KB284726.ps1) | IT Wiper PowerShell | 2025–2026 | Medium-High | Modèle destruction récursif lent |
| CurlyShell / CurlCat | Post-exploitation | 2024+ | Medium | Abus Hyper-V, EDR evasion |
| Prestige | Ransomware (expérimental) | 2022–2024 | Medium | Transport/logistique européen |

---

