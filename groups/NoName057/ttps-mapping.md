# TTPs Mapping — NoName057

**Dernière mise à jour :** 2026-04
**Techniques Enterprise :** 16
**Techniques ATT&CK for ICS :** 2
**Sources :** CISA AA25-343A (déc. 2025), Recorded Future (juil. 2025), CISA Critical Infrastructure Advisory (déc. 2025), Picus Security (jan. 2026), SOCRadar (jan. 2026)

---

## Note sur le mapping de NoName057

NoName057(16) est **radicalement différent** de tous les autres groupes de cette série.

Le mapping ATT&CK de NoName057 est donc beaucoup plus court que les autres groupes, non pas parce qu'ils sont moins dangereux, mais parce que leur technique principale (DDoS) ne nécessite pas de chaîne d'intrusion complète.

**La dangerosité de NoName057(16) vient de son VOLUME et sa PERSISTANCE, pas de sa sophistication.**

---

## Table de mapping — ATT&CK Enterprise

| # | Comportement observé | Source | Technique ATT&CK | ID | Tactic | Confiance |
|---|---------------------|--------|------------------|----|--------|-----------|
| 1 | Surveillance des annonces politiques et militaires (sanctions, livraisons armes, votes OTAN) pour sélectionner les cibles | CISA AA25-343A, SOCRadar | Gather Victim Org Information | T1591 | Reconnaissance | HIGH |
| 2 | Identification d'hôtes gouvernementaux et d'infrastructure publique via scanning internet | Recorded Future CTA-2025-0722 | Active Scanning | T1595 | Reconnaissance | HIGH |
| 3 | Scanning d'équipements OT exposés (VNC) avec identifiants par défaut — via collaboration CARR/Z-Pentest | CISA AA25-343A (déc. 2025) | Active Scanning: Vulnerability Scanning | T1595.002 | Reconnaissance | HIGH |
| 4 | Développement et maintien de DDoSia — outil propriétaire Go, multi-plateforme | CISA AA25-343A, Recorded Future | Develop Capabilities: Malware | T1587.001 | Resource Development | HIGH |
| 5 | Infrastructure à deux niveaux : Tier 1 (proxies C2 éphémères ~9j) + Tier 2 (backend ACL-protégé) | Recorded Future CTA-2025-0722 | Acquire Infrastructure: Server | T1583.004 | Resource Development | HIGH |
| 6 | Recrutement de bénévoles via Telegram + paiement crypto (leaderboard, badges, récompenses) | CISA AA25-343A, Europol | Establish Accounts: Social Media | T1585.001 | Resource Development | HIGH |
| 7 | Achat/location de serveurs pour le botnet propre (several hundred servers) en plus des bénévoles | Europol, Recorded Future | Acquire Infrastructure: Botnet | T1583.005 | Resource Development | HIGH |
| 8 | Accès aux VPN, RDP, VDI exposés d'organisations cibles via credentials par défaut | CISA AA25-343A | External Remote Services | T1133 | Initial Access | HIGH |
| 9 | Accès aux interfaces VNC exposées avec identifiants par défaut ou faibles (collaboration Z-Pentest) | CISA AA25-343A (déc. 2025) | Valid Accounts: Default Accounts | T1078.001 | Initial Access | HIGH |
| 10 | Exécution du client DDoSia sur machines des bénévoles — flood HTTP/HTTPS automatisé | CISA AA25-343A, Recorded Future | Command and Scripting Interpreter | T1059 | Execution | HIGH |
| 11 | Rotation des serveurs Tier 1 toutes les 1-9 jours pour éviter blocklists | Recorded Future | Impair Defenses: Disable or Modify Tools | T1562.001 | Defense Evasion | HIGH |
| 12 | Utilisation de NordVPN et proxies pour masquer l'origine des administrateurs | CISA AA25-343A | Proxy | T1090 | Defense Evasion | HIGH |
| 13 | Conservation du Tier 2 (backend) derrière ACL — inaccessible même si Tier 1 compromis | Recorded Future | Hide Infrastructure | T1665 | Persistence | HIGH |
| 14 | Cartographie des infrastructures ciblées et identification des services exposés | CISA AA25-343A | Network Service Discovery | T1046 | Discovery | HIGH |
| 15 | DDoS volumétrique/applicatif (Layer 7 HTTP flood) — 50 cibles/jour, jusqu'à 91/jour | Recorded Future, SOCRadar | Network Denial of Service: Direct Network Flood | T1498.001 | Impact | HIGH |
| 16 | Flood applicatif Layer 7 ciblant les serveurs web gouvernementaux | CISA, Recorded Future | Endpoint Denial of Service: Application Exhaustion Flood | T1499.003 | Impact | HIGH |

---

## Table de mapping — ATT&CK for ICS 

> Note : Ces techniques ICS sont documentées pour les groupes NoName057 + CARR + Z-Pentest, pas pour NoName057 seul. L'attribution directe à NoName057(16) est medium en terme de confidence pour les techniques ICS.

| # | Comportement observé | Source | Technique ICS | ID ICS | Confiance |
|---|---------------------|--------|---------------|--------|-----------|
| ICS-1 | Manipulation d'équipements HMI via VNC exposés (changement paramètres, désactivation alarmes, redémarrage) | CISA AA25-343A (déc. 2025), Imperva | Manipulate I/O Image | T0835 | MEDIUM |
| ICS-2 | Modification de noms de systèmes HMI — defacement OT pour revendiquer (Z-Pentest, avril 2025) | CISA AA25-343A | Modify Parameter | T0836 | MEDIUM |

---

## Particularités du mapping NoName057(16)

### Ce qui est absent (et pourquoi)
- **Pas de techniques Credential Access sophistiquées** — ils utilisent des credentials par défaut, pas des dumps AD ou DCSync
- **Pas de Lateral Movement documenté** — les attaques DDoS ne nécessitent pas de mouvement latéral
- **Pas de Collection/Exfiltration** — NoName057(16) ne vole pas de données (contrairement à CARR ou Z-Pentest qui font du hack-and-leak)
- **Pas de malware de persistence** — DDoSia est un outil volontairement installé par les bénévoles, pas un malware caché

### Ce qui est unique (vs les autres groupes)
- **T1583.005 (Botnet)** — peu de groupes hacktivist ont leur propre botnet + armée de bénévoles
- **T1585.001 (Establish Social Media Accounts)** — le Telegram est central à tout le modèle opérationnel
- **T1498 + T1499** — dans cette série, seul NoName057(16) utilise le DoS comme technique d'Impact principale (Sandworm utilise T1485 Data Destruction, LockBit T1486 Encryption)
- **Corrélation géopolitique** — les cibles sont sélectionnées en temps réel selon l'actualité internationale, pas de façon opportuniste

### La vraie dangerosité : le volume et la persistance

En une semaine (nov. 24-30, 2025), SOCRadar a observé **7 939 commandes DDoS** vers **147 hôtes** distincts. L'outil DDoSia lui-même ne génère pas de trafic volumétrique massif comparable à un botnet classique — mais la **persistance**, la **fréquence** et la **coordination** créent des perturbations réelles sur des sites à faible protection DDoS (sites gouvernementaux de pays moins bien équipés).

---

*Note : Actualisation Avril 2026*
