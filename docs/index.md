# Mon Site de Documentation

## Comment créer un site de documentation avec Mkdocs ?

1. télécharger Mkdocs avec la commande `pip install mkdocs`
2. J'avais pas pip donc je l'ai telechargé avec  `curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py` et installé via `python3 get-pip.py`
3. Après avoir installé Mkdocs ,j'ai suivi à la lettre la documentation de mkdocs accessible ici : [Mkdocs - Getting started](https://www.mkdocs.org/getting-started/)
4. Je me suis amusée à changer le thème en choisissant le thème `Dracula` : [Documentatin ici](https://draculatheme.com/mkdocs)

## Comment déployer un site de documentation Mkdocs avec Github ?
1. Pousser le repo en local vers le repo distant Github
2. Se mettre sur la branche Main du repo 
3. déployer avec la commande `mkdocs gh-deploy`

### [Repository du site mkdocs](https://github.com/elhayanich/chay_docu)

---------------------------------------------------------------


## Comment créer un site de documentation avec Github Pages ?

1. Créer repo sur github et le cloner  sur mon bureau ( dans mon cas je l’ai appelé mon_site_de_docu)
2. Y accéder via ma ligne de commande ( terminal) : cd nom de votre repo (dans mon cas c'éatit cd mon_site_de_docu)
3. Créer un fichier index.md ( mon fichier de markdown) : `nano index.md`
4. mettre notre documentation en Markdown (Titres avec Hashtags, texte sans les hashtags etc )
5. Pour enregistrer le fichier et quitter : `ctrl o` , `entrer` , `ctrl x`
6. Pour configurer le site, créer un fichier YAML avec la commande : `nano _config.yaml`
( Lien Utile : `https://quire.getty.edu/docs-v1/fundamentals/`) 
7. Étpae 5
8. Ensuite, suivre les étapes pour pousser notre travail vers le repo distant :  
`git add .` 
`git commit -m "votre message de commit"`
`git push` 
9. Sur votre profil Github, dans votre repo de doc : Aller dans `settings > Pages`
10. Déployer le site


## Comment mettre à jour la documentation ?

Pour mettre à jour la documentation, suivez les étapes ci-dessous :

1. Ouvrez le dossier `mon-site-de-docu` de votre projet.
2. Modifiez le fichier Markdown `index.md` correspondant à la documentation.
3. Enregistrez vos modifications:  `git add .` `git commit -m "votre message de commit"`
4. Poussez les changements vers le dépôt distant: `git push` 

### [Repository du site en  markdown avec Github](https://github.com/elhayanich/mon-site-de-docu)


## Le protocole HTTP (Exo 3) 

Requête HTTP: `GET https://dummyjson.com:443/recipes?limit=10 HTTP/2`

###### • Q : C’est quoi une requête HTTP ?
• A : C'est une demande initiée par le client en utilisant le protocole http afin d'obtenir des informations ou une ressource ou encore effectuer une action spécifique. Elle contient la méthode `GET` `PUT` `POST` ...etc, le chemin de la ressource `PATH` et la version du protocole http
###### • Q : C’est quoi un DNS ?
• A : `Domain name system`, il traduit les noms de domaines en adresses IP compréhensibles par les machines. Cela permet à un utilisateur de saisir un nom de domaine convivial dans un navigateur, plutôt que d'avoir à se souvenir d'une adresse IP complexe.
###### • Q : C’est quoi GET ?
• A : c'est une méthode qui nous permet de récuperer des informations d'une API. Les méthodes definissent les types d'opérations qu'un client veut effectuer 
###### • Q : C’est quoi https:// ?
• A : le `schéma` qui spécifie le protocole utilisé : le https veut dire qu'on veut utiliser le protocole http sécrusié et le :// est un délimitateur par convention qui sépare le protocole utilisé et la suite de l'url.
###### • Q : C’est quoi dummyjson.com ?
• A : c'ets un nom de domaine; dummyjson est 
###### • Q : C’est quoi 443 ?
• A : c'est le port de connexion 
###### • Q : C’est quoi recipes ?
• A : une endpoint
###### • Q : C’est quoi ? ?
• A : début de params
###### • Q : C’est quoi limit ?
• A : le prametre
###### • Q : C’est quoi 10 ?
• A : la valeur du paramètre
###### • Q : C’est quoi HTTP/2 ?
• A : La version du protocole HTTP
###### • Q : Que contient la réponse à cette requête ?
• A : bad request erreur 400, si on enlève le HTTP/2, ça nous renvoie une api avec un objet qui contient lui meme un tableau avec 10 objets
