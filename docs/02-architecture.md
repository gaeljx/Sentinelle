# Architecture

## Schéma

![Maquette Packet Tracer de Sentinelle](../images/schema-packet-tracer.png)

Maquette Packet Tracer : elle montre la structure (frontière, zones, flux). Elle ne montre ni la configuration des VLAN ni les règles, qui sont dans les autres fichiers.

> Le HomeRouter représente la box réelle (routeur Wi-Fi). Le routeur 2911 représente le routeur Sentinelle, frontière de la zone.

## Flux principaux

| Flux | De | Vers | Passe par |
|---|---|---|---|
| Internet entrant | Internet | Vestibule (VPN) | Box → routeur Sentinelle |
| Internet sortant | Zones | Internet | Routeur Sentinelle |
| Accès admin | Zone admin (10) | Chambre forte | Routeur Sentinelle |
| Invités | Salon (30) | Internet | Routeur Sentinelle |
| Maison | Réseau familial | Internet | Box (hors Sentinelle) |

## Zones

| Zone | VLAN | Rôle | Contenu |
|---|---|---|---|
| Admin | 10 | Administration | PC fixe, Kali |
| Postes | 20 | Usage quotidien | PC portable, téléphone |
| Salon (invités gérés) | 30 | Invités, accès au cas par cas | Appareils invités |
| Vestibule (DMZ) | À compléter | Services exposés | VPN, honeypot |
| Chambre forte | À compléter | Données et services critiques | SSO, Vaultwarden, Restic, Syslog, Grafana |
| Maison (hors Sentinelle) | aucun | Réseau familial, non géré | Appareils de la famille |

## Équipements

| Équipement | Rôle | Statut |
|---|---|---|
| Box internet | Liaison Internet, routeur (bridge envisagé) | ✅ |
| Routeur Sentinelle | Pare-feu, frontière, VLAN | À acheter |
| Switch manageable 8 ports | VLAN, trunk | À acheter |
| PC fixe (16 Go) | Zone admin, VM | ✅ |
| Vieux PC (8 Go) | Rôle à définir | À compléter |
