# Les méta caractères du shell

Les méta caractères sont utilises pour regrouper (générer) les noms des fichiers
qui ont des parties communes (qui ont certaines similitudes).

## `*`

*Le méta caractère \* (joker) :* Remplace n'importe quelle chaîne de caractères
dans le nom 48 d'un fichier, sauf le caractère `.` en première position (fichier
cachés). Par exemple l'expression `test` désigne tous les noms de fichiers,
relativement à un répertoire, qui commencent par le mot `test`.

> [!EXAMPLE]
>
> ```bash
> $ ls .zsh* # Listera tous les fichier qui commencent avec .zsh
> ```

## `?`

*Le méta caractère `?` :* Remplace (masque) n'importe quel caractère sauf le
point `.` en première position.

> [!EXAMPLE]
>
> ```bash
> $ ls main.? # Listera tous les fichier qui commencent avec main. et termine avec un char, ex: main.h
> ```

## `[]`

*Les méta caractères les crochets `[]` :* Désigne un seul caractère parmi les
caractères qui sont donnés entre crochets `[]`.

> [!EXAMPLE]
>
> ```bash
> $ ls main.[h,c] # Listera tous les fichier qui commencent avec main. et termine avec soit h ou c
> ```

## `[-]`

*Les méta caractères `[-]` :* Désigne un seul caractère parmi la séquence de
caractères définie entre les crochets `[]`.

> [!EXAMPLE]
>
> ```bash
> $ ls [a-zA-Z]* # Listera tous les fichier qui commencent avec une lettre minuscule ou majuscule
> ```

## `[^]` ou `[!]`

*Les méta caractères `[^]` ou `[!]`:* Désigne n'importe quel caractère sauf ceux
donnés entre crochets.

> [!EXAMPLE]
>
> ```bash
> $ ls [!a-zA-Z]* # Listera tous les fichiers qui ne commencent pas avec une lettre minuscule ou majuscule.
> ```
