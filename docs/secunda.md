# Comment créer un site de documentation avec Mkdocs ?

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


# Comment créer un site de documentation avec Github Pages ?

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


# Comment mettre à jour la documentation ?

Pour mettre à jour la documentation, suivez les étapes ci-dessous :

1. Ouvrez le dossier `mon-site-de-docu` de votre projet.
2. Modifiez le fichier Markdown `index.md` correspondant à la documentation.
3. Enregistrez vos modifications:  `git add .` `git commit -m "votre message de commit"`
4. Poussez les changements vers le dépôt distant: `git push` 

### [Repository du site en  markdown avec Github](https://github.com/elhayanich/mon-site-de-docu)