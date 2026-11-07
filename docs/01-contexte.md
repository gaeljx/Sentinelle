# Contexte

## Besoin
Sécuriser une zone de mon réseau domestique et la transformer en lab permanent, pour apprendre et démontrer des compétences en sécurité réseau.

## Périmètre (dedans)
- PC fixe principal (Windows 11, 16 Go RAM) : zone admin
- PC portable : zone postes
- Téléphone : zone postes (Wi-Fi, plus tard)
- Vieux PC (8 Go) : rôle à confirmer, probablement serveur de services
- Routeur et switch Sentinelle : à acheter, à l'intérieur de la zone

## Hors périmètre
- Réseau familial (box, Wi-Fi familial) : séparé, sans VLAN
- Box internet : configurée en mode bridge, elle ne fait que la liaison
 
## Contraintes
- Lab accessible uniquement depuis la maison
- Données privées, stockées en local
- Pas de clé API ni de service cloud pour les données sensibles
- Fonctionnement 24/7 visé, avec un onduleur si possible
- Respect des autres : aucune surveillance ni blocage des appareils de la famille sans leur accord

## Objectifs de sécurité
1. Confidentialité : le trafic sensible est chiffré
2. Accès : chaque zone n'atteint que ce qui lui est autorisé
3. Identité : un accès est vérifié (mot de passe, 2FA, clé SSH)
4. Entrées et sorties : seuls les flux autorisés passent
5. Intégrité : une modification de fichier ou de config est détectée
6. Disponibilité : les services restent joignables
7. Récupération : une sauvegarde se restaure et se vérifie
8. Détection : une intrusion test génère une alerte

Les critères de validation de chaque objectif sont dans `06-tests.md`.

## Services retenus

| Service | Rôle | Zone | Statut |
|---|---|---|---|
| VPN (WireGuard) | Accès à distance, seule entrée depuis l'extérieur | Vestibule (DMZ) | ✅ |
| SSO / 2FA | Identité centralisée pour les autres services | Chambre forte | ✅ |
| Gestionnaire de mots de passe (Vaultwarden) | Mots de passe, en local | Chambre forte | ✅ |
| Sauvegardes chiffrées (Restic) | Copie des données critiques, testée | Chambre forte | ✅ |
| Partage de fichiers (Samba) | Dossiers partagés, droits par utilisateur | Zone postes ou admin | ✅ |
| Streaming (Jellyfin) | Médias en local | Zone postes ou admin | ✅ |
| DNS (Pi-hole) | Filtrage des domaines malveillants | Zone admin ou serveur | 🔁 |
| DHCP | Adresses IP par zone | Routeur Sentinelle | ✅ |
| Pare-feu / routage | Filtrage entrant et sortant | Routeur Sentinelle | ✅ |
| Logs centralisés (Syslog) | Journaux, la « caméra » | Chambre forte | ✅ |
| Détection (Suricata) | Alertes sur le trafic | Routeur ou switch (mirroring) | ✅ |
| Supervision (Grafana, Prometheus) | État des machines, alertes | Chambre forte ou admin | ✅ |
| Honeypot (Cowrie) | Leurre pour observer les attaques | Fausse chambre forte (vestibule) | ✅ |
| Machine d'attaque (Kali) | Tests de défense | Zone admin | ✅ |

**Règle par défaut** : les invités (salon, VLAN 30) n'ont qu'Internet. Tout autre service s'ouvre au cas par cas.
