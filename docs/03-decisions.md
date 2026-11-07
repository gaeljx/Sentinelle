# Décisions

## 1. Mode de la box
**Choix** : bridge (pont). La box ne fait que la liaison Internet.
**Pourquoi** : le routeur Sentinelle doit être la seule passerelle, pour contrôler tout le trafic.
**Avant** : routeur normal (rejeté : deux niveaux de NAT, la box garde un regard sur le réseau).
**Date** : 2026-11-07

## 2. Routeur et switch dans la zone Sentinelle
**Choix** : le routeur et le switch font partie de Sentinelle.
**Pourquoi** : je veux les sécuriser moi-même (mots de passe, mises à jour, règles).
**Date** : 2026-11-07

## 3. Règle par défaut : deny by default
**Choix** : tout flux non explicitement autorisé est bloqué et journalisé.
**Pourquoi** : un réseau ouvert par défaut expose tout ce qui n'a pas été pensé. Chaque ouverture doit être justifiée.
**Conséquence** : les invités (salon, VLAN 30) n'ont qu'Internet. Tout autre service s'ouvre au cas par cas.
**Date** : 2026-11-07

## 4. Pi-hole : emplacement
**Choix** : à trancher (zone admin ou serveur dédié).
**Statut** : 🔁 à revoir.
**Date** : 2026-11-07
