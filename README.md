# Tp-Docker

Cloner le repo
- git clone <https://github.com/Arthur21000/Tp-Docker.git>

Avant de lancer, modifiez dans le docker-compose.yml la ligne 110   "- LOCAL_NETWORK=192.168.10.0/24" et mettez votre réseau

Lancer les conteneurs
- docker-compose up -d

Pour accéder à portainer pour administrer les conteneurs URL <ip machine:9000> 
Compte : admin/Admin33*

Pour accéder à Jackett URL <ip machine:9117>
Deux indexer sont déjà configurer OxTorrent et GkTorrent

Pour accéder à Radarr URL <ip machine:7878>


Pour accéder à Sonarr URL <ip machine:8989>


Pour accéder à Bazarr URL <ip machine:6767>


Pour accéder à Transmission-OPENVPN  URL <ip machine:9091>
Pour changer le compte VPN, allez dans le docker-compose.yml et changez les lignes 106 à 109
- OPENVPN_PROVIDER=<VPN>
- OPENVPN_CONFIG=
- OPENVPN_USERNAME=<nom>
- OPENVPN_PASSWORD=<password>

Pour accéder à la plateform de streaming final "Jellyfin" URL <ip machine:8096>
