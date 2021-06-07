
# PROJET DE MAJEURE - Virtualisation & Cloud

#### équipe 1 - VIGNAUD - MEUNIER - GRESLE

***

*Introduction* : L'objectif de ce projet est d'utiliser différentes fonctionnaliés de VMware vSphere afin de déployer un cloud privé. Le data center de CPE est utilisé comme infrastucture sur laquelle le cluster de virtualisation sera utilisé. L'architecture globale développée est la suivante:

***

1. *Installation et configuration ESXi :*

Dans un premier temps, nous devons créer deux hyperviseurs ESXi (type 1) qui auront pour rôle d'orchestrer l'exécution des différentes machines virtuelles et de leur allouer les ressources nécessaires en fonction de leurs besoin.

* Nous avons tout d'abord récupéré les images nécessaires (ESXi 7 et Windows Server 2012) qui étaient présentes dans le stockage *lunlibrary* du datacenter.

* Nous avons ensuite configuré les hyperviseurs ESXi, premièrement,  nous avons configuré les disques durs en mode *Thin* afin de pouvoir mutualiser les ressources entre tous les groupes

* Ensuite nous avons mis 4 adaptateurs réseau sur les ESXi afin de se connecter aux quatre réseaux de l'infrastructure. Dans un premier temps, un standard switch par port sera mis en place. Les ports attribués à notre groupe ont les IDs 101,102,103.

* Le nom de domaine pour notre groupe est : *4eti-01.tpv.cpe.localdomain* 

* Le plan d'adressage utilisé pour le premier ESXi est le suivant, les adresses Ip statiques ont été configurées de la manière suivante:

![plan](https://github.com/GuillaumeGrs/projetmajeure/blob/master/Capture.JPG)




2. *Configuration du stockage NAS*

* Un serveur NAS a été mis en place avec l'outil TrueNAS son adresse sur le réseau de management est 192.168.17.62/24. L'interface réseau NAS qui nous a été attribuée sur le réseau de stockage est 172.16.1.1/24 (em2). Il s'agit d'un réseau de stockage partagé qui nous servira pour la suite, cette interface em2 est connectée sur notre réseau de stockage. On attribue le stockage à nos deux ESXi via un adaptateur ISCSI qui "écoute" le NAS sur l'interface 172.16.1.254 pour ESXi1 et 172.16.1.253 pour ESXi2.


3. *Mise en place du contrôleur de domaine*

* Sur ESXi1, nous avons créé une première machine virtuelle sous Windows Serveur 2012, sur laquelle nous avons installé les rôles et les fonctionnalités suivantes pour installer un controleur de domaine:
                                     - DNS (la recherche inversé a été 
                                     - AD DS
                                     - DHCP (pour attribuer les addresses IP aux machines sur le réseau Prod)

* A présent l'active directory est mis en place, des utilisateurs "classiques" sont créés. Avec la mise en place de l'ensemble AD DS et DNS, il est possible de se connecter à n'importe quel utilisateur ou administrateur sur n'importe quelle machine cliente (qui tournent également sous Windows Serveur). Pour cela, les machines clientes ont été ajoutées dans notre domaine 4eti-01.tpv.cpe.localdomain.
    








