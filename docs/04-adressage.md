# Plan d'adressage

## Plages par zone
| Zone | VLAN | Plage | Passerelle | Attribution |
|---|---|---|---|---|
| Gestion (équipements réseau) | 99 | À compléter | À compléter | Fixe |
| Admin | 10 | À compléter | À compléter | DHCP + réservations |
| Postes | 20 | À compléter | À compléter | DHCP |
| Salon (invités gérés) | 30 | À compléter | À compléter | DHCP |
| Vestibule (DMZ) | À compléter | À compléter | À compléter | Fixe |
| Chambre forte | À compléter | À compléter | À compléter | Fixe |

## Adresses fixes par service
| Service | Zone | Adresse | Port |
|---|---|---|---|
| VPN (WireGuard) | Vestibule | À compléter | À compléter |
| SSO / 2FA | Chambre forte | À compléter | À compléter |
| Vaultwarden | Chambre forte | À compléter | À compléter |
| Restic (sauvegardes) | Chambre forte | À compléter | À compléter |
| Syslog | Chambre forte | À compléter | À compléter |
| Grafana / Prometheus | Chambre forte | À compléter | À compléter |
| Pi-hole (DNS) | À compléter (voir décision 4) | À compléter | 53 |
| Samba | Zone admin ou postes | À compléter | 445 |
| Jellyfin | Zone admin ou postes | À compléter | 8096 |
| Honeypot (Cowrie) | Vestibule | À compléter | 2222 |

## Règles
- Une adresse par service, jamais deux services sur la même adresse.
- Les plages des zones ne se chevauchent pas.
- Toute adresse fixe est notée ici avant d'être configurée.
