# Linux prep

## Commands

### head

By default it shows the the first 10 lines.

#### Options

- `-q`: n'affiche pas le nom du fichier. (quite)
- `-v`: affiche le nom du fichier avant. (verbose)
- `-n v`: will show the first `v` number of lines.
- `-c v`: shows `v` number of first chars.

### tail

By default it shows the last 10 lines.

#### Options

- `-c v`: shows `v` number of last chars.
- `-n -v`: shows the last `v` number of lines.
- `-n +v`: displays from the `v`th line till the end.

### find
Finds files inside dirs.

`find rep [criteres] [options]`

#### Options

- `-print`: print the results.
- `-name`: search using a name, can use metachars.
- `-type`: search using the type `f,d,l,p`.
- `-user`: search using the user.
- `-group`: search using the group.


### sort

Sorts content, by default it sorts numbers first, then lowercase letters and before last capital letters and finally any special char.

#### Options

- `-o`: output file.
- `-n`: numeric order.
- `-d`: dictionnairy order.
- `-f`: case insensitive.
- `-r`: reverse order.
- `-b`: ignores space in the beginning.
- `-u`: ignore doubles.
- `-tcar`: specify `car` as delimiter (by default it's space or tabs).
- `-kpos1 -kpos2`: picks a column index (starts at pos1 ends at pos2).

### grep

Search for a pattern in a file(s).

`grep [options] regex [file(s)]`

#### Options

| Option   | Description                                                                  |
|----------|-------------------------------------------------------------------------------|
| `-i`     | Ignore la casse (majuscule/minuscule).                                       |
| `-v`     | Affiche les lignes **ne contenant pas** le motif recherché.                  |
| `-c`     | Affiche le **nombre** de lignes contenant le motif.                          |
| `-n`     | Affiche les **numéros** des lignes correspondantes.                          |
| `-l`     | Affiche **uniquement les noms des fichiers** contenant le motif.             |
| `-L`     | Affiche les **fichiers ne contenant pas** le motif.                          |
| `-r` / `-R` | Recherche **récursive** dans les sous-dossiers.                          |
| `-w`     | Recherche le **mot exact** (évite les sous-mots).                            |
| `-x`     | Affiche uniquement les **lignes correspondant exactement** au motif.         |

| Option     | Description                                         | Exemple                               |
|------------|-----------------------------------------------------|----------------------------------------|
| `-A N`     | Affiche **N lignes après** la ligne trouvée         | `grep -A2 "mot" fichier.txt`           |
| `-B N`     | Affiche **N lignes avant** la ligne trouvée         | `grep -B3 "mot" fichier.txt`           |
| `-C N`     | Affiche **N lignes avant et après** la ligne        | `grep -C2 "mot" fichier.txt`           |


### wc

Word count.

#### Options

| Option   | Description                                                       |
|----------|-------------------------------------------------------------------|
| `-l`     | Affiche **le nombre de lignes**.                                  |
| `-w`     | Affiche **le nombre de mots**.                                    |
| `-c`     | Affiche **le nombre d’octets** (taille brute du fichier).         |
| `-m`     | Affiche **le nombre de caractères** (utile pour fichiers UTF-8).  |
| `-L`     | Affiche **la longueur de la plus longue ligne**.                  |


## Metachars

- `*`: Joker.
- `?`: any one char excepts `.`.
- `[]`: a char from the chars inside the brackets.
- `[-]`: a char from the sequence of chars inside the brackets.
- `[^]/[!]`: any char but the ones inside the brackets.

## Regex

| Symbole   | Signification                                               | Exemple                                 |
|-----------|-------------------------------------------------------------|-----------------------------------------|
| `.`       | N'importe quel caractère sauf un retour à la ligne          | `a.b` → correspond à `"acb"`, `"a3b"`…  |
| `^`       | Début d'une ligne                                           | `^Hello` → correspond à `"Hello"` en début de ligne |
| `$`       | Fin d'une ligne                                             | `end$` → correspond à `"end"` en fin de ligne |
| `*`       | Répète 0 ou plusieurs fois le caractère précédent           | `a*b` → `"b"`, `"ab"`, `"aaab"`…        |
| `+`       | Répète 1 ou plusieurs fois le caractère précédent           | `a+b` → `"ab"`, `"aaab"` mais pas `"b"` |
| `?`       | Rend le caractère précédent optionnel (0 ou 1 fois)         | `colou?r` → `"color"` ou `"colour"`     |
| `{n}`     | Répète exactement n fois                                    | `a{3}` → `"aaa"`                        |
| `{n,}`    | Au moins n répétitions                                      | `a{2,}` → `"aa"`, `"aaa"`, `"aaaa"`…    |
| `{n,m}`   | Entre n et m répétitions                                    | `a{2,4}` → `"aa"`, `"aaa"`, `"aaaa"`    |
| `[]`      | Classe de caractères                                        | `[aeiou]` → n'importe quelle voyelle    |
| `[^]`     | Exclure une classe                                          | `[^0-9]` → tout sauf des chiffres       |
| `\d`      | Chiffre (`[0-9]`)                                           | `\d+` → `"123"`, `"456"`…               |
| `\D`      | Tout sauf un chiffre (`[^0-9]`)                             |                                         |
| `\w`      | Lettre, chiffre ou `_` (`[a-zA-Z0-9_]`)                     |                                         |
| `\W`      | Tout sauf lettre, chiffre ou `_` (`[^a-zA-Z0-9_]`)          |                                         |
| `\s`      | Espace, tabulation, saut de ligne                           |                                         |
| `\S`      | Tout sauf un espace                                         |                                         |
| `\|`      | OU logique                                                  | `(a\|b)+` → `"aa"`, `"bbab"`…           |
| `()`      | Groupe capturant                                            | `(ab)+` → `"ab"`, `"abab"`…             |
| `\b`      | Délimiteur de mot                                           | `\bchat\b` → `"chat"` mais pas `"château"` |

## Bash scripting

```bash
#!/bin/bash
# your code here
exit 0
```

### 🧾 4.3. Les paramètres spéciaux en Shell

Ce sont des **variables réservées**. Certaines sont liées aux **arguments passés** au script shell.  
Pour les utiliser, on les précède du symbole `$`.

| Paramètre | Signification                                                                 |
|-----------|-------------------------------------------------------------------------------|
| `$0`      | Nom du script shell                                                           |
| `$*`      | Liste de tous les arguments sous **forme d'une seule chaîne**                 |
| `$@`      | Liste de tous les arguments sous **forme de plusieurs arguments séparés**    |
| `$#`      | Nombre total d’arguments passés au script                                     |
| `$?`      | Code retour de la **dernière commande exécutée**                             |
| `$$`      | PID du processus qui exécute le script (sous-shell lancé par le shell parent) |
| `$!`      | PID du **dernier processus lancé en arrière-plan**                           |

🧠 **Astuce :**  
Utilise `"${@}"` avec des guillemets pour préserver l'intégrité de chaque argument avec espaces.
