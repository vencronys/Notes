# La commande `read`

--cin copycat

echo `$REPLY` if var name is not specified, unless `read var1 var2`

La commande `read` peut etre utilisee pour la lecture d'un fichier.

>[!Exemplle]
> Sans utiliser la commande `read`, afficher la premiere ligne d'un fichier nomme `fiche`
> ```bash
> % head -n 1 < fiche
> ou
> % cat fiche | head -n 1
> ```


>[!Exemplle]
> en utilisant la commande `read`, afficher la premier ligne d'un fichier nomme `fiche`
> ```bash
> % cat fiche | read line
> % echo "$line"
> ou
> % read line < fiche
> % echo "$line"
> ```

