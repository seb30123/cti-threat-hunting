# Lapsus$ — Profil Complet

## 1. Identité

| Champ | Détail |
|-------|--------|
| Type | Groupe d'extorsion cybercriminel — vol de données + chantage |
| Origine | UK + Brésil — membres dispersés internationalement |
| Actif | Juin 2021 — Septembre 2022 (core group) / 2025–2026 via SLH  |
| Taille estimée | 7 à 11 membres core. Structure très lâche, recrutement ad hoc., Lapsus$ est aujourd'hui devenu une marque, plusieurs personnes s'identifient comme en faisant partie. |


### Spécificité du groupe Lapsus$ 

1. **Pas de malware sophistiqué** — utilisent des techniques connues et disponibles publiquement
2. **Membres adolescents** — âgés de 16 à 21 ans au moment des attaques
3. **Aucun exploit 0-day documenté** — 100% social engineering et abus d'identité (*voir le Telegram de Lapsus$ avec un recrutement fait dessus, référence section 3*)
4. **Totalement publics** — annoncent leurs attaques, publient des données, organisent des sondages sur Telegram pour choisir leur prochaine cible
5. **Recrutement d'insiders** — approchent directement les employés des cibles pour acheter des accès
6. **Ont réussi là où des groupes étatiques auraient eu du mal** — compromission de Microsoft, Nvidia, Okta, Uber simultanément en quelques semaines

---

## 2. Membres identifiés

| Alias | Identité réelle | Nationalité | Rôle | Statut légal |
|-------|-----------------|-------------|------|--------------|
| **White** / **breachbase** | **Arion Kurtaj** | UK | Membre central, Uber + Rockstar hacks | Déclaré inapte au procès pour autisme. **Internement psychiatrique indéfini** (déc. 2023). Exprime le souhait de reprendre dès que possible. |
| — | Mineur (17 ans, non identifié) | UK | Membre central | 18 mois Rehabilitation Order + 3 mois supervision intensive (déc. 2023) |
| — | 5 autres mineurs/jeunes adultes | UK | Membres | Arrêtés mars 2022, âgés de 16 à 21 ans |
| — | Mineur brésilien | Brésil | Membre | Arrêté octobre 2022, lié aux attaques gouvernementales brésiliennes |
| **okta-admin** | Non identifié | — | Accès Okta | Non arrêté |

> **Note sur Arion Kurtaj :** Arrêté une première fois en mars 2022, relâché sous caution, a continué à hacker depuis un Holiday Inn où il était hébergé par la police (y compris le hack de Rockstar Games avec une télévision, un téléphone et un Chromecast).

---

## 3. Doctrine opérationnelle

### Le fonctionnement de Lapsus$ est présenté en 5 étapes

**1. Reconnaissance et ciblage des insiders**
Lapsus$ ne commence pas par attaquer le réseau. Il commence par cibler des **employés ou prestataires** ayant des accès privilégiés. Le Telegram de Lapsus$ était public et diffusait des annonces de recrutement explicites.

**2. Acquisition d'accès par social engineering**
Trois méthodes principales :
- **SIM Swapping** : contacter l'opérateur télécom de la victime en usurpant son identité pour transférer son numéro → intercepter les SMS MFA
- **MFA Fatigue** : bombarder la victime de push notifications MFA jusqu'à ce qu'elle accepte par lassitude (souvent à 2h du matin)
- **Vishing helpdesk** : appeler le service IT de la cible en se faisant passer pour un employé et demander une réinitialisation de MFA

**3. Élévation de privilèges**
Une fois l'accès initial obtenu, Lapsus$ cherche immédiatement les accès les plus élevés :
- Recherche dans les dépôts de code (Azure DevOps, GitHub, GitLab) des credentials hardcodés
- Accès aux outils internes (Jira, Confluence, Slack) pour trouver des secrets d'administration
- Utilisation de DCSync et Mimikatz pour dump de l'Active Directory

**4. Exfiltration massive et rapide**
- Vol de code source (Microsoft Bing/Cortana, Samsung, Nvidia, Rockstar Games GTA VI)
- Exfiltration vers des services cloud personnels ou Telegram
- Utilisation de NightHawk ou outils LotL pour se déplacer

**5. Extorsion et publication**
- Contact direct avec la victime via Telegram ou email
- Demande de rançon (souvent pas acceptée, le groupe semble préférer la notoriété)
- Publication des données et screenshots sur leur canal Telegram public 

---

## 4. Victimologie

### Profil des cibles
- **Grandes entreprises tech** avec des accès identitaires critiques (Okta, Azure AD)
- **Éditeurs de jeux vidéo** (code source, secrets de production)
- **Télécoms et MSP** (accès transversal à de nombreux clients)
- **Fournisseurs d'identité** (Okta = vecteur d'attaque vers des milliers de clients)
- Pas de ciblage géopolitique ni sectoriel structuré — opportuniste et attiré par la notoriété

### Victimes documentées (2021-2022)

| Date | Victime | Impact documenté |
|------|---------|-----------------|
| Déc. 2021 | Ministère de la Santé Brésilien | Bases de données COVID exfiltrées, site mis hors ligne |
| Déc. 2021 | Claro, Embratel, NET (Brésil) | Source code, données clients, ordres de surveillance |
| Jan. 2022 | Impresa (Portugal) | Comptes Twitter pris en otage, faux articles publiés |
| Fév. 2022 | Nvidia | 1 To de données, schémas GPU, credentials 71 000 employés |
| Fév. 2022 | Samsung | 190 Go source code (Galaxy), clés privées, algorithmes biométriques |
| Fév. 2022 | Vodafone | Source code réseau interne (non confirmé par Vodafone) |
| Mars 2022 | **Microsoft** | 37 Go source code Bing, Cortana, Bing Maps, Azure DevOps |
| Mars 2022 | **Okta** | Accès admin panel → 2,5% des clients Okta potentiellement affectés |
| Mars 2022 | Ubisoft | Perturbation services, accès systèmes internes |
| Mars 2022 | T-Mobile | Code source, outils internes (credentials achetés sur dark web) |
| Avr. 2022 | LG Electronics | Hashes credentials comptes utilisateurs et services |
| Juin 2022 | Globe Telecom (Philippines) | Données internes |
| Juil. 2022 | **Globant** | 70 Go code source, credentials admin du client Uber |
| Août 2022 | **Uber** | Accès total systèmes internes — Slack, AWS, GCP, HackerOne, logs Pentest |
| Sept. 2022 | **Rockstar Games** | 90 vidéos GTA VI + code source — depuis un Holiday Inn via Chromecast |
| Sept. 2022 | BT Group (UK) | Données internes |

---

## 5. Connexion avec les groupes liés — The Com

Lapsus$ s'inscrit dans un écosystème plus large de cybercriminels anglophones adolescents :

### Scattered Spider (0ktapus / Octo Tempest / UNC3944)
- Fondé en mai 2022, probablement par d'anciens membres ou contacts de Lapsus$
- TTPs quasi identiques : SIM swapping, MFA fatigue, vishing helpdesk
- Attaques MGM Resorts (2023, ~$100M dégâts) et Caesars (rançon 15M$)
- CISA advisory AA23-320A mis à jour juillet 2025 avec nouveaux TTPs

### ShinyHunters (UNC6040/UNC6240)
- Spécialisé dans les violations de données cloud (Snowflake breach 2024, 165+ organisations)
- Campagne vishing Salesforce 2025 — AI voice agents pour imiter des humains

### Scattered LAPSUS$ Hunters (SLH) — **Fusion août 2025**
En août 2025, les trois groupes (Scattered Spider, Lapsus$, ShinyHunters) ont fusionné en un collectif connu sous le nom de Scattered LAPSUS$ Hunters (SLH), créant au moins 16 canaux Telegram depuis le 8 août 2025.

---

## 6. Héritage et impact systémique

### Ce que Lapsus$ a changé

**Concernant le MFA :**
Le rapport CSRB (août 2023) a conclu que Lapsus$ a exposé une **défaillance collective** de l'écosystème MFA. Le SMS-based MFA est fondamentalement brisé. Recommandation : transition vers FIDO2 / passkeys.

**Concernant le SIM swapping :**
Les opérateurs télécom US n'avaient pas de protocoles suffisants. FCC/FTC recommandées pour mandater de nouvelles protections.

**Concernant les fournisseurs d'identité (IdP) :**
La compromission d'Okta illustre le risque de concentration — un seul IdP compromis = potentiellement des milliers d'organisations affectées.

**Concernant la cybercriminalité juvénile :**
CSRB recommande au Congrès US de traiter spécifiquement la cybercriminalité juvénile dans la législation — les peines actuelles sont perçues comme insuffisantes.

---

## 7. Timeline complète (2021-2026)

| Période | Événement | Statut |
|---------|-----------|--------|
| Juin 2021 | Premières mentions Lapsus$ sur forums, Brésil | Reported |
| Déc. 2021 | Attaque Ministère Santé Brésil + Claro/Embratel | Corroborated |
| Jan.-Fév. 2022 | Vague Impresa, Nvidia, Samsung, Vodafone | Corroborated |
| Mars 2022 | Semaine décisive : Microsoft + Okta simultanément | Corroborated |
| 23-25 mars 2022 | 7 arrestations City of London Police (16-21 ans) | Corroborated |
| Avr.-Juil. 2022 | LG, Globant — activité post-arrestation continue | Corroborated |
| Août 2022 | **Arion Kurtaj (sous caution) hack Uber depuis un Holiday Inn** | Corroborated |
| Sept. 2022 | **Rockstar Games** — GTA VI via Chromecast + télévision | Corroborated |
| Oct. 2022 | Arrestation membre brésilien | Corroborated |
| Août 2023 | **CSRB publie son rapport** — 10 recommandations systémiques | Corroborated |
| Déc. 2023 | **Jugement Arion Kurtaj** — internement psychiatrique indéfini | Corroborated |
| 2024 | Activité dormante directe Lapsus$ | Dormant |
| **Août 2025** | **Fusion SLH** — Scattered Spider + Lapsus$ + ShinyHunters | Reported |
| **Sept. 2025** | **Jaguar Land Rover** — ransomware SLH, ~$67M/semaine | Reported |
| 2026 | SoundCloud, Betterment, Crunchbase, MatchGroup breachés par SLH | Reported |

---

*Sources : MITRE G1004, CSRB Report (août 2023), Microsoft DEV-0537 (mars 2022), NCC Group TTPs (avr. 2022), Resecurity (sept. 2025), Push Security (nov. 2025), CISA AA23-320A (màj juil. 2025)*
