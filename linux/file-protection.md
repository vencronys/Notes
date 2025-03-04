# Protection des fichier

## Droit d'acces aux fichiers

A chaque fichier est associe en ensemble d'indicateurs precisant les droits
d'acces au fichier.

Pour chaque fichier il existe trois types d'utilisateurs :

- le proprietaire du fichier
- les membres du groupe proprietaire du fichier
- les autres utilisateurs du systeme

Pour chaque fichier et par type d'utilisateur il existe trois principaux :

- `w` autorisation d'ecriture
- `r` autorisation de lecture
- `x` autorisation d'execution
- `-` aucun droit d'acces

Sous Linux il existe differentes types de fichiers :

| Type              | Code  |
|-------------------|-------|
|ordinaire          | -     |
|repertoire         | d     |
|lien symbolique    | l     |
|pipe nomme         | p     |

### Pour les fichiers ordinaires

#### Droit de lecture

L'utilisateur est autorise a lire le contenu du fichier (le visualiser),le
copier, le compiler. Sans ce droit, l'utilisateur ne peut pas, par exemple
copier ce fichier ou le compiler.

#### Droit d'ecriture

L'utilisateur peut modifier (ecrire dans) le fichier.
**Attention:** pour pouvoir modifier le fichier il faut l'ouvrir, donc le droit
d'ecriture seul (sans le droit de lecture) ne permet pas de modifier le fichier.

#### Droit d'execution

Si le fichier est executable (binaire, script shell, ...), l'utilisateur peut
l'executer le fichier.

### Pour les repertoires (catalogue)

#### Droit de lecture (rep)

L'utilisateur est autorise a lister le contenu du repertoire.

#### Droit d'ecriture (rep)

L'utilisateur est autorise a creer, supprimer ou renommer des fichiers du repertoire.

#### Droit Droit d'execution

L'utilisateur est autorise a acceder au repertoire (faire la commande `cd`).

### Signification de la ligne `drw-r-xr-x 2 etudiant SMI 4096 2012-04-23 09:14 cours`

- `cours`: Le nom du fichier
- `d` : est un repertoire
- `rw-r-xr-x` : Masque de protection, chaque 3 char represent : User - Group - Others
- `2` : nombre de liens
- `etudiant` : user
- `SMI` : group
- `4096` : nombre d'inode
- `2012-04-23 09:14` : date de modification

## Modification des droits d'acces aux fichiers

### Modification des droits d'acces

La protection d'un fichier ne peut etre modifiee que par le proprietaire a
l'aide de la commande `chmod` (CHange MODe). Il existe deux modes d'utilisation
de cette commande. La premiere utilise la description des protections par un
nombre octal.

> [!Example]
>
> ```bash
> $ chmod 765 => rwx rw- r-x
> succes
> ```

La deuxieme mode d'utilisation de chmod, le mod symbolique, permet une description
absolue ou relative des droits d'acces. comme suit :
une combinaison de lettre :

- `u` : user=proprietaire
- `g` : groupe
- `o` : other
- `a` : all
- `+` : permet d'ajouter un droit d'acces
- `-` : permet de supprimer un droit d'acces
- `=` : permet d'affecter un droit de maniere absolut (tous les autres bits = `-`)

### Notion d'inode

Un noeud d;index ou inode (contraction de l'anglais index et node) est une
structure de donnees contenant des informations a propos d'un fichier ou
repertoire stocke dans certains systemes de fichiers.

#### Structure d'un inode

- Le type (fichier ordinaire, special, catalogue, ...)
- le nombre de liens,
- UID (User IDentification): numero d'utilisateur du proprietaire
- GID (Group IDentificaition): numero du groupe proprietaire
- Taille du fichier en octes
- Adresse des blocs de donnees (qui contiennent le fichier)
- Droits du fichier
- Date de la derniere modification
- Date de creation
