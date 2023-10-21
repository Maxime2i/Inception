# Inception

Ce projet de l'école 42 vise à élargir vos connaissances en administration système en utilisant Docker. En utilisant plusieurs images Docker, en les créant dans votre machine virtuelle.

## Definition

##### Fonctionnement de Docker : 
Docker est une application qui permet d'emballer une application et ses dependances dans un conteneur :
	
 - **conteneur** : logiciel autonome qui contient une application et toutes ses dépendances
 - **images** : modèle de base à partir duquel les conteneurs sont créés
 - **dockerfile** : fichier texte dans lequel vous spécifiez comment construire une image Docker


##### Fonctionnement de Docker Compose : 
Docker-compose outil qui facilite le déploiement et la gestion de plusieurs conteneurs Docker qui travaillent ensemble pour former une application plus complexe :
	
 - **Fichier de configuration** : "docker-compose.yml" dans le répertoire du projet, qui contient des informations tel que l'image Docker à utiliser, les ports à exposer, les volumes à monter, les variables d'environnement
 - **Lancement de l'application** : Docker Compose lit le fichier de configuration et crée les conteneurs en fonction des spécifications
 - **Gestion des conteneurs** : permet de  démarrer, arrêter et surveiller tous les services en une seule commande

##### Pourquoi utiliser Docker plutot qu'une VM :

  - **efficacite des ressources** : les conteneurs partagent le meme noyau du systeme d'exploitation (plus leger que les VM qui ont un OS complet)
  - **isolation** : les conteneurs sont isole les un des autres (contrairement aux VM) mais partagent des ressources de maniere plus efficace
  - **portabilite** : les VM sont dependanstes de leur infrastructure alors que les conteneur fonctionne de la meme maniere sur n'importe quel environnement
  - **deploiement rapide** : les conteneurs sont deploye rapidement par rapport aux VM qui doivent configurer l'OS complet
  - **gestion simplifie** : Docker-compose permet de gerer plusieurs docker en meme temps alors que les VM necesittent des outils suplementaires
  - **meilleur mise a l'echelle** : augmenter les capacites de conteneur est plus simple que pour une VM (par leur taille et leur consomation de ressources)
  - **communaute** : beaucoup plus de ressources et d'outils pour les conteneurs


  ## Commandes Docker les plus utiles
  
   **docker build** : utilisé pour créer une image Docker à partir d'un fichier Docker.
   
   **docker run** : utilisé pour exécuter un conteneur Docker basé sur une image Docker.
   
   **docker pull** : utilisé pour extraire une image Docker d'un registre, tel que Docker Hub.
   
   **docker push** : utilisé pour envoyer une image Docker vers un registre.
   
   **docker ps** : utilisé pour répertorier les conteneurs Docker en cours d'exécution sur un système.
   
   **docker stop** : utilisé pour arrêter un conteneur Docker en cours d'exécution.
   
   **docker rm** : utilisé pour supprimer un conteneur Docker.
   
   **docker rmi** : Utilisé pour supprimer une image Docker.
   
   **docker exec** : utilisé pour exécuter une commande dans un conteneur Docker en cours d'exécution.
   
   **Journaux Docker** : utilisés pour afficher les journaux d'un conteneur Docker.

   
  ## Dockerfile 

  Un fichier Dockerfile est un script utilisé pour créer une image Docker, il contient une série d'instructions qui décrivent comment construire l'image. Voici quelques-unes des instructions couramment utilisées dans un Dockerfile :

  **FROM** : il s'agit d'une commande utilisée dans un fichier Docker pour spécifier l'image de base à utiliser comme point de départ pour créer l'image Docker. L'image de base fournit les calques de base de l'image, et vous pouvez ensuite ajouter des calques supplémentaires par-dessus pour personnaliser l'image en fonction de vos besoins spécifiques.
  
  **RUN** : Il s'agit d'une commande utilisée dans un Dockerfile pour exécuter une commande dans le terminal du conteneur. Il est généralement utilisé pour installer des logiciels ou des bibliothèques nécessaires à l'application.
 
  **CMD** : il s'agit d'une commande utilisée dans un Dockerfile pour spécifier la commande par défaut qui doit être exécutée lorsqu'un conteneur est démarré à partir de l'image. Il est utilisé pour spécifier la commande principale que le conteneur doit exécuter lors de son démarrage.
 
  **services** : il s'agit d'une clé dans un fichier Docker Compose qui est utilisée pour définir les services qui composent votre application. Un service est un conteneur qui exécute une application ou un composant spécifique de votre application.
  
  **volumes** : il s'agit d'une clé dans un fichier Docker Compose qui est utilisée pour définir le stockage persistant de votre application. Un volume est un élément de stockage attaché à un conteneur et utilisé pour stocker des données qui doivent persister même lorsque le conteneur est arrêté ou supprimé.
 
  **networks** : il s'agit d'une clé dans un fichier Docker Compose qui est utilisée pour définir les réseaux auxquels les conteneurs doivent être connectés. Un réseau est un réseau virtuel utilisé pour connecter les conteneurs et leur permettre de communiquer entre eux.
  
  **ENTRYPOINT** : specifie les commendes ou executables qui s'executeront tout de suite apres le demarage du conteneur

  

  ## Les 3 conteneurs a cree

  **nginx** : serveur web open source très populaire, ainsi qu'un serveur proxy inverse. Il est conçu pour gérer la distribution de requêtes web, le chargement équilibré de serveurs backend, et le serveur de fichiers statiques
  
  
  **wordpress** : système de gestion de contenu (CMS) open source très populaire, largement utilisé pour la création et la gestion de sites web et de blogs, facilité d'utilisation et grande flexibilité
  
  
  **mariaDB** : système de gestion de base de données relationnelle open source qui est une bifurcation (fork) de MySQL. Il est conçu pour être une alternative compatible avec MySQL tout en offrant des améliorations et des fonctionnalités supplémentaires


 ## Quelques infos a savoir 

- **pertinnence de la structure des dossiers** : favorise l'isolation, la reproductibilité, la maintenance, la sécurité, la gestion des volumes, la clarté, et la compatibilité avec les outils. Cela facilite donc le developpement et le deploiement des conteneurs


- **Docker-network** : un outil essentiel pour la gestion de la connectivité réseau des conteneurs Docker. Il permet de créer des réseaux virtuels, d'isoler des groupes de conteneurs, de configurer la connectivité avec des ressources externes et de garantir la sécurité et la cohérence des communications entre les conteneurs


- **Diff entre http et https** : HTTP (HyperText Transfer Protocol) et HTTPS (HyperText Transfer Protocol Secure), la principale différence entre HTTP et HTTPS réside dans la sécurité des données. HTTPS utilise un chiffrement SSL/TLS pour protéger les informations lors de leur transfert sur Internet, tandis qu'HTTP ne le fait pas, exposant les données à des risques potentiels d'interception. Donc HTTPS est plus utilisé pour sécuriser les transactions en ligne, les connexions aux sites Web, et garantir la confidentialité des données.


- **cetificat SSL/TLS** : (Secure Sockets Layer/Transport Layer Security), fichier électronique qui lie de manière cryptographique une clé publique à des informations spécifiques sur une entité, il assure la confidentialité et la sécurité des données échangées avec les utilisateurs


- **comment se connecter a la DataBase** :

	- docker exec -it mariadb bash
	- mysql -u root -p
	- 'entrer le mdp'
	- SHOW DATABASES;
	- USE wordpress;
	- SHOW TABLES;


- **verifier que nginx est accessible par le port 443** :
	- srcs/requirements/conf/default


- **ouvrir le certificat SSL/TLS** :
	- login.42.fr --> 🔒 --> Connexion non securise --> Plus d'information --> Securite --> Afficher le certificat


- **montrer le nom des images docker** :
	- docker ps


- **verifier que le certificat est TLS v1.2/v1.3** :
	- (Transport Layer Security, deux version du protocole TLS, 1.3 sorti en 2018 est la plus recente et la plus securise)
	- srcs/requirements/mariadb/conf/50-server.cnf


- **verifier les volumes des docker** : 
	- docker volume ls
	- docker volume inspect <nom_du_volume>

 
