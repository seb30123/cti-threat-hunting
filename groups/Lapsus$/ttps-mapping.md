# TTPs Mapping — Lapsus$

**Dernière mise à jour :** 2026-03


**Techniques identifiées :** 26

**[Sources](./sources/links.md) : Voir lien** 

---

## Légende

| Niveau | Signification |
|--------|---------------|
| **HIGH** | Documenté explicitement dans sources primaires (CSRB, Microsoft, NCC Group) |
| **MEDIUM** | Documenté dans sources secondaires ou partiellement corroboré |

---

## Table de mapping

| # | Comportement observé | Source | Technique ATT&CK | ID | Tactic | Confiance |
|---|---------------------|--------|------------------|----|--------|-----------|
| 1 | SIM Swapping : contacter l'opérateur télécom de la victime pour transférer son numéro et intercepter les SMS MFA | CSRB 2023, Microsoft DEV-0537 | SIM Card Swap | T1451 (Mobile) | Initial Access | HIGH |
| 2 | Phishing ciblé d'employés pour vol de credentials — pages de login imitant des services légitimes (Okta, VPN) | MITRE G1004, NCC Group | Phishing: Spearphishing Link | T1566.002 | Initial Access | HIGH |
| 3 | Vishing helpdesk : appeler le service IT de la cible en usurpant l'identité d'un employé pour demander réinitialisation MFA | CSRB 2023, Microsoft DEV-0537 | Phishing: Spearphishing via Service | T1566.003 | Initial Access | HIGH |
| 4 | Recrutement d'insiders via Telegram public — annonces offrant de l'argent pour des accès VPN, Citrix, Okta | MITRE G1004, CSRB 2023 | Phishing: Spearphishing via Service | T1566.003 | Initial Access | HIGH |
| 5 | Achat de credentials volés sur des forums criminels (Genesis Store, dark web) | CSRB 2023, KrebsonSecurity | Obtain Capabilities: Digital Certificates | T1588 | Resource Development | HIGH |
| 6 | MFA Fatigue (Push Bombing) : bombardement de push notifications MFA jusqu'à acceptation par lassitude | CSRB 2023, Microsoft DEV-0537 | Multi-Factor Authentication Request Generation | T1621 | Credential Access | HIGH |
| 7 | Utilisation de NightHawk C2 framework pour post-exploitation (documenté dans Uber breach) | NCC Group, MITRE G1004 | Command and Scripting Interpreter | T1059 | Execution | HIGH |
| 8 | Recherche de credentials hardcodés dans les dépôts de code internes (Azure DevOps, GitLab, GitHub) | Microsoft DEV-0537, MITRE G1004 | Unsecured Credentials: Credentials in Code Repository | T1552.007 | Credential Access | HIGH |
| 9 | Création de nouveaux comptes de domaine pour maintenir la persistence | MITRE G1004, NCC Group | Create Account | T1136 | Persistence | HIGH |
| 10 | Ajout de nouveaux fournisseurs d'identité (IdP) dans Okta/Azure AD pour persistence cross-tenant | Microsoft DEV-0537, CSRB | Additional Cloud Credentials | T1098.001 | Persistence | HIGH |
| 11 | DCSync pour dump de l'Active Directory complet (credentials domaine) | NCC Group, MITRE G1004 | OS Credential Dumping: DCSync | T1003.006 | Credential Access | HIGH |
| 12 | Mimikatz pour dump des credentials en mémoire (LSASS) | NCC Group, MITRE G1004 | OS Credential Dumping: LSASS Memory | T1003.001 | Credential Access | HIGH |
| 13 | Vol de session tokens et cookies d'authentification actifs depuis des employés | CSRB 2023, Microsoft DEV-0537 | Steal Web Session Cookie | T1539 | Credential Access | HIGH |
| 14 | Impersonation de compte avec tokens volés (access token manipulation pour contourner re-auth) | SOC Prime, MITRE G1004 | Access Token Manipulation | T1134 | Privilege Escalation | HIGH |
| 15 | Élévation de privilèges via accès à des comptes admin Okta compromis | CSRB 2023, Microsoft DEV-0537 | Valid Accounts: Cloud Accounts | T1078.004 | Privilege Escalation | HIGH |
| 16 | Désactivation ou manipulation des alertes de sécurité pour éviter la détection | NCC Group | Impair Defenses: Disable or Modify Tools | T1562.001 | Defense Evasion | MEDIUM |
| 17 | Utilisation d'outils légitimes (ngrok, AnyDesk, Splashtop) pour accès distant non détecté | NCC Group, MITRE G1004 | Remote Access Software | T1219 | Defense Evasion | HIGH |
| 18 | Enumération des systèmes internes et accès SharePoint, Confluence pour cartographier l'infrastructure | Microsoft DEV-0537, MITRE G1004 | Network Share Discovery | T1135 | Discovery | HIGH |
| 19 | Vol massif de code source depuis Azure DevOps (Bing, Cortana, Samsung, Nvidia source) | Microsoft DEV-0537, MITRE G1004 | Data from Information Repositories | T1213 | Collection | HIGH |
| 20 | Téléchargement massif de données via outils cloud légitimes (SharePoint sync, MEGA, services perso) | MITRE G1004, NCC Group | Transfer Data to Cloud Account | T1537 | Collection | HIGH |
| 21 | Exfiltration vers services cloud personnels (MEGA, Telegram) | MITRE G1004 | Exfiltration to Cloud Storage | T1567.002 | Exfiltration | HIGH |
| 22 | Exfiltration de données via canal Telegram du groupe | MITRE G1004, CSRB | Exfiltration Over Web Service | T1567 | Exfiltration | HIGH |
| 23 | Publication de données sensibles sur Telegram public pour pression extorsion | MITRE G1004, CSRB 2023 | Data Leak — Financial Threat | T1657 | Impact | HIGH |
| 24 | Suppression ou effacement de données pour nuire si rançon non payée (Ministère Santé Brésil) | MITRE G1004, Picus Security | Data Destruction | T1485 | Impact | MEDIUM |
| 25 | Acquisition de comptes email ou téléphoniques réels pour l'usurpation d'identité sociale | CSRB 2023 | Establish Accounts | T1585 | Resource Development | HIGH |
| 26 | Utilisation de proxies résidentiels pour masquer l'origine géographique des connexions | NCC Group | Proxy: Residential Proxy | T1090.004 | Defense Evasion | MEDIUM |

---

## Techniques spécifiques 

Ces techniques sont utilisées par Scattered LAPSUS$ Hunters (fusion 2025), héritées directement de Lapsus$ :

| ID | Technique | Comportement 2025 | Source |
|----|-----------|-------------------|--------|
| T1621 | MFA Request Generation | MFA bombing toujours technique centrale de SLH | Resecurity sept. 2025 |
| T1451 | SIM Card Swap | SIM swapping + AI voice agents pour vishing | Push Security nov. 2025 |
| T1566.003 | Spearphishing via Service | AI voice (Vapi, Bland via VoIP) pour imiter humains | Medium nov. 2025 |
| T1078.004 | Cloud Accounts | Ajout d'IdP Okta/Entra — AiTM phishing kit 2026 | Push Security 2026 |
| T1539 | Web Session Cookie | Vol session Okta/Entra/Google SSO — kit AiTM temps réel | Push Security 2026 |

---

