# Lazarus Group — Profil Complet

## 1. Identité et attribution

| Champ | Détail |
|-------|--------|
| Type | APT étatique — Corée du Nord (RPDC) |
| Attribution | **RGB (Reconnaissance General Bureau)** — service de renseignement étranger de la Corée Du Nord, sous l'égide de l'Armée Populaire de Corée (General Staff Bureau) |
| Unité militaire | Unit 121 / Bureau 121 — branche cyber du 3e Bureau du RGB |
| Actif depuis | 2009 officiellement documenté (activité possible depuis 2007) |
| Sanctions | Département du Trésor Américain, septembre 2019 |
| Inculpations | Park Jin Hyok (inculpé DOJ 2018, lié à Sony/WannaCry/SWIFT) |

### Problématique du nom "Lazarus Group"

**"Lazarus Group" est un terme qui est devenu généraliste**. On l'utilise souvent pour désigner l'ensemble des opérations cyber nord-coréennes. En réalité, il s'agit de **plusieurs sous-groupes distincts** sous le RGB, partageant infrastructure, malwares et personnel.


---

## 2. Sous-groupes RGB 

| Sous-groupe | Aliases | Spécialité | Victimes types |
|-------------|---------|-----------|----------------|
| **Lazarus (core)** | Labyrinth Chollima, ZINC, Diamond Sleet | Espionnage + sabotage | Sony Pictures, gouvernements, défense |
| **APT38 / Bluenoroff** | Alluring Pisces, Sapphire Sleet, NICKEL GLADSTONE | **Vol financier** (banques) | SWIFT, Bangladesh Bank, banques |
| **Andariel** | Stonefly, Silent Chollima | Cyberespionnage + crypto | Corée du Sud, infrastructures |
| **TraderTraitor** | Jade Sleet, UNC4899 | **Vol crypto** — crypto exchanges | Bybit, Axie Infinity, DMM Bitcoin |
| **Gleaming Pisces** | Citrine Sleet | Crypto (AppleJeus campagne) | Bourses crypto, mineurs |
| **Moonstone Sleet** | Storm-1789 | Nouveau (2024) — ransomware + crypto | Entreprises diverses |
| **Famous Chollima** | DeceptiveDevelopment, Contagious Interview | Fake IT workers + fake job interviews | Développeurs crypto, freelances |
| **BeagleBoyz** | — | ATM cash-out | Banques mondiales |

---

## 3. Motivations

### 3.1 Espionnage
- Vol de technologie militaire (sous-marins, missiles)
- Collecte de renseignement politique sur adversaires (Corée du Sud, USA, Japon)
- Vol de propriété intellectuelle (défense, aérospatiale, nucléaire)
- Ciblage de journalistes et dissidents nord-coréens

### 3.2 Sabotage
- **Sony Pictures 2014** — wiper destructif, 70% des ordinateurs détruits, suite au film The Interview
- **DarkSeoul 2013** — attaques destructrices sur banques/médias sud-coréens
- **WannaCry 2017** — ransomworm mondial — 200 000+ ordinateurs affectés dans 150 pays (NHS UK, Renault France, etc.)
- **Olympic Destroyer 2018** — controverse d'attribution : Sandworm (Russie) s'est fait passer pour Lazarus en false flag

### 3.3 Financier (motivation unique pour un APT étatique)
> **Chiffres clés** :
> - **$6,75 milliards** cumulés volés depuis 2007
> - **$2,02 milliards** volés en 2025 (+51% vs 2024) — **/!\ 60% de tout le vol crypto mondial**
> - **$3,4 milliards** estimés depuis émergence (CSIS)

**Pourquoi l'aspect financier ?**
La RPDC utilise les cyber-vols pour **financer son programme nucléaire et balistique** en contournant les sanctions internationales. C'est un cas unique dans le monde APT : Lazarus est à la fois un APT étatique ET un groupe cybercriminel.

---

## 4. Exemple d'attaque provenant de LazarusGroup : Le Bybit Heist 

### Faits clés
- **Date** : 21 février 2025
- **Victime** : Bybit (Dubai) — 2e plus grande bourse crypto mondiale
- **Montant volé** : **~1,5 milliard $ en Ethereum** (~400 000 ETH)
- **Sous-groupe responsable** : **TraderTraitor** (FBI PSA du 26 fév. 2025)
- **Premier "exercice GDP-scale"** — montant supérieur au PIB de certains États

### Chaîne d'attaque complète

| Jour | Événement |
|------|-----------|
| **J-17 (4 fév. 2025)** | Compromission initiale : phishing/social engineering ciblé sur "Developer1" de Safe{Wallet} (plateforme multisig tierce utilisée par Bybit) |
| J-17 | Installation de malware sur le MacBook du développeur — contrôle complet |
| J-16 à J-1 | Hijacking des tokens de session AWS (bypass MFA) — reconnaissance des patterns Bybit |
| J-0 (21 fév.) | Injection d'une charge JavaScript malveillante spécifiquement pour Bybit dans l'UI Safe{Wallet} |
| J-0 | CEO Ben Zhou autorise ce qui semble être une transaction de routine cold→hot wallet |
| J-0 | Le code modifie l'interface : le CEO signe, mais la transaction est redirigée vers des wallets contrôlés par Lazarus |
| J+1 à J+28 | Laundering : 86,29% des ETH convertis en BTC en 27 jours via DEX, mixers, cross-chain bridges, P2P, money laundering-as-a-service |

### Impact
- **Ethereum** : -20% immédiatement après l'annonce
- **Bitcoin** : passé sous les 90 000 $
- **Retraits massifs** sur toutes les bourses
- **FBI PSA** : 51 adresses Ethereum listées pour blocage
- **Bounty Bybit** : jusqu'à 10% du montant récupéré

---

## 5. Arsenal malware

| Malware | Type | Plateforme | Contexte |
|---------|------|-----------|---------|
| **BeaverTail** | Infostealer + downloader | Windows/macOS/Linux (JS+Qt C++) | Contagious Interview — fake job challenges |
| **InvisibleFerret** | RAT modulaire Python | Multi-plateforme | Stage 2 de BeaverTail |
| **OtterCookie** | Stealer évolution BeaverTail | Multi-plateforme | Extraction tokens auth + wallets crypto |
| **WeaselStore** | Stealer (ClickFix) | Windows/Linux/macOS | Campagne ClickFake Interview 2025 |
| **Tropidoor** | Backdoor avancé | Windows | Basé sur PostNapTea (Lazarus 2022) — lien DeceptiveDevelopment / Lazarus confirmé |
| **TsunamiKit** | Toolkit .NET + Python | Windows | Multi-stage — crypto mining + stealer |
| **GolangGhost** / **PyLangGhost** | Backdoor Go/Python | Multi-plateforme | Campagne ClickFix 2025 |
| **RustBucket** | macOS malware | macOS | AppleJeus — crypto targeting |
| **AppleJeus** | Trojanized trading apps | macOS/Windows | Campagne historique crypto (Gleaming Pisces) |
| **FALLCHILL** | RAT Windows | Windows | HIDDEN COBRA (historique) |
| **HOPLIGHT** | Trojan | Windows | US-CERT MAR-10135536-8 |

### Outils historiques emblématiques
- **Wiper Sony 2014** — destruction de données, liens avec DarkSeoul
- **WannaCry 2017** — ransomworm EternalBlue
- **SWIFT malware (2016)** — utilisé contre Bangladesh Bank (81M$ volés)

---

## 6. Campagnes sociales — Fake IT Workers & Fake Job Interviews

### Operation Dream Job (historique — toujours actif)
Faux profils LinkedIn de recruteurs (Boeing, Lockheed, etc.) → cibles = employés aérospatial/défense → malware via "offres d'emploi"

### Contagious Interview / ClickFake Interview (2023–2025)
- Cibles : **développeurs crypto, freelances Web3**
- Vecteur : faux recruteurs via LinkedIn, Upwork, Freelancer.com, Crypto Jobs List
- Tactique : "defi challenge technique" → repo GitHub/GitLab/Bitbucket piégé → BeaverTail → InvisibleFerret
- Évolution **ClickFix** (2025) : faux CAPTCHAs demandant de copier-coller des commandes curl dans le terminal

### Wagemole / Fake IT Workers (2024–2026)
**Innovation unique** : faux employés IT infiltrés dans entreprises occidentales.
- **Modus operandi** : opérateurs RPDC utilisent de fausses identités (et AI pour visage) → postulent à des postes remote tech → employés → salaires reversés au régime (Exemple de l'ingénieur Nord Coréen à qui l'on a demandé d'insulter Kim Jong Un et qui a quitté l'appel après avoir fait semblant de ne pas comprendre pour ne pas se retrouver en danger dans son pays)
- **+ de 12 entreprises crypto infiltrées en 2024** selon Chainalysis
- **Extension à l'Europe en 2025** : GTIG Google documente Allemagne, Portugal, UK, Italie
- **Exemple** : société blockchain d'Atlanta, +900 000$ volés via insider access de fake IT worker

---

## 7. Attaques historiques majeures

| Année | Cible | Impact | Sous-groupe |
|-------|-------|--------|-------------|
| 2013 | Banques/médias sud-coréens (DarkSeoul) | Wiper destructif | Lazarus core |
| **2014** | **Sony Pictures** | **Wiper, 70% computers détruits, emails leakés** | Lazarus core / Guardians of Peace |
| **2016** | **Bangladesh Bank (SWIFT)** | **Tentative 1Md$, volé 81M$ (typo bloque le reste)** | APT38 / Bluenoroff |
| **2017** | **WannaCry** | **200K+ machines, 150 pays, NHS UK, Renault France** | Lazarus core |
| 2018 | Bancomext Mexico | Tentative vol $110M | APT38 |
| 2018 | JO d'hiver PyeongChang | Olympic Destroyer (false flag Sandworm imitant Lazarus) | — |
| 2018 | Operation Sharpshooter | Ciblage nucléaire/défense mondial | Lazarus core |
| 2020 | Operation Interception | Aerospace européen | Lazarus core |
| 2022 | Axie Infinity (Ronin Bridge) | **$620M crypto volés** | TraderTraitor |
| 2023 | Multiples crypto heists | ~$660M | TraderTraitor, Gleaming Pisces |
| 2024 | DMM Bitcoin (Japon) | **$308M crypto** (collapse de DMM) | TraderTraitor |
| 2024 | Multiples | **$1,3 Mds crypto cumulés** | Plusieurs sous-groupes |
| **Fév. 2025** | **Bybit** | **$1,5 Mds — record absolu** | **TraderTraitor** |
| 2025 | Multiples crypto | **$2,02 Mds cumulés — 60% du vol crypto mondial** | Plusieurs sous-groupes |

---

## 8. Attaques en France

| Date | Contexte | Impact France |
|------|----------|---------------|
| **Mai 2017** | **WannaCry** | **Renault** : usines arrêtées (Sandouville, Douai, Cléon, Batilly) — production impactée plusieurs jours |
| 2017 | WannaCry | Hôpitaux français en alerte (pas d'impact majeur comme au NHS UK, grâce au patch rapide) |
| 2018 | Operation Sharpshooter | Entreprises françaises du nucléaire/défense parmi les cibles globales |
| 2020 | Operation Interception | Aérospatial européen — France potentiellement ciblée (Airbus, Thales) |
| 2023–2025 | Contagious Interview | Développeurs crypto français ciblés via LinkedIn/Upwork |
| 2025 | Wagemole | Entreprises européennes infiltrées (GTIG Google documente Allemagne/UK/Portugal — France probable selon modèle) |

> Note France : La France n'est pas une cible prioritaire de Lazarus comme l'est la Corée du Sud ou les USA. 
---

## 9. Timeline (2007–2026)

| Période | Événement | Statut |
|---------|-----------|--------|
| 2007–2009 | Premières activités documentées | Reported |
| 2013 | DarkSeoul — wiper banques/médias SK | Corroborated |
| **Nov. 2014** | **Sony Pictures Hack** — The Interview | Corroborated (FBI + DOJ indictment 2018) |
| **Fév. 2016** | **Bangladesh Bank SWIFT heist — $81M** | Corroborated |
| **Mai 2017** | **WannaCry** — 150 pays | Corroborated (attribution USA/UK/AU) |
| 2018 | Park Jin Hyok inculpé par DOJ | Corroborated |
| Sept. 2019 | Sanctions OFAC US sur Lazarus, Bluenoroff, Andariel | Corroborated |
| 2022 | Axie Infinity (Ronin Bridge) — $620M | Corroborated (FBI) |
| 2023 | Contagious Interview débute — fake job interviews | Corroborated |
| 2024 | DMM Bitcoin — $308M + Wagemole explosion | Corroborated |
| Oct. 2024 | Début intégration AI dans TTPs Lazarus | Reported |
| **Fév. 2025** | **Bybit — $1,5 Mds — record absolu** | Corroborated (FBI PSA 26 fév. 2025) |
| 2025 | ClickFake Interview + AI voice vishing + expansion Europe | Corroborated (Sekoia, ESET, GTIG) |
| Sept. 2025 | ESET/Virus Bulletin confirme liens DeceptiveDevelopment ↔ Lazarus (Tropidoor/PostNapTea) | Corroborated |
| Déc. 2025 | Total vol crypto 2025 = $2,02 Mds (60% mondial) | Corroborated (Chainalysis) |
| 2026 | Expansion continue, AI-enhanced social engineering | Ongoing |

---

*Sources : MITRE G0032, FBI PSA (26 fév. 2025), Wilson Center, CSIS, Chainalysis Crypto Crime Report, Palo Alto Unit 42 (oct. 2024), ESET Virus Bulletin 2025 (sept. 2025), Sekoia TDR (2025), SentinelOne Labs (sept. 2025), Google Threat Intelligence Group (GTIG), ANY.RUN, Picus Security*
