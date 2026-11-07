# Sentinelle

Lab réseau et sécurité domestique : protéger une zone de mon réseau, contrôler ce qui y entre et en sort, détecter les intrusions.

## En bref
- **Problème** : un réseau domestique est plat, tout le monde se voit, rien n'est contrôlé.
- **Solution** : une zone protégée, séparée par VLAN, derrière un routeur-pare-feu, avec chiffrement et détection.
- **Ce que ça démontre** : segmentation, pare-feu, chiffrement, supervision, méthode documentée.

## Architecture
Internet → Box (mode bridge) → Routeur Sentinelle (pare-feu, frontière) → Switch manageable → Zones (VLAN)

| Zone | VLAN | Contenu |
|---|---|---|
| Admin | 10 | PC fixe principal |
| Postes | 20 | PC portable, téléphone |
| Salon (invités gérés) | 30 | Invités, accès accordé au cas par cas |
| Hors Sentinelle | aucun | Appareils de la famille, non gérés |

Schéma détaillé et analogie maison : [docs/02-architecture.md](docs/02-architecture.md) et [docs/00-conception.md](docs/00-conception.md)

## Objectifs
Confidentialité, contrôle des accès, identification, filtrage entrant et sortant, intégrité, disponibilité, récupération, détection.
Détail et critères de validation : [docs/01-contexte.md](docs/01-contexte.md), [docs/06-tests.md](docs/06-tests.md)

## Décisions clés
Les choix retenus et leurs raisons : [docs/03-decisions.md](docs/03-decisions.md)

## Avancement
- [x] Périmètre et objectifs définis
- [x] Analogie maison et tableau de conception
- [ ] Schéma réseau validé
- [ ] Plan d'adressage (`04-adressage.md`)
- [ ] Règles pare-feu (`05-regles.md`)
- [ ] Tests et preuves (`06-tests.md`)
- [ ] Détection (Suricata, logs)

## Limites connues
Voir [docs/07-limites.md](docs/07-limites.md) : ce qui n'est pas couvert et pourquoi.

## Matériel
- PC fixe (Windows 11, 16 Go RAM), PC portable, téléphone
- Vieux PC (8 Go), rôle à définir
- Routeur et switch manageable (à acheter)

## Documentation
[Contexte](docs/01-contexte.md) · [Conception](docs/00-conception.md) · [Architecture](docs/02-architecture.md) · [Décisions](docs/03-decisions.md) · [Adressage](docs/04-adressage.md) · [Règles](docs/05-regles.md) · [Tests](docs/06-tests.md) · [Limites](docs/07-limites.md) · [Retour](docs/08-retour.md)
