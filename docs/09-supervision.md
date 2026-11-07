# Supervision

## Périmètre
- PC fixe (Windows, VLAN 10) : windows_exporter, port 9100
- Second PC (Linux, chambre forte) : Node Exporter, port 9100
- Hors supervision : portable, téléphone, appareils de la famille

## Besoins et sources

| Besoin (question) | Donnée | Source | Format | Mise à jour | Si anormal |
|---|---|---|---|---|---|
| Est-ce que tout tourne ? | CPU, RAM, disque | windows_exporter (PC fixe), Node Exporter (serveur) | Métriques | 1 min | Alerte ntfy |
| Le PC fixe chauffe-t-il ? | Température | windows_exporter ou LibreHardwareMonitor | Métriques | 1 min | Alerte si seuil |
| Y a-t-il une attaque ? | Alertes Suricata | eve.json | Logs | Temps réel | Alerte immédiate |
| Qui a été banni ? | IP bloquées | CrowdSec | Logs | 1 h | Consulter |
| La sauvegarde a-t-elle réussi ? | Statut Restic | Script → fichier texte | Métrique | 1 jour | Alerte si échec |
| Qu'est-ce qui s'est passé ? | Événements | Syslog | Logs | Temps réel | Consulter |

## Design de la page principale
- Haut : états des services (vert / rouge)
- Milieu : jauges (CPU, RAM, température) et graphe de trafic
- Sous-pages : logs et tableaux (sécurité, trafic)

## Journal
### 2026-11-07
- Premier jet des besoins et des sources.
