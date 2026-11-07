# Contexte

## Besoin
Sécuriser une zone de mon réseau domestique et la transformer en lab permanent, pour apprendre et démontrer des compétences en sécurité réseau.

## Périmètre (dedans)
- PC fixe principal (Windows 11, 16 Go RAM) : zone admin
- PC portable : zone postes
- Téléphone : zone postes (Wi-Fi, plus tard)
- Vieux PC (8 Go) : rôle à définir, pas encore inclus
- Routeur et switch Sentinelle : à acheter, à l'intérieur de la zone

## Hors périmètre
- Appareils des autres personnes de la maison : je ne les gère pas, je ne les inspecte pas
- Box internet : configurée en mode bridge, elle ne fait que la liaison
- Accès à distance (VPN externe) : pas pour l'instant

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
