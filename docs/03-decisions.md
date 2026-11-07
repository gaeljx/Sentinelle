# Décisions

## 1. Mode de la box
**Choix** : box en mode routeur pour l'instant (état réel). Passage en bridge envisagé plus tard.
**Pourquoi** : la box actuelle route et fait le Wi-Fi familial. Je ne veux pas la reconfigurer avant d'avoir validé Sentinelle en maquette.
**Conséquence** : deux niveaux de NAT (box, puis routeur Sentinelle). À documenter dans les limites.
**Date** : 2026-11-07

## 2. Routeur et switch dans la zone Sentinelle
**Choix** : le routeur et le switch font partie de Sentinelle.
**Pourquoi** : je veux les sécuriser moi-même (mots de passe, mises à jour, règles). Une panne du routeur coupe la zone Sentinelle, pas la maison.
**Date** : 2026-11-07

## 3. Règle par défaut : deny by default
**Choix** : tout flux non explicitement autorisé est bloqué et journalisé.
**Pourquoi** : un réseau ouvert par défaut expose tout ce qui n'a pas été pensé. Chaque ouverture doit être justifiée.
**Conséquence** : les invités (salon, VLAN 30) n'ont qu'Internet. Tout autre service s'ouvre au cas par cas.
**Date** : 2026-11-07

## 4. Pi-hole : emplacement
**Choix** : à trancher. Probablement sur le serveur de services, pas sur le routeur.
**Statut** : 🔁 à revoir.
**Date** : 2026-11-07

## 5. Routeur et serveur de services séparés
**Choix** : le routeur est le pare-feu de la zone, le serveur de services héberge les services (Vaultwarden, SSO, Restic, Syslog, Grafana, Pi-hole).
**Pourquoi** : isoler la panne et la compromission. Une panne du serveur coupe les services, pas la zone.
**Date** : 2026-11-07

## 6. Supervision limitée à deux machines
**Choix** : supervision du PC fixe et du serveur de services uniquement.
**Pourquoi** : je ne supervise que mes appareils. Portable, téléphone et famille restent hors périmètre.
**Date** : 2026-11-07

## 7. Rôle du vieux PC et choix du serveur
**Choix** : le vieux PC (8 Go) est probablement le serveur de services. Un mini PC (2 ports Ethernet, 16 Go) reste une option si le vieux PC est trop juste.
**Statut** : 🔁 à confirmer quand les ports Ethernet et la RAM seront vérifiés.
**Date** : 2026-11-07
