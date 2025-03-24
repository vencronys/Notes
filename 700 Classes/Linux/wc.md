# La commande `wc`

La commande `wc` (Word Count) permet de compter le nombre de lignes, de mots, de caracteres et d'octets dans un fichier ou une entree standard.

>[!Syntaxe]
> ```bash
> wc [option] [fichier]
>```

Sans option, wc affiche trois nombre dans cet ordre:
1. Nombre de lignes
2. Nombre de mots
3. Nombre de caracteres (ou octets)


| **Option** | **Description**                                                     |
| ---------- | ------------------------------------------------------------------- |
| `-l`       | Affiche uniquement le nombre de lignes.                             |
| `-w`       | Affiche uniquement le nombre de mots.                               |
| `-c`       | Affiche le nombre d'octets (taille du fichier en octets).           |
| `-m`       | Affiche le nombre de caracteres (utilie pour les fichier en UTF-8). |
| `-L`       | Affiche la longeur de la plus longue ligne.                         |
