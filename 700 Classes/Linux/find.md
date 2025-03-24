# La commande `find`

Permet de cherche dans un repertoire (repere de base) et dans toute l'arborescence
depuis ce repertoire (on explore recursivement le repertoire et ces sous repertoires)
les fichiers verifiant certains criteres.

> [!Syntax]
> ```bash
> find repertoire [criteres] [options]
> ```

Si le critere n;'est pas specifie, alors la commande `find` affiche recursivement tous les repertoires et fichiers du repertoire precise dans l invite de commande.

- L'option `-print` permet d'afficher les resultats de la recherche sur la sortie standard.
- L'option `-name` fait une recherche sur le nom de fichier. On peut utiliser les metacaracteres.
- L'option `-type` permet de faire un e recherche par type de fichier.
	- `f` pour fichier normal.
	- `d` pour repertoire
	- `l` pour lien symbolique
	- `p` pour les tubes nommes (pipes)
- Les options `-user` et `-group` permettent de chercher les fichiers et repertoires verifiant les criteres sur le nom du proprietaire et du group,

> [!example]
> ```bash
> find /home -name main.c -print
>```

