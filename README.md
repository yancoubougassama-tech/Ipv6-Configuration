# Ipv6-Configuration
## Objetctif du projet
Ce projet consiste à configurer et tester un réseau IPv6 en utilisant des équipements Cisco Systems (routeurs, switches). L'objectif est de comprendre l'adressage IPv6.Configuration automatiquement via SLAAC, permettant aux clients de générer leurs adresses Link‑Local et Global Unicast et une configuration statique des adresses ipv6 des serveurs, routeur et switches.
## Architecture du réseau
## Routeur R1 (Cisco 2811)
- F0/0: 2001:DB8:1:1::1/64
- F1/0: 2001:DB8:1:2::1/64
- Link-local:FE80::1
## Serveurs
- Acounting: 2001:DB8:1:1::2/64
- CAD: 2001:DB8:1:2::2/64
- Gateway: FE80::1
## Clients
- Sales: SLAAC
- Billing: SLAAC
- Design: 2001:DB8:1:2::3/64
- Engineering: 2001:DB8:1:2::4/64
- Gateway: FE80::1
## Notes configuration des postes clients
Les clients du réseau sont configurés selon deux modes complémentaires.
- Sales & Billing: utilisent l’autoconfiguration IPv6 (SLAAC), ce qui leur permet d’obtenir automatiquement une adresse Global Unicast et la passerelle via le Router
- Design & Engineering: eçoivent une configuration statique et la gateway Link‑Local
## Test réseau
- Ping
- Traceroute
- Accès web
## Commandes principales utilisées
- ipv6 unicast-routing: (active le routage ipv6)
- ipv6 address "adresse"/"prefix": ( configure une adresse ipv6 statique)
- ipv6 address "prefix" EUI-64: (génère automatiquement une adresse ipv6 via EUI-64)
- ipv6 address fe80::1 link-local: ( Définit manuellement l’adresse Link‑Local.)
- no shutdown: (active l'interface réseau)

