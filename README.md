# Tp-Docker

Cloner le repo
- git clone <https://github.com/Arthur21000/Tp-Docker.git>

Avant de lancer, modifiez dans le docker-compose.yml la ligne 110   "- LOCAL_NETWORK=192.168.10.0/24" et mettez votre réseau

Lancer les conteneurs
- docker-compose up -d

Pour accéder à portainer pour administrer les conteneurs URL "ip machine:9000"

- Compte : admin/Admin33*

Pour accéder à Jackett URL "ip machine:9117"

- Deux indexer sont déjà configurer OxTorrent et GkTorrent

Pour accéder à Radarr URL "ip machine:7878"

- Pour ajouter les indexers de Jackett il faut aller dans "settings - indexers" puis ajoutez un indexers Torznab

![image](https://user-images.githubusercontent.com/56296245/157655186-2973c8c7-9725-4061-9fb5-7d37e32948c6.png)

- Faire la même chose pour OxTorrent

- Pour ajouter le download-client il faut aller dans "settings - download-client " puis ajoutez un client Transmission

![image](https://user-images.githubusercontent.com/56296245/157655912-7ed70841-b75c-411d-b7b7-2c0c074f17bb.png)

- Ajoutez ensuite le dossier où seront mis les films , allez dans "settings - media management" et "ADD ROOT FOLDER", ajoutez le chemin /radarr/movies. Si vous n'avez pas les droits faites la commande suivante : - chmod 777 chmod 777 TP-Docker/radarr/movies/

![image](https://user-images.githubusercontent.com/56296245/157659820-e00229ad-f673-4753-89d8-df538c438253.png)

Pour accéder à Sonarr URL "ip machine:8989"

- Pour ajouter les indexers et le download-client, faites la même chose que sur Radarr
- Ajoutez ensuite le dossier où seront mises les series, allez dans "settings - media management" et "ADD ROOT FOLDER", ajoutez le chemin /sonarr/tv. Si vous n'avez pas les droits faites la commande suivante : - chmod 777 chmod 777 TP-Docker/sonarr/tvseries/

![image](https://user-images.githubusercontent.com/56296245/157659660-91904012-18c2-46c0-a2ed-f2cb4ac303e2.png)


Pour accéder à Bazarr URL "ip machine:6767"

Pour accéder à Transmission-OPENVPN  URL "ip machine:9091"

Pour changer le compte VPN, allez dans le docker-compose.yml et changez les lignes 106 à 109
- OPENVPN_PROVIDER=VPN
- OPENVPN_CONFIG=
- OPENVPN_USERNAME=nom
- OPENVPN_PASSWORD=password

Pour accéder à la plateform de streaming final "Jellyfin" URL "ip machine:8096

- Connecter vous au serveur

![image](https://user-images.githubusercontent.com/56296245/157656794-903daabc-642c-45d1-9f04-0497565e60af.png)

- Ensuite vous arriver sur la page de configuration (Si c'est pas le cas recharger la page) puis suivez les instructions

- Ajoutez ensuite vos médiathèque (soit deux, une pour les films et une pour les séries)

![image](https://user-images.githubusercontent.com/56296245/157657359-2ee7a8ce-fb2b-41f1-92f5-fb33d942c1b5.png)

![image](https://user-images.githubusercontent.com/56296245/157657519-91745c2c-a2e1-41e0-a476-4ba206cf0bbc.png)

![image](https://user-images.githubusercontent.com/56296245/157657590-05ebc416-2478-4e00-8370-1685c8861dd8.png)

Pour la supervision:

- Dans un premier temps , il faut vérifier que la base de donnée time série , Prometheus dans notre cas, est bien en état de marche:
- Pour se faire , se connecter en "localhost:9090":
![image](https://user-images.githubusercontent.com/56296245/158546878-f8bfe356-90e7-4722-8001-5282441c9a98.png)

- Ensuite se connecter à Grafana en "localhost:3000", l'utilisateur par défaut est "admin" et le mot de passe "admin", une fois connecter le changement de mot de passe est obligatoire et proposé directement aprés.

- Il faut ajouter la base de donnée à grafana. Aller dans l'onglet configuration et ajouter la base de donnée Prometheus en "access:Browser"
![image](https://user-images.githubusercontent.com/56296245/158547093-16741354-255f-43c8-b121-392fffa297cd.png)

- Il ne reste plus qu'à ajouter un pannel , dans l'exemple ci-dessous nous avons choisis le nombre de bytes restants ,il y a aussi le gestionnaire des disques pour prouver que la métrique choisie n'est pas aléatoire.
![image](https://user-images.githubusercontent.com/56296245/158547302-6f565a8d-9f1d-4ff7-aeba-2db962cbfa2b.png)


