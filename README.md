
# PROJET DE MAJEURE - Virtualisation & Cloud

#### équipe 1 - VIGNAUD - MEUNIER - GRESLE

***

*Introduction* : L'objectif de ce projet est d'utiliser différentes fonctionnaliés de VMware vSphere afin de déployer un cloud privé. Le data center de CPE est utilisé comme infrastucture sur laquelle le cluster de virtualisation sera utilisé. L'architecture globale développée est la suivante:

***

1. *Installation et configuration ESXi :*

Dans un premier temps, nous devons créer deux hyperviseurs ESXi (type 1) qui auront pour rôle d'orchestrer l'exécution des différentes machines virtuelles et de leur allouer les ressources nécessaires en fonction de leurs besoin.

* Nous avons tout d'abord récupéré les images nécessaires (ESXi 7 et Windows Server 2012) qui étaient présentes dans le stockage *lunlibrary* du datacenter.

* Nous avons ensuite configuré les serveurs ESXi, premièrement,  nous avons configuré les disques durs en mode *Thin* afin de pouvoir mutualiser les ressources entre tous les groupes

* Ensuite nous avons mis 4 cartes réseau sur les machines de virtualisation, de façon à ce que celles cis puissent communiquer avec tous les port groupe (qui sont au nombre de 4 également)

* Nous avons configuré les adresses IP d’accès à chaque instance pour qu'elles appartiendra au réseau de management (de la forme 192.168.17.XX/XX)

* Le nom de domaine pour notre groupe est : *4eti-01.tpv.cpe.localdomain* 

* Nous avons finalement :





