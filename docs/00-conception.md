# Conception : l'idée avec l'analogie de la maison

## Tableau d'analogie (maison → réseau)

| Maison | Équivalent réseau | Statut |
|---|---|---|
| **Porte d'entrée** | Routeur Sentinelle (filtre ce qui entre) | ✅ |
| **Porte de sortie** | Règles de sortie du pare-feu (filtre ce qui sort) | ✅ |
| **Fenêtre** | Port ouvert ou service exposé (peut laisser voir l'intérieur) | ✅ |
| **Interphone** | Identification (authentification, clé SSH, certificat) | ✅ |
| **Langage** | Chiffrement (TLS, VPN) | ✅ |
| **Mot de code** | Mot de passe, 2FA, clé SSH | ✅ |
| **Étages** | VLAN (zones séparées) | ✅ |
| **Escalier / couloirs** | Trafic entre zones, passant par le routeur et le switch | ✅ |
| **Caméra** | Logs et détection (Suricata, journaux) | ✅ |
| **Pièces et objets** | Machines et données à protéger (PC, serveurs, fichiers) | ✅ |
| **Vestibule** | DMZ : zone tampon où arrivent les services exposés, isolée du reste | ✅ |
| **Fausse chambre forte** | Honeypot : leurre attirant, observe les intrusions sans rien protéger | ✅ |
| **Chambre forte** | Zone des données et services critiques (Vaultwarden, sauvegardes), accès très restreint | ✅ |
| **Salon** | Zone invités gérée : accès accordé par toi au cas par cas, surveillé | 🔁 |

**Reste ouvert** : les services accessibles aux invités (à définir quand tu auras listé tes services, VPN compris).

## Journal

### 2026-11-07
- Tableau d'analogie maison complet (14 composantes), salon en 🔁, services invités à définir.
