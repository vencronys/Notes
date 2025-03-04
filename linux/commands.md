# Commandes

## more

Affiche sur la sortie standard, le contenu des fichiers, spécifiés en argument
de la commande, l'un après l'autre et page écran par page écran :
Pour visualiser la page suivante, on tape sur la touche `SPACE`.
- Pour visualiser la ligne suivante, on tape sur la touche `RETURN`.
- Pour terminer la visualisation, on tape sur la touche `q` ou `Q`.

## head et tail

### head

Permet d'afficher sur la sortie standard les débuts des fichiers passés en argument
de la commande, l'un après l'autre.

>**Syntaxe:**
>
>```bash
>head [-q][-c nbcar][-n nbligne] [fichier1, ...]
>```

### tail

Elle permet d'afficher sur la sortie standard les dernières lignes des fichiers
passés en argument de la commande fichier.

>**Syntaxe:**
>
>```bash
>tail [-c nbcar][-n +/-nbligne] [fichier1, ...]
>```

- Par défaut, la commande afficher les 10 dernières lignes de chaque fichier
  passé en argument.
