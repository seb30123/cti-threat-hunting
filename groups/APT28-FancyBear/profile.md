# APT28 — Profil Complet

## 1. Identité

| Champ | Détail |
|-------|--------|
| Nom principal | APT28 |
| Aliases | Fancy Bear (CrowdStrike), Sofacy (Kaspersky), STRONTIUM / Forest Blizzard (Microsoft), Sednit (ESET), Pawn Storm (Trend Micro), Tsar Team (iSight) |
| ID MITRE ATT&CK | G0007 |
| Pays d'origine | Russie |
| Entité commanditaire | GRU — Direction principale du renseignement de l'état-major des forces armées russes, unité militaire 26165 (et 74455 pour Sandworm, groupe cousin) |
| Niveau de confiance attribution | HIGH — attributions gouvernementales officielles (USA DoJ 2018, NCSC UK 2018, ANSSI FR 2024, Conseil UE 2020) |

---

## 2. Motivation et objectifs

APT28 opère exclusivement au profit des intérêts stratégiques russes. Ses objectifs documentés :

- **Espionnage politique** : infiltration de gouvernements, partis politiques, think-tanks pour voler des informations stratégiques
- **Espionnage militaire** : ciblage de l'OTAN, ministères de la défense, industries d'armement
- **Désinformation et influence** : vol de données puis publication sélective pour nuire à des personnalités ou organisations (opération Macron Leaks 2017, DNC Leaks 2016)
- **Sabotage ciblé** : perturbation d'organisations sportives (WADA, JO) en réponse aux sanctions antidopage

---

## 3. Victimologie

### Secteurs ciblés

| Secteur | Exemples | Priorité |
|---------|----------|----------|
| Gouvernements & administrations | Ministères FR, UE, USA, Ukraine | ⭐⭐⭐ Critique |
| Défense & industrie militaire | OTAN, contractants défense | ⭐⭐⭐ Critique |
| Partis politiques | DNC (USA), En Marche! (FR), CDU (DE) | ⭐⭐⭐ Critique |
| Médias & journalistes | TV5 Monde (FR), Deutsche Welle | ⭐⭐ Élevé |
| Organisations sportives | WADA, Comités olympiques, fédérations | ⭐⭐ Élevé |
| Think-tanks & ONG | Atlantic Council, organisations droits de l'homme | ⭐⭐ Élevé |
| Infrastructure critique | Énergie, télécommunications | ⭐ Modéré |

### Zones géographiques ciblées

Principalement : **USA, France, Allemagne, Ukraine, pays OTAN**
Secondairement : Géorgie, Pays-Bas, Espagne, Royaume-Uni

---

## 4. Lien avec la France

APT28 est l'un des groupes représentant la plus grande menace pour la France selon l'ANSSI.

**Incidents documentés impliquant la France :**

- **2015** — TV5 Monde : attaque destructrice contre le diffuseur public français, attribution officielle APT28 par l'ANSSI en 2017
- **2017** — Opération Macron Leaks : vol et fuite de données de la campagne d'Emmanuel Macron, attributé à APT28 avec haute confiance
- **2023-2024** — Campagnes de spearphishing ciblant des administrations françaises documentées par l'ANSSI
- **2024** — Ciblage d'organisations liées aux Jeux Olympiques de Paris (ANSSI — CERT-FR alerte TLP:WHITE)

---

## 5. Infrastructure

APT28 utilise une infrastructure sophistiquée et éphémère :

- **Domaines** : imitent des services légitimes (microsoft-update[.]com, secure-login[.]org) avec des patterns cohérents par campagne
- **Hébergeurs** : fournisseurs permettant l'anonymisation (OVH FR, DigitalOcean, VPS anonymes crypto)
- **C2** : communication chiffrée via HTTPS, souvent sur des ports standards pour passer inaperçu
- **VPN / Proxies** : utilisation systématique de nœuds de sortie pour masquer l'origine réelle
- **Compromission de routeurs** : depuis 2023, APT28 utilise des routeurs SOHO compromis comme relais C2 (documenté par FBI/CISA)

---

## 6. Malwares et outils associés

| Outil | Type | Description |
|-------|------|-------------|
| X-Agent (Sofacy) | RAT | Outil principal — keylogger, accès distant, exfiltration |
| X-Tunnel | Tunnel | Chiffrement des communications C2 |
| Zebrocy | Downloader/RAT | Utilisé en phases initiales, récupère X-Agent |
| LoJax | UEFI Rootkit | Premier rootkit UEFI documenté in-the-wild (APT28 2018) |
| Drovorub | Linux implant | Rootkit Linux (documenté NSA/FBI 2020) |
| Komplex | macOS RAT | Ciblage des systèmes macOS |
| OCEANMAP | Backdoor | Utilisé via IMAP pour les communications C2 (post-2023) |

---

## 7. Timeline des campagnes majeures

| Année | Campagne | Cible(s) | Impact |
|-------|----------|----------|--------|
| 2014 | APT28 First Exposure | Gouvernements OTAN | Mandiant publie le premier rapport public |
| 2015 | TV5 Monde | Média public français | Destruction de données, canaux TV coupés |
| 2016 | DNC Hack | Parti démocrate américain | Fuite massive, influence élection présidentielle |
| 2017 | Macron Leaks | Campagne présidentielle FR | Fuite de 9 Go de données internes |
| 2018 | WADA Leaks | Agence mondiale antidopage | Publication de données médicales d'athlètes |
| 2020 | COVID Research | Labos vaccins UK/CA/US | Tentatives de vol de recherches COVID-19 |
| 2022-23 | Ukraine Operations | Gouvernement ukrainien | Espionnage et sabotage en contexte de guerre |
| 2024 | JO Paris 2024 | Comité olympique, administrations FR | Campagnes de phishing documentées ANSSI |

---

*Sources : MITRE ATT&CK G0007, ANSSI, Mandiant APT28 2014, Microsoft MSTIC, NCSC UK, CrowdStrike*
