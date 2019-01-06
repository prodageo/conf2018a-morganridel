# Avec les GitLab Runners, comme Mickey dans Fantasia, devenez un apprenti sorcier de l'intégration continue (et du déploiement) 

## Cartouche d'identification

 - Manifestation : CodeursEnSeine 2018
 - Lieu : Kindarena Métropole Rouen Normandie
 - Conférence : Avec les GitLab Runners, comme Mickey dans Fantasia, devenez un apprenti sorcier de l'intégration continue (et du déploiement) 
 - Horaire de la conférence : 14h30
 - Durée de la conférence : 50 minutes
 - Conférencier(s) :
   - Philippe Charrière ([LinkedIn](https://www.linkedin.com/in/phcharriere/), [Github](https://github.com/k33g), [Twitter](https://twitter.com/k33g_org))
 - Audience : ...
 - Auteur du billet : Morgan Ridel
 - Mots-clés
 - URL de l'illustration : ![Conférence GitLab Runners](conf-gitlab.jpg)
 
## Support
 - Lien vers le support (diapos) présenté en conférence : Indisponible
 - Nombre de diapos du support :
 - Plan du support :

## Résumé
Aujourd'hui GitLab tente de fournir les outils permettant de gérer le cycle entier de vie du DevOps, en particulier via GitLab CI. Le principe est simple, un fichier de configuration `.gitlab-ci.yml` est placé à la racine du projet. Ce fichier définit toutes les étapes (jobs) de notre chaine d'intégration: test, build, deploiement... ainsi que différentes options. En installant ce qu'on appelle un runner sur une machine, on peut ensuite faire executer automatiquement la chaine d'intégration à l'aide d'une pipeline à chaque push de commit sur le dépôt. L'état de cette pipeline est visible depuis l'interface Web de GitLab. Le chaine d'intégration est entièrement personalisable, on peut assigner des opérations uniquement à certaines branches, générer des fichier "artefact" à chaque exécution ou faire tourner n'importe quel script.

La conférence est majoritairement technique, l'intérêt de GitLab CI est décrit comme ci-dessus puis des démonstrations montrent en direct l'utilisation de petites chaine d'intégration. On voit que chaque commit déclenche une pipeline, où des tests sont effectués et un fichier rapport est créé en tant qu'artefact. Il est montré qu'il est facile de déployer une application sur différentes plateforme Cloud comme la plateforme Serverless [OpenFaaS](https://github.com/openfaas/faas) et sur [Clever-Cloud](https://www.clever-cloud.com/en/). On voit donc comment fonctionnent les runners GitLab puis le résultat avec la mise à jour en direct de la "production" sur les services Cloud.

## Architecture et facteur qualité
Le facteur qualité lié à cette conférence selon la norme ISO9126:2001 est la Maintainability (Maintenabilité). En effet, la chaine d'intégration mise en place par GitLab CI va permettre de modifier et mettre à jour le projet et de le déployer en production tout en s'assurant que les tests passent. Cela correspond aux sous facteurs de ce facteur comme la Testability mais aussi la Stability car des modifications entrainant des effets indésirables feront échouer la pipeline, empêchant les problèmes d'arriver en production. L'Analyzability est aussi un sous-facteur adapté, car la pipeline fait office de monitoring permettant de diagnostiquer les erreurs.
En règle générale, GitLab CI permet la maintenance d'un projet en assurant les étapes allant de la vérification du code jusqu'au déploiement tout en étant capable d'interrompre le processus si une erreur émerge.
