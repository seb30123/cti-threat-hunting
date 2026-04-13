# NoName057 — Profil Complet

## 1. Identité et origine

| Champ | Détail |
|-------|--------|
| Nom | NoName057 |
| Aliases | 05716nnm, NoName057, NoName |
| Type | Hacktivist pro-russe — DDoS crowdsourcé |
| Créé | Mars 2022 — quelques jours après l'invasion de l'Ukraine (24 fév. 2022) |
| Lien étatique | **CISM** — Centre for the Study and Network Monitoring of the Youth Environment (organisation Kremlin) |
| Outil | DDoSia (successeur du botnet Bobik) |
| Modèle | Crowdsourcé — bénévoles recrutés via Telegram, payés en crypto |

### Le lien CISM — évaluation CISA 

La CISA (advisory AA25-343A, déc. 2025) évalue que :
- Le CISM (organisation liée au Kremlin) a créé NoName057 comme projet covert
- Les dirigeants et employés du CISM ont développé et personnalisé DDoSia
- Le CISM a payé l'infrastructure réseau du groupe
- Des cadres CISM ont servi d'administrateurs sur les canaux Telegram NoName057
- Le CISM a sélectionné les cibles DDoS


---

## 2. DDoSia — L'outil central

### Qu'est-ce que DDoSia ?

DDoSia est un client DDoS crowdsourcé, développé en Go, successeur du botnet Bobik. C'est l'innovation centrale de NoName057, transformer des bénévoles ordinaires en soldats numériques sans qu'ils aient la moindre compétence technique.

### Comment ça fonctionne

1. Un bénévole télécharge le client DDoSia depuis Telegram
2. Il s'enregistre avec un token unique (pour le suivi des récompenses)
3. DDoSia contacte automatiquement les serveurs C2 de Tier 1 sur **port 80**
4. Le client reçoit la liste des cibles et paramètres d'attaque
5. Il génère du trafic HTTP/HTTPS de flood vers les cibles
6. Les résultats sont remontés → leaderboard → récompenses crypto

### Infrastructure à deux niveaux

| Niveau | Description | Durée de vie | Rôle |
|--------|-------------|--------------|------|
| **Tier 1** | Serveurs C2 publics (proxies éphémères) | ~9 jours (parfois 1 jour) | Communication avec les clients DDoSia |
| **Tier 2** | Serveurs backend | Permanent | Logique centrale + base de cibles, protégé par ACL |

La rotation des Tier 1 permet d'éviter les blocklists. Même si Tier 1 est compromis → Tier 2 reste opérationnel.

### Évolution de DDoSia

| Version | Année | Nouveautés |
|---------|-------|-----------|
| v1.0 | 2022 | Preuve de concept, Windows only, trafic simple facilement bloqué |
| v2.0 | 2023 | Multi-plateforme (Linux), modules additionnels, meilleures techniques d'évasion |
| v3.0+ | 2024–2025 | Modulaire, multi-plateforme (Linux/Windows/macOS), ACL backend, résistance aux blocklists |

### Gamification — le moteur humain

NoName057 a inventé la gamification de la cyberguerre :
- Leaderboard public sur Telegram — classement des bénévoles les plus actifs
- Récompenses crypto (principalement TON/Toncoin, parfois Bitcoin)
- Badges et statuts pour les participants les plus fidèles
- Shout-outs (mentions publiques) pour motiver
- Narration patriotique — "défendre la Russie", "venger les événements politiques"


---

## 3. Playbook opérationnel

### Cycle d'attaque 

1. **Sélection des cibles** — opérateurs choisissent les cibles selon l'actualité géopolitique (annonces militaires, visites diplomatiques, sanctions, etc.)
2. **Annonce** — publication sur Telegram de la prochaine campagne + rhétorique politique pour mobiliser
3. **Distribution des paramètres** — envoi des listes de cibles et configs aux clients DDoSia
4. **Attaque** — flood Layer 7 (HTTP/HTTPS) simultané par tous les bénévoles + botnet propre (plusieurs centaines de serveurs)
5. **Rapport** — publication de screenshots d'indisponibilité, statistiques de performance
6. **Récompenses** — mise à jour du leaderboard, paiement crypto aux meilleurs
7. **Itération** — ajustement infrastructure si nécessaire → prochaine campagne

### Rythme opérationnel

- **Moyenne 2024–2025** : 50 cibles uniques par jour
- **Pic** : 91 cibles en une seule journée
- **Horaires** : calqués sur le fuseau horaire russe — pics à 05h00-07h00 UTC et 11h00 UTC
- **En une semaine (nov. 2025)** : 7 939 commandes DDoS vers 147 hôtes uniques (SOCRadar)

### Corrélation géopolitique

Les attaques sont systématiquement déclenchées par des événements géopolitiques :
- Annonces de livraisons d'armes à l'Ukraine → attaques sur le pays annonceur
- Visites de Zelensky → attaques sur le pays hôte (ex : Belgique oct. 2023)
- Votes OTAN → attaques sur les membres
- Sanctions → attaques sur les pays sanctionnant

---

## 4. Affiliations et écosystème

### Groupes liés

| Groupe | Lien avec NoName057 | Statut |
|--------|------------------------|--------|
| **CARR** (Cyber Army of Russia Reborn) | Alliance depuis mi-2024, opérations conjointes, membres partagés → Z-Pentest | Actif. Lié GRU (Unité 74455 selon CISA) |
| **Z-Pentest** | Sous-groupe créé sept. 2024 par membres CARR + NoName057 | Actif. Spécialisé OT/ICS intrusion. |
| **Sector16** | Groupe novice créé jan. 2025 via Z-Pentest | Actif |
| **Z-Alliance** | Coalition hacktivist pro-russe/iranienne | Actif. NoName057 y participe pour campagnes coordonnées |
| KillNet | Prédécesseur contextuel, même niche hacktivist pro-russe | Partiellement dissous |

### Note importante sur CARR et GRU

CISA évalue que GRU/GTsST (Unité 74455) a soutenu CARR (pas NoName directement). Z-Pentest a été créé quand les admins CARR+NoName sont devenus insatisfaits du soutien GRU → Z-Pentest est séparé du GRU. La chaîne d'attribution est : Kremlin (CISM) → NoName057(16) → Z-Pentest, sans GRU direct.

---

## 5. Victimologie

### Chiffres globaux (juillet 2024 – juillet 2025)
- **3 776** hôtes distincts ciblés en 13 mois
- **50** cibles uniques/jour en moyenne
- **4 693** attaques revendiquées en 2025 (record mondial)

### Pays ciblés (par intensité)

| Rang | Pays | % des attaques | Note |
|------|------|---------------|------|
| 1 | Ukraine | 29,47% | Cible principale — infrastructure critique, gouvernement |
| 2 | France | 6,09% | 2e pays le plus ciblé hors Ukraine — 3e pays en France selon Wikipedia |
| 3 | Italie | 5,39% | Soutien militaire à Ukraine |
| 4 | Suède | 5,29% | Entrée OTAN |
| 5 | Allemagne | — | 250 entreprises/institutions ciblées en 14 vagues depuis nov. 2023 |
| 6 | USA | — | Pas cible principale malgré soutien Ukraine |

### Secteurs ciblés 

| Secteur | % des attaques |
|---------|---------------|
| Gouvernement & secteur public | 41,09% |
| Transport & logistique | 12,44% |
| Technologie, médias, télécoms | 10,19% |
| Finance & banque | ~8% |
| Infrastructure critique (eau, énergie) | ~5% (en hausse 2025) |

---

## 6. Attaques documentées en France

La France est l'une des cibles prioritaires de NoName057, **6,09% de toutes les attaques** sur la période juillet 2024 – juillet 2025.

| Date | Cible | Type d'attaque | Contexte |
|------|-------|---------------|----------|
| Mars 2023 | Assemblée nationale | DDoS — site public indisponible | Soutien France à l'Ukraine |
| Mai 2023 | Sénat | DDoS — site bloqué | Même contexte |
| Juin 2023 | RATP (sites liés) | DDoS | Continuation campagne France |
| Déc. 2024 | Nice, Marseille, Pau (sites municipaux) | DDoS symboliques | 31 décembre 2024 |
| Déc. 2025 | **La Poste + filiales bancaires** | DDoS — serveurs ciblés avant Noël | Maintien pression sur soutien FR à Ukraine |
| Juil. 2025 | Divers sites allemands et italiens (post-Eastwood) | DDoS | Réponse opération européenne |

> Note France : Deux arrestations de l'Opération Eastwood ont eu lieu en France(juillet 2025) — montrant que des membres ou facilitateurs résidaient sur le territoire français.

---

## 7. Opération Eastwood — Juillet 2025

### Faits

L'**Opération Eastwood** (14-17 juillet 2025) est la plus grande opération internationale contre NoName057 :
- **Coordonnée** par Europol + Eurojust
- **Pays participants** : Tchéquie, France, Finlande, Allemagne, Italie, Lituanie, Pologne, Espagne, Suède, Suisse, Pays-Bas, USA
- **Soutien** : Belgique, Canada, Estonie, Danemark, Lettonie, Roumanie, Ukraine, ENISA, ShadowServer, abuse.ch
- **Résultats** : 2 arrestations (France + Espagne), 7 mandats d'arrêt (6 Allemagne + 1 Espagne), 24 perquisitions, 100+ serveurs saisis
- **EU Most Wanted** : 5 Russes ajoutés à la liste, dont BURLAKOV (membre central)

### Impact réel

| Phase | Comportement observé |
|-------|---------------------|
| Pendant l'opération (14-17 juil.) | **Aucun ralentissement** — 10 cibles/jour, activité normale |
| Jour J (17 juil.) | Communiqué Telegram : "ne croyez pas ce non-sens des services étrangers" |
| 18-22 juil. | **5 jours de silence** — premier impact observable |
| Dès le 22 juil. | Reprise des attaques — sites italiens et allemands (pays participants à Eastwood) |
| Post-Eastwood | 13 revendications d'intrusions OT (eau Roumanie/Tchéquie, chauffage Lituanie, désalinisation Espagne) |
| Fin 2025 | **4 693 attaques totales en 2025** — 83% post-Eastwood |

---

## 8. Timeline (2022–2026)

| Période | Événement | Statut |
|---------|-----------|--------|
| Mars 2022 | Création NoName057 — invasion Ukraine | Corroborated |
| Juin–Sept. 2022 | Attaques Lituanie, Pologne, Norvège, Finlande | Corroborated |
| Août 2022 | Lancement **DDoSia v1** — projet bénévoles | Corroborated |
| Déc. 2022 | Attaques Italie (post-annonce Meloni armes Ukraine) | Corroborated |
| Jan. 2023 | Attaques secteur bancaire danois | Corroborated |
| Mars 2023 | **France** — Assemblée nationale DDoS | Corroborated |
| Sept. 2023 | Canada + Québec (sites gouvernementaux) | Corroborated |
| Oct. 2023 | **Belgique** — Palais royal, Premier ministre, Sénat (post-visite Zelensky) | Corroborated |
| Nov. 2023 | Début vague Allemagne — 14 vagues, 250 orgs ciblées | Corroborated |
| Mid-2024 | Alliance opérationnelle avec **CARR** | Corroborated |
| Juillet 2024 | Revendication conjointe NoName+CARR d'intrusion OT USA | Reported |
| Sept. 2024 | Création **Z-Pentest** (membres CARR + NoName) | Corroborated |
| Déc. 2024 | Attaques municipalités françaises (Nice, Marseille, Pau) | Corroborated |
| **14-17 juil. 2025** | **Opération Eastwood** — 100+ serveurs, 2 arrêtés | Corroborated |
| Post-Eastwood 2025 | Reprise immédiate, 4 693 attaques totales 2025 (record) | Corroborated |
| Déc. 2025 | **La Poste France** — DDoS avant Noël. Ciblage infra eau RO/CZ | Reported |
| 2026 | CISA advisory AA25-343A — confirmation lien CISM/Kremlin | Corroborated |

---

*Sources : CISA AA25-343A (déc. 2025), Recorded Future CTA-2025-0722 (juil. 2025), Imperva (sept. 2025), Wikipedia FR (màj mars 2026), The Hacker News Europol (juil. 2025), SOCRadar (jan. 2026), Picus Security (jan. 2026)*
