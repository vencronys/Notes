# grep

La commande `grep` cherche, dans un fichier passe en argumentt, les lignes qui verifient le critere de recherche (les lignes qui contiennet) l'expression reguliere precisee sur la ligne de commande), et affiche les lignes trouvees sur la sortie standard (ecran).

> [!Syntaxe]
> ```bash
> grep [options] regex [liste-de-fichiers]
>```

## Les principales Options de grep


| **Option**   | **Description**                                                  |
| ------------ | ---------------------------------------------------------------- |
| `-i`         | Ignore la casse (majuscule/miniscule).                           |
| `-v`         | Affiche les lignes ne contenet pas le motif recherche.           |
| `-c`         | Affiche le nombre de lignes contenant le motif.                  |
| `-n`         | Affiche les numeros des lignes correspondantes.                  |
| `-l`         | Affiche uniquement les noms des fichiers contenant le motif.     |
| `-L`         | Affiche les fichiers ne contenant pas le motif.                  |
| `-r` ou `-R` | Recherche recursive dans les sous-repertoires.                   |
| `-w`         | Recherche le mot exact (evite les sous-mots).                    |
| `-x`         | Affiche uniquement les lignes correspondant exactement au motif. |

## Les options pour afficher des lignes de contexte


| **Option** | **Description**                           | **Exemple**                  |
| ---------- | ----------------------------------------- | ---------------------------- |
| `-An`      | Affiche `n` lignes apres la ligne trouvee | `grep -A2 "mot" fichier.txt` |
| `-Bn`      | Affiche `n` lignes avant la ligne trouvee | `grep -B3 "mot" fichier.txt` |
| `-Cn`      | Affiche `n` ligne avant et apres          | `grep -C2 "mot" fichier.txt` |
