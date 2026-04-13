# Gap Analysis — NoName057

**Date :** 2026-03
**MITRE référence :** NoName057 n'a pas encore de page MITRE ATT&CK dédiée, cela a donc été fait depuis des sources primaires CISA/Recorded Future/Europol
**Techniques dans ma layer :** 16 Enterprise + 2 ICS = 18
**Actualisation :** Avril 2026

---

## Situation MITRE pour NoName057

Contrairement aux autres, NoName057 n'a pas encore de page MITRE ATT&CK officielle actuellement (avril 2026). Cela s'explique par :

1. **Le groupe est classé hacktivist, pas APT**,  MITRE priorise les acteurs étatiques et les groupes avec des TTPs plus complexes
2. **Le DDoS est une technique bien documentée mais peu différenciante**, les techniques T1498/T1499 sont déjà dans le framework


---

## Sources utilisées en remplacement de MITRE

| Source | Équivalent MITRE | Contenu clé |
|--------|-----------------|-------------|
| CISA AA25-343A (déc. 2025) | Principal | TTPs confirmées, lien CISM, collaboration CARR/Z-Pentest |
| Recorded Future CTA-2025-0722 (juil. 2025) | Technique | Infrastructure Tier 1/Tier 2, tempo opérationnel, géographie |
| Europol (juil. 2025) | Attribution | Structure, membres, 4 000+ bénévoles |
| SOCRadar (jan. 2026) | Volume | Fréquence d'attaque, métriques opérationnelles |

---

## Ce que cette analyse apporte par rapport aux profils publics

### Techniques documentées dans ce mapping

| Technique | Nouveauté |
|-----------|-----------|
| T1595.002 (OT Vulnerability Scanning) | Lien avec CARR/Z-Pentest — extension DDoS vers OT |
| T1078.001 (Default Accounts) | Via VNC exposés — confirmation CISA déc. 2025 |
| T1665 (Hide Infrastructure) | Architecture Tier 1/Tier 2 documentée par Recorded Future |
| T0835 / T0836 (ICS) | Via Z-Pentest — évolution hacktivisme vers OT |

---

## Gaps identifiés

### Techniques probables mais non confirmées publiquement

| ID | Technique | Probabilité | Note |
|----|-----------|-------------|------|
| T1498.002 | Reflection Amplification | MEDIUM | Certaines campagnes semblent utiliser de l'amplification, non confirmé |
| T1583.003 | Virtual Private Server | HIGH | Infrastructure VPS probable, non spécifiquement documentée |
| T1583.006 | Web Services | MEDIUM | Hébergement de DDoSia sur GitHub documenté (NCC Group) |
| T1499.002 | Service Exhaustion | MEDIUM | Layer 7 HTTP précis → probable service exhaustion |
| T0829 (ICS) | Loss of View | LOW-MEDIUM | Indisponibilité HMI documentée mais causalité technique incertaine |

---

