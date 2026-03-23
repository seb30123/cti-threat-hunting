# LockBit — Profil Complet

## 1. Identité

| Champ | Détail |
|-------|--------|
| Type | RaaS (Ransomware-as-a-Service) — Cybercriminel pur, motivation exclusivement financière |
| Origine | Russophone — membres dispersés internationalement, serveurs multijuridictions |
| Leader | **Dmitry Yuryevich Khoroshev**, alias LockBitSupp / putinkrab, 31 ans, originaire de Voronej (Russie) |
| Démasqué | 7 mai 2024 par FBI/NCA/Europol — inculpé de 26 chefs dont fraude, extorsion, dommages systèmes |
| Sanctions | Asset freeze + travel ban UK, sanctions OFAC US (15M$ de récompense pour sa capture) |
| Début | Septembre 2019 (première variante connue sous le nom ".abcd") |
| Nom actuel | LockBit 5.0 "ChuongDong" (depuis septembre 2025) |

### Membres arrêtés/inculpés

| Alias | Identité réelle | Rôle | Statut |
|-------|-----------------|------|--------|
| LockBitSupp / putinkrab | Dmitry Khoroshev | Administrateur principal | En fuite, inculpé mai 2024 |
| Wazawaka / m1x | Mikhail Matveev | Affilié clé | Inculpé mai 2023, en fuite (Russie) |
| — | Ruslan Astamirov | Affilié | Arrêté, en détention (New Jersey) |
| Bassterlord | Ivan Kondratyev | Affilié | Inculpé fév. 2024 |
| — | Artur Sungatov | Affilié | Inculpé fév. 2024 |
| Beverley | Aleksandr Ryzhenkov | Affilié clé, lien Evil Corp | Sanctionné oct. 2024 |
| — | **Rostislav Panev** | Développeur (mécanisme impression ransom notes) | Arrêté à Haïfa (Israël) août 2024 |

> **Hack du panel admin (mai 2025)** : LockBit a été hacké par quelqu'un se réclamant de Prague. Un dump MySQL du panel d'administration (déc. 2024 → avr. 2025) a été publiquement partagé, révélant : identités d'affiliés, organisations victimes, transcriptions de chats, wallets crypto, configurations builds ransomware.

---

## 2. Modèle opérationnel du RaaS

LockBit fonctionne comme une franchise criminelle :

 1. **LockBitSupp** développe et maintient l'infrastructure, le ransomware, et le panneau d'administration
 2. **Les affiliés** (opérateurs) s'inscrivent, déposent ~500$ en Bitcoin (depuis LockBit 5.0), attaquent des cibles
3.  **Split** : LockBit prend ~20% des rançons, les affiliés gardent ~80%

4.  **Règles** : pas d'attaque de pays de la CEI, pas d'hôpitaux (règle violée à plusieurs reprises)



### Évolution des versions

| Version | Nom | Période | Informations sur le RaaS |
|---------|-----|---------|-----------------|
| ABCD | — | Sept 2019 | Première variante, extension .abcd |
| LockBit 1.0 | — | 2020 | Site propre, posts RU+EN |
| LockBit 2.0 | LockBit Red | Juin 2021 | StealBit (exfil auto), recrutement insiders, Linux/ESXi Locker (oct. 2021) |
| LockBit 3.0 | LockBit Black | Mars 2022 | UAC bypass, Windows Defender abuse, Cobalt Strike, similitudes BlackMatter/BlackCat |
| LockBit Green | — | Jan 2023 | Code source Conti assimilé, cible cloud |
| LockBit 4.0 / NG-Dev | LockBit Neo | Déc 2024 | .NET Core (multi-plateforme), annoncé post-Cronos, perturbé par FBI |
| **LockBit 5.0** | **ChuongDong** | **Sept 2025 (plus rècente)** | Multi-plateforme (Win/Linux/ESXi), extensions aléatoires 16 chars, anti-analyse renforcé, dépôt 500$ BTC affil. |

---

## 3. Opération Cronos — Février 2024

Le 19 février 2024, l'Opération Cronos (11 pays dont la France via la Gendarmerie) a saisi le site principal de LockBit et 34 de ses serveurs.

**Ce qui a été saisi :**
- Infrastructure principale + 34 serveurs
- Code source du ransomware (dont LockBit-NG-Dev)
- Données volées aux victimes + liste des victimes
- ~200 portefeuilles crypto-monnaies
- Panel de gestion des affiliés

**Résultat :** Moins d'une semaine après, LockBit avait restauré ses serveurs et lancé un nouveau site en exposant douze nouvelles victimes. LockBitSupp a évité la capture et annoncé un retour.

**Rebond :** LockBit 5.0 annoncé en septembre 2025 sur RAMP forum. En décembre 2025, LockBit a revendiqué 96 attaques, soit 83% de leur total 2025, toutes en 4 semaines.

---

## 4. Victimologie

### Chiffres clés
- **7 000+ attaques** entre juin 2022 et février 2024
- **~1 milliard $** de rançons extorquées (gov. britannique)
- **20-30%** de toutes les attaques ransomware mondiales (2021-2024)
- **Rançon médiane 2024-2025 :** 1,5M$ 
- **Temps de récupération moyen 2025 :** 22 jours

### Secteurs ciblés

| Secteur | Priorité |
|---------|----------|
| Manufacturing & industrie | Critique |
| Santé (hôpitaux) | Critique |
| Services professionnels & juridiques | Critique |
| Finance & banque | Critique |
| Infrastructure critique | Élevé |
| Logistique & transport | Élevé |
| Gouvernements & administrations | Élevé |
| Retail & distribution | Modéré |

### Pays les plus touchés
USA · Royaume-Uni · **France** · Allemagne · Chine

---

## 5. Lien avec la France

La France est responsable de 69 piratages LockBit en 2022 et 2023. LockBit est responsable de 27% des demandes de rançon en France.

### Attaques documentées


| Date | Victime | Impact | Version |
|------|---------|--------|---------|
| Jan. 2022 | **Thales** | Données exfiltrées, publiées | LockBit 2.0 |
| Juil. 2022 | **La Poste Mobile** | Services admin/gestion perturbés | LockBit 2.0 |
| Sept. 2022 | **Hôpital Corbeil-Essonnes** | Rançon 10M$, données santé publiées | LockBit 3.0 |
| Sept. 2022 | **28 organismes FR** (revendication) | dont 12 organismes français | LockBit 3.0 |
| 2022 | **OEHC (Corse)** | Chiffrement données, rançon non payée | LockBit |
| 2023 | **Département du Loiret** | SDIS, collèges, conseil départemental affectés | LockBit 3.0 |
| Jan. 2023 | **Nuxe** (luxe) | Données exfiltrées | LockBit 3.0 |
| Jan. 2024 | **Subway** (FR) | Revendication centaines de Go | LockBit 3.0 |
| **Avr. 2024** | **Hôpital Simone-Veil (Cannes)** | **61 Go publiés** — données patients/RIB/CI | LockBit 3.0 |
| 2024 | **Région Pays de la Loire** | Données publiées | LockBit 3.0 |
| 2024 | **Hôpital d'Armentières** | Builder LockBit 3.0 (usurpateur possible) | LockBit 3.0 dérivé |

---

## 6. Arsenal et outils

| Outil | Type | Description |
|-------|------|-------------|
| **StealBit** | Exfiltration propriétaire | Outil maison d'automatisation de l'exfil de données (LockBit 2.0+) |
| **Cobalt Strike** | C2 / Post-exploitation | Utilisé pour pivot réseau, C2, déploiement payload |
| **Mimikatz** | Credential dumping | Vol credentials, impersonation tokens |
| **PsExec** | Exécution distante | Déploiement ransomware domain-wide |
| **AnyDesk** | Remote access | Accès distant persistant |
| **7-Zip** | Compression | Archivage données avant exfiltration |
| **MEGA** | Exfiltration cloud | Service cloud légitime pour exfiltrer |
| **Splashtop** | Remote desktop | Déplacement latéral alternatif RDP |
| **PowerShell / cmd.exe** | LotL | Exécution commandes, suppression shadow copies |

---

## 7. Timeline (2019–2026)

| Période | Événement | Impact |
|---------|-----------|--------|
| Sept. 2019 | Première variante ABCD | Création du groupe |
| 2020 | LockBit 1.0 + site propre | Premier site vitrine |
| Juin 2021 | LockBit 2.0 + StealBit | Double extorsion systématisée |
| Oct. 2021 | Linux/ESXi Locker | Expansion aux serveurs virtuels |
| 2022 | LockBit 3.0 "Black" | Groupe le plus actif mondialement |
| Jan. 2023 | LockBit Green (Conti source) | Expansion cloud |
| 2023 | Groupe #1 mondial | 22% de toutes les attaques ransomware |
| **Fév. 2024** | **Opération Cronos** | Infrastructure saisie, 11 pays |
| **Mai 2024** | **LockBitSupp démasqué** | Khoroshev identifié + inculpé |
| Août 2024 | Panev arrêté en Israël | Développeur clé neutralisé |
| Déc. 2024 | LockBit 4.0 annoncé | Rebond partiel |
| **Mai 2025** | **Panel admin hacké** | Dump MySQL publié (affiliés, victimes, configs) |
| **Sept. 2025** | **LockBit 5.0 "ChuongDong"** | Nouveau retour opérationnel |
| **Déc. 2025** | **96 attaques en 1 mois** | Retour à activité significative |
| Jan. 2026 | Secteur manufacturing/santé ciblé | Activité soutenue confirmée |

---

*Sources : Wikipedia FR, CISA Advisory AA23-165A, Check Point Research (nov. 2025), Halcyon (fév. 2026), MITRE S1202 & S1199, Senseon TTPs mapping, arxiv 2511.06429 (nov. 2025)*
