# Les méta caractères du shell

Les méta caractères sont utilises pour regrouper (générer) les noms des fichiers
qui ont des parties communes (qui ont certaines similitudes).

- *Le méta caractère \* (joker) :* Remplace n'importe quelle chaîne de caractères
dans le nom 48 d'un fichier, sauf le caractère *<<.>>* en première position (fichier
cachés). Par exemple l'expression *<<test*>> désigne tous les noms de fichiers,
relativement à un répertoire, qui commencent par le mot *<<test>>*.
