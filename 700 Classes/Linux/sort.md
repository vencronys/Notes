# La commande sort

Par defaut, les regles de tri sont:
- Les lignes commencant par un chifre apparaitront avant les lignes commencant par une lettre
- Les lignes commencant par une lettre minuscule apparaitront avant les lignes commencant par la meme lettre en majuscule

**Tri des ligne a partire d'un fichier**

> [!Syntax]
> ```bash
> sort [option] fiche
>```

La commande `sort` trie les lignes du fichier `fiche` et affiche le resultat sur la sortie standard.

> [!Options]
> - `-o`: permet de specifier le fichier dans lequel sera ecrit le resultat du tri.
> - `-n` numerique
> - `-d` le tri est effectue selon l'ordre defini dans un dictionnaire.
> - `-f` on ignore majuscules et miniscules.
> - `-r` reverse l'ordre.
> - `-b` ignore les espaces en debut de champ.
> - `-u` pour trier la liste et supprimer les doublons.
 
## Tri sure un champ particulier

> [!Syntax]
> ```bash
> sort [option] [-tcar] [-kpos1] [-kpos2] [fichier...]
>```

- Par defaut les champs sont delimites par une tabulation ou par espace.
- L'option `-tcar` permet de specifier un char qui designera le nouveau delimiteur de champs.
- `pos1` designe le premier champ et `pos2` designe le dernier champ, selon lesquels le trie s'effectuera.
- 