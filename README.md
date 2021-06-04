
# PROJET DE MAJEURE

#### équipe 1 - VIGNAUD - MEUNIER - GRESLE

***

*Introduction* : 

***

1. *Installation et configuration ESXi :*

Dans un premier temps, nous devons créer des serveurs ESXi qui auront pour rôle de gérer l'exécution des machines virtuelles et de leur allouer les ressources nécessaires en fonction de leurs besoin.

* Nous avons tout d'abord installé les images des serveurs qui étaient présentes dans le stockage *lunlibrary* de VMWare

* Nous avons ensuite configuré les serveurs ESXi, premièrement,  nous avons configuré les disques durs en mode *Thin* afin de pouvoir mutualiser les ressources entre tous les groupes

* Ensuite nous avons mis 4 cartes réseau sur les machines de virtualisation, de façon à ce que celles cis puissent communiquer avec tous les port groupe (qui sont au nombre de 4 également)

* Nous avons configuré les adresses IP d’accès à chaque instance pour qu'elles appartiendra au réseau de management (de la forme 192.168.17.XX/XX)

* Le nom de domaine pour notre groupe est : *4eti-01.tpv.cpe.localdomain* 

* Nous avons finalement :





![image test](https://github.com/GuillaumeGrs/projetmajeure/blob/master/MicrosoftTeams-image.png)
