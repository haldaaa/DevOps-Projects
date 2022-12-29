# DevOps-Projects




## Projet  1 :




-> Déploiement d'une application web JAVA avec son serveur de base de donnée (MariaDb), un serveur RabbitMq, Memcached et un serveur TomCat pré-configurés via des scripts shell.

-> Cloner le dépot et executer <code>"vagrant up"</code> 

-> L'installlation devrait durer entre 10 et 20 minutes.

-> Le fichier Vagrantfile appelle des scripts shells qui configure automatiquement chaque service

-> L'application doit être accessible via l'adresse publique Nginx




### Problème pendant l'installation :

1) Sur les Mac (puce ARM) : 

- Problème avec l'installation de vagrant host manager, la dépendance fog 1.43 est necessaire (j'ai la 1.45 installé)
Solution : telecharger la release 2.0.3 de vagrant sur le site officiel.

2) <code>vagrant up </code> : problème shared folder : relancer la commande avec les logs en error et normal semble contourner le problème

3) <code> vagrant up SSL certificate error </code> :   rajouter l'option <code> config.vm.box_download_insecure = true </code> dans le Vagrantfile

3) Erreur 502 : vérifier si Tomcat est bien lancé.

4) Erreur login application : vérifier si la base de donnée est active, que la table users avec les credentials sont bien présents, dans le cas contraire reconstruire la vm db01

